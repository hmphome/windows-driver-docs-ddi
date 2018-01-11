---
UID: NF.wdfrequest.WdfRequestCompleteWithPriorityBoost
title: WdfRequestCompleteWithPriorityBoost function
author: windows-driver-content
description: The WdfRequestCompleteWithPriorityBoost method completes a specified I/O request and supplies a completion status. It also specifies a value that the system can use to boost the run-time priority of the thread that requested the I/O operation.
old-location: wdf\wdfrequestcompletewithpriorityboost.htm
old-project: wdf
ms.assetid: c09ea33d-a20e-4535-8b5c-4645a30841a7
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfRequestCompleteWithPriorityBoost
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfRequestCompleteWithPriorityBoost
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, BufAfterReqCompletedWriteA, CompleteCanceledReq, DeferredRequestCompleted, DoubleCompletion, DoubleCompletionLocal, DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, EvtSurpriseRemoveNoRequestComplete, InvalidReqAccess, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, MdlAfterReqCompletedIntIoctl, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctl, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedRead, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWrite, MdlAfterReqCompletedWriteA, MemAfterReqCompletedIntIoctl, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctl, MemAfterReqCompletedIoctlA, MemAfterReqCompletedRead, MemAfterReqCompletedReadA, MemAfterReqCompletedWrite, MemAfterReqCompletedWriteA, NoCancelFromEvtSurpriseRemove, ReqDelete, ReqIsCancOnCancReq, ReqNotCanceledLocal, ReqSendFail, RequestCompleted, RequestCompletedLocal
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

# WdfRequestCompleteWithPriorityBoost function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestCompleteWithPriorityBoost</b> method completes a specified I/O request and supplies a completion status. It also specifies a value that the system can use to boost the run-time priority of the thread that requested the I/O operation.



## -syntax

````
VOID WdfRequestCompleteWithPriorityBoost(
  _In_ WDFREQUEST Request,
  _In_ NTSTATUS   Status,
  _In_ CCHAR      PriorityBoost
);
````


## -parameters

### -param Request [in]

A handle to the framework request object that represents the I/O request that is being completed.


### -param Status [in]

An <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS value</a> that represents the completion status of the request. Valid status values include, but are not limited to, the following:




### -param STATUS_SUCCESS

The driver successfully completed the request.


### -param STATUS_CANCELLED

The driver canceled the request.


### -param STATUS_UNSUCCESSFUL

The driver encountered an error while processing the request.

</dd>
</dl>

### -param PriorityBoost [in]

A system-defined constant value by which to increment the run-time priority of the original thread that requested the operation. Constant values are device-type-specific and are defined in <i>Wdm.h</i>. The format for the constant names is <i>XXX</i>_INCREMENT. For more information about priority boost values, see <a href="wdf.specifying_priority_boosts_when_completing_i_o_requests">Specifying Priority Boosts When Completing I/O Requests</a>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Your driver should call <b>WdfRequestCompleteWithPriorityBoost</b> if you want to override the default priority boost that the framework provides. For example, the driver might set the priority boost to IO_NO_INCREMENT if it was able to complete the request quickly, perhaps because it detected an error. 

After a call to <b>WdfRequestCompleteWithPriorityBoost</b> returns, the request handle is no longer valid unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add one or more additional reference counts to the request object. Note that after <b>WdfRequestCompleteWithPriorityBoost</b> returns, the driver must not attempt to access the associated WDM IRP structure, even if it has called <b>WdfObjectReference</b>.

For more information about calling <b>WdfRequestCompleteWithPriorityBoost</b>, see <a href="wdf.completing_i_o_requests">Completing I/O Requests</a>.

The following code example shows how the example at <a href="wdf.wdfrequestcomplete">WdfRequestComplete</a> can use <b>WdfRequestCompleteWithPriorityBoost</b> instead of <b>WdfRequestComplete</b>.


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
<dt>Wdfrequest.h (include Wdf.h)</dt>
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
<a href="devtest.kmdf_bufafterreqcompletedintioctl">BufAfterReqCompletedIntIoctl</a>, <a href="devtest.kmdf_bufafterreqcompletedintioctla">BufAfterReqCompletedIntIoctlA</a>, <a href="devtest.kmdf_bufafterreqcompletedioctl">BufAfterReqCompletedIoctl</a>, <a href="devtest.kmdf_bufafterreqcompletedioctla">BufAfterReqCompletedIoctlA</a>, <a href="devtest.kmdf_bufafterreqcompletedread">BufAfterReqCompletedRead</a>, <a href="devtest.kmdf_bufafterreqcompletedreada">BufAfterReqCompletedReadA</a>, <a href="devtest.kmdf_bufafterreqcompletedwrite">BufAfterReqCompletedWrite</a>, <a href="devtest.kmdf_bufafterreqcompletedwritea">BufAfterReqCompletedWriteA</a>, <a href="devtest.kmdf_completecanceledreq">CompleteCanceledReq</a>, <a href="devtest.kmdf_deferredrequestcompleted">DeferredRequestCompleted</a>, <a href="devtest.kmdf_doublecompletion">DoubleCompletion</a>, <a href="devtest.kmdf_doublecompletionlocal">DoubleCompletionLocal</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_evtiostopcancel">EvtIoStopCancel</a>, <a href="devtest.kmdf_evtiostopcompleteorstopack">EvtIoStopCompleteOrStopAck</a>, <a href="devtest.kmdf_evtsurpriseremovenorequestcomplete">EvtSurpriseRemoveNoRequestComplete</a>, <a href="devtest.kmdf_invalidreqaccess">InvalidReqAccess</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_markcanconcancreqlocal">MarkCancOnCancReqLocal</a>, <a href="devtest.kmdf_mdlafterreqcompletedintioctl">MdlAfterReqCompletedIntIoctl</a>, <a href="devtest.kmdf_mdlafterreqcompletedintioctla">MdlAfterReqCompletedIntIoctlA</a>, <a href="devtest.kmdf_mdlafterreqcompletedioctl">MdlAfterReqCompletedIoctl</a>, <a href="devtest.kmdf_mdlafterreqcompletedioctla">MdlAfterReqCompletedIoctlA</a>, <a href="devtest.kmdf_mdlafterreqcompletedread">MdlAfterReqCompletedRead</a>, <a href="devtest.kmdf_mdlafterreqcompletedreada">MdlAfterReqCompletedReadA</a>, <a href="devtest.kmdf_mdlafterreqcompletedwrite">MdlAfterReqCompletedWrite</a>, <a href="devtest.kmdf_mdlafterreqcompletedwritea">MdlAfterReqCompletedWriteA</a>, <a href="devtest.kmdf_memafterreqcompletedintioctl">MemAfterReqCompletedIntIoctl</a>, <a href="devtest.kmdf_memafterreqcompletedintioctla">MemAfterReqCompletedIntIoctlA</a>, <a href="devtest.kmdf_memafterreqcompletedioctl">MemAfterReqCompletedIoctl</a>, <a href="devtest.kmdf_memafterreqcompletedioctla">MemAfterReqCompletedIoctlA</a>, <a href="devtest.kmdf_memafterreqcompletedread">MemAfterReqCompletedRead</a>, <a href="devtest.kmdf_memafterreqcompletedreada">MemAfterReqCompletedReadA</a>, <a href="devtest.kmdf_memafterreqcompletedwrite">MemAfterReqCompletedWrite</a>, <a href="devtest.kmdf_memafterreqcompletedwritea">MemAfterReqCompletedWriteA</a>, <a href="devtest.kmdf_nocancelfromevtsurpriseremove">NoCancelFromEvtSurpriseRemove</a>, <a href="devtest.kmdf_reqdelete">ReqDelete</a>, <a href="devtest.kmdf_reqiscanconcancreq">ReqIsCancOnCancReq</a>, <a href="devtest.kmdf_reqnotcanceledlocal">ReqNotCanceledLocal</a>, <a href="devtest.kmdf_reqsendfail">ReqSendFail</a>, <a href="devtest.kmdf_requestcompleted">RequestCompleted</a>, <a href="devtest.kmdf_requestcompletedlocal">RequestCompletedLocal</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>
</dt>
<dt>
<a href="wdf.wdfrequestcomplete">WdfRequestComplete</a>
</dt>
<dt>
<a href="wdf.wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestCompleteWithPriorityBoost method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
