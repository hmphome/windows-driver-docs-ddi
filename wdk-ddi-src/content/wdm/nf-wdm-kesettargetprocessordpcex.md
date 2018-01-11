---
UID: NF.wdm.KeSetTargetProcessorDpcEx
title: KeSetTargetProcessorDpcEx function
author: windows-driver-content
description: The KeSetTargetProcessorDpcEx routine specifies the processor that a DPC routine will run on.
old-location: kernel\kesettargetprocessordpcex.htm
old-project: kernel
ms.assetid: a21f3304-9181-4027-9a7e-d590037b4b0f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: KeSetTargetProcessorDpcEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeSetTargetProcessorDpcEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.product: Windows 10 or later.
---

# KeSetTargetProcessorDpcEx function



## -description
The <b>KeSetTargetProcessorDpcEx</b> routine specifies the processor that a DPC routine will run on.



## -syntax

````
NTSTATUS KeSetTargetProcessorDpcEx(
  _Inout_ PKDPC             Dpc,
  _In_    PPROCESSOR_NUMBER ProcNumber
);
````


## -parameters

### -param Dpc [in, out]

A pointer to the caller's <a href="https://msdn.microsoft.com/ae8758f5-0e23-4db2-9eac-aab31d98247b">DPC object</a>. This parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure, which is an opaque, system structure that represents the DPC object. This object must previously have been initialized by the <a href="kernel.keinitializedpc">KeInitializeDpc</a> routine.


### -param ProcNumber [in]

A pointer to a caller-allocated <a href="kernel.processor_number">PROCESSOR_NUMBER</a> structure that identifies the target processor on which the DPC will be queued and executed. This structure specifies a group and a processor within this group.


## -returns
<b>KeSetTargetProcessorDpcEx</b> returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>ProcNumber</i> parameter points to an invalid processor number.

 


## -remarks
Each processor in a multiprocessor system has its own DPC queue. <b>KeSetTargetProcessorDpcEx</b> specifies which processor's queue the system should use when the driver calls the <a href="kernel.keinsertqueuedpc">KeInsertQueueDpc</a> or <a href="kernel.iorequestdpc">IoRequestDpc</a> routine to queue a DPC to be run later.

<b>KeSetTargetProcessorDpcEx</b> can specify the target processor for both ordinary DPCs and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564621">threaded DPCs</a>. An ordinary DPC cannot be preempted by even a high-priority thread, but a threaded DPC can be preempted by time-critical threads that have sufficiently high priorities.

A related routine, <a href="kernel.kesettargetprocessordpc">KeSetTargetProcessorDpc</a>, specifies a target processor for a DPC, but this routine, unlike <b>KeSetTargetProcessorDpcEx</b>, does not specify a group for the target processor. Starting with Windows 7, <b>KeSetTargetProcessorDpc</b> assumes that the target processor belongs to group 0. This behavior ensures that existing drivers that call <b>KeSetTargetProcessorDpc</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeSetTargetProcessorDpcEx</b> instead of <b>KeSetTargetProcessorDpc</b>.

A call to <b>KeSetTargetProcessorDpcEx</b> that occurs after a DPC object has been queued has no effect on the selection of a processor for the DPC routine to run on. To control the selection of the target processor, a <b>KeSetTargetProcessorDpcEx</b> call must occur before the call to <b>KeInsertQueueDpc</b> or <b>IoRequestDpc</b> that queues the DPC object.

For more information about DPC queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.


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
Version

</th>
<td width="70%">
Available starting with Windows 7.

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
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iorequestdpc">IoRequestDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>
</dt>
<dt>
<a href="kernel.keinitializedpc">KeInitializeDpc</a>
</dt>
<dt>
<a href="kernel.keinsertqueuedpc">KeInsertQueueDpc</a>
</dt>
<dt>
<a href="kernel.kesettargetprocessordpc">KeSetTargetProcessorDpc</a>
</dt>
<dt>
<a href="kernel.processor_number">PROCESSOR_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetTargetProcessorDpcEx routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
