---
UID: NC.wdm.PREAD_DMA_COUNTER
title: PREAD_DMA_COUNTER
author: windows-driver-content
description: The ReadDmaCounter routine returns the number of bytes remaining to be transferred during the current subordinate DMA operation.
old-location: kernel\readdmacounter.htm
old-project: kernel
ms.assetid: c5a49bbd-ddb7-4faa-934a-d5846273d648
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReadDmaCounter
req.alt-loc: wdm.h
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# PREAD_DMA_COUNTER callback



## -description
The <b>ReadDmaCounter</b> routine returns the number of bytes remaining to be transferred during the current subordinate DMA operation.



## -prototype

````
PREAD_DMA_COUNTER ReadDmaCounter;

ULONG ReadDmaCounter(
  _In_ PDMA_ADAPTER DmaAdapter
)
{ ... }
````


## -parameters

### -param DmaAdapter [in]

Pointer to the adapter object previously returned by <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> representing the system DMA controller channel currently in use. 


## -returns
<b>ReadDmaCounter</b> returns the number of bytes remaining to be transferred in the current DMA operation.


## -remarks
<b>ReadDmaCounter</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="kernel.dma_operations">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a>.

<b>ReadDmaCounter</b> can be called only by drivers of subordinate DMA devices. Usually, the caller is the driver of a subordinate device that uses a system DMA controller's autoinitialize mode. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_irqldispatch">IrqlDispatch</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.dma_adapter">DMA_ADAPTER</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>
</dt>
<dt>
<a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PREAD_DMA_COUNTER callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
