---
UID: NF.wdm.PoSetDeviceBusyEx
title: PoSetDeviceBusyEx function
author: windows-driver-content
description: The PoSetDeviceBusyEx routine notifies the power manager that the device associated with the specified idle counter is busy.
old-location: kernel\posetdevicebusyex.htm
old-project: kernel
ms.assetid: 3f4d01fe-84cb-424e-9107-e29c4e25d85c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PoSetDeviceBusyEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with SP1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoSetDeviceBusyEx
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

# PoSetDeviceBusyEx function



## -description
The <b>PoSetDeviceBusyEx</b> routine notifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> that the device associated with the specified idle counter is busy.



## -syntax

````
VOID PoSetDeviceBusyEx(
  _Inout_ PULONG IdlePointer
);
````


## -parameters

### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="kernel.poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoSetDeviceBusyEx</b>.


## -returns
None


## -remarks
This routine is a direct replacement for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a> macro. If you are writing new driver code for Windows Vista with Service Pack 1 (SP1) and later versions of Windows, call <b>PoSetDeviceBusyEx</b> instead of <b>PoSetDeviceBusy</b>.

A driver calls the <b>PoSetDeviceBusyEx</b> and <b>PoRegisterDeviceForIdleDetection</b> routines to enable system idle detection for its device. If a device that is registered for idle detection stays idle for the driver-specified time-out period, the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request to put the device in a requested sleep state.

<b>PoSetDeviceBusyEx</b> reports that the device is busy, so that the power manager can restart its idle countdown. If the device is in a sleep state, <b>PoSetDeviceBusyEx</b> does not change the state of the device. That is, it does not cause the system to send an <b>IRP_MN_SET_POWER</b> request to awaken the device.

<b>PoSetDeviceBusyEx</b> is designed for use with I/O operations that are relatively brief compared to the time-out period of the idle counter. For longer operations that might exceed this period, use the <a href="kernel.postartdevicebusy">PoStartDeviceBusy</a> and <a href="kernel.poenddevicebusy">PoEndDeviceBusy</a> routines instead.

A driver that makes multiple requests for brief I/O operations should call <b>PoSetDeviceBusyEx</b> for every I/O request that it makes.


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
Available starting with Windows Vista with SP1.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>
</dt>
<dt>
<a href="kernel.poenddevicebusy">PoEndDeviceBusy</a>
</dt>
<dt>
<a href="kernel.poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a>
</dt>
<dt>
<a href="kernel.postartdevicebusy">PoStartDeviceBusy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoSetDeviceBusyEx routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
