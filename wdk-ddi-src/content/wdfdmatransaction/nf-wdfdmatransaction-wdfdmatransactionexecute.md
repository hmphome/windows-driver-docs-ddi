---
UID: NF.wdfdmatransaction.WdfDmaTransactionExecute
title: WdfDmaTransactionExecute function
author: windows-driver-content
description: The WdfDmaTransactionExecute method begins the execution of a specified DMA transaction.
old-location: wdf\wdfdmatransactionexecute.htm
old-project: wdf
ms.assetid: 8f52557f-b65d-479d-aab4-1e4f7298c8f9
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfDmaTransactionExecute
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDmaTransactionExecute
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDmaTransactionExecute function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionExecute</b> method begins the execution of a specified DMA transaction. 



## -syntax

````
NTSTATUS WdfDmaTransactionExecute(
  _In_     WDFDMATRANSACTION DmaTransaction,
  _In_opt_ WDFCONTEXT        Context
);
````


## -parameters

### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param Context [in, optional]

Driver-defined context information. The framework passes the value specified for <i>Context</i>, which can be a pointer, to the driver's <a href="wdf.evtprogramdma">EvtProgramDma</a> event callback function. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfDmaTransactionExecute</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The driver previously called <a href="wdf.wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a> and the resources needed for the request are unavailable.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The call to <a href="wdf.wdfdmatransactionexecute">WdfDmaTransactionExecute</a> was not preceded by a call to <a href="wdf.wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a> or <a href="wdf.wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>.
<dl>
<dt><b>STATUS_WDF_BUSY</b></dt>
</dl>The device performs single-packet transfers, and the driver called <a href="wdf.wdfdmatransactionexecute">WdfDmaTransactionExecute</a> while another transaction was executing.
<dl>
<dt><b>STATUS_WDF_TOO_FRAGMENTED</b></dt>
</dl>The number of scatter/gather elements that the operating system needed to handle the specified transfer size was greater than the value that the driver's call to <a href="wdf.wdfdmaenablersetmaximumscattergatherelements">WdfDmaEnablerSetMaximumScatterGatherElements</a> specified. For more information, see the following Remarks section.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The <b>WdfDmaTransactionExecute</b> method initializes a transaction's scatter/gather list for the first <a href="wdf.dma_transactions_and_dma_transfers">DMA transfer</a> that is associated with the specified <a href="wdf.dma_transactions_and_dma_transfers">DMA transaction</a>. (For single-packet transfers, the scatter/gather list contains a single element.) Then, the method calls the driver's <a href="wdf.evtprogramdma">EvtProgramDma</a> event callback function, and the callback function can program the device to begin the transfer. 

Framework-based drivers typically call <b>WdfDmaTransactionExecute</b> from within an <a href="wdf.request_handlers">I/O queue event callback function</a>. 

After a driver has called <a href="wdf.wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a> or <a href="wdf.wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a> to initialize a DMA transaction, the driver must call <b>WdfDmaTransactionExecute</b> only once before <a href="wdf.completing_a_dma_transaction">completing the DMA transaction</a>. 


          If <b>WdfDmaTransactionInitialize<i>Xxx</i></b> returns success but <b>WdfDmaTransactionExecute</b> returns an error value, your driver must call <a href="wdf.wdfdmatransactionrelease">WdfDmaTransactionRelease</a>.

In framework versions prior to 1.11, if the device performs single-packet transfers, the operating system can execute only one DMA transaction at a time. In this case, <b>WdfDmaTransactionExecute</b> returns STATUS_WDF_BUSY if another transaction is executing.

In framework versions 1.11 and later, if the driver uses DMA version 3 to perform single-packet transfers, the operating system can store multiple DMA transactions in an internal queue. In this case, the driver can call <b>WdfDmaTransactionExecute</b> while another transaction is executing. To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> to 3.

If the device performs scatter/gather transfers, the operating system can execute multiple DMA transactions simultaneously. In this case, the driver can call <b>WdfDmaTransactionExecute</b> while another transaction is executing.

If the driver calls <a href="wdf.wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a> to report a partial transfer, and if the driver had specified the DMA transaction's data buffer by using MDLs that it chained together (using the <b>Next</b> member of the <a href="kernel.mdl">MDL</a> structure), <b>WdfDmaTransactionExecute</b> can return STATUS_WDF_TOO_FRAGMENTED because the framework might recalculate the number and size of fragments and might exceed the number of allowed fragments.

The <b>WdfDmaTransactionExecute</b> returns STATUS_SUCCESS if the transaction was successfully started. To determine if the framework successfully sent all of the transaction's transfers to the driver's <a href="wdf.evtprogramdma">EvtProgramDma</a> callback function, the driver must call <a href="wdf.wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>, <a href="wdf.wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>, or <a href="wdf.wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>.

If the value that the <i>Context</i> parameter supplies is a pointer or handle, the memory that it references must be accessible in the driver's <a href="wdf.evtprogramdma">EvtProgramDma</a> event callback function at IRQL = DISPATCH_LEVEL. You can use <a href="wdf.framework_object_context_space">framework object context</a> to meet this requirement.

The driver can call <b>WdfDmaTransactionExecute</b> in a non-blocking manner if it has previously called <a href="wdf.wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>.

For more information about DMA transactions, see <a href="wdf.starting_a_dma_transaction">Starting a DMA Transaction</a>.

The following code example is from the <a href="wdf.sample_kmdf_drivers">PCIDRV</a> sample driver. This example creates and initializes a DMA transfer and begins its execution.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdmatransaction.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.evtprogramdma">EvtProgramDma</a>
</dt>
<dt>
<a href="wdf.wdfdmaenablersetmaximumscattergatherelements">WdfDmaEnablerSetMaximumScatterGatherElements</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactioninitializeusingrequest">WdfDmaTransactionInitializeUsingRequest</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactionsetimmediateexecution">WdfDmaTransactionSetImmediateExecution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionExecute method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
