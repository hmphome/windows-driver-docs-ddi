---
UID: NF.wdfdevice.WdfDeviceGetIoTarget
title: WdfDeviceGetIoTarget function
author: windows-driver-content
description: The WdfDeviceGetIoTarget method returns a handle to a function or filter driver's local I/O target, for a specified device.
old-location: wdf\wdfdevicegetiotarget.htm
old-project: wdf
ms.assetid: a0749324-8b4e-4b82-8c51-b1b8883d521e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfDeviceGetIoTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceGetIoTarget
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceGetIoTarget function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetIoTarget</b> method returns a handle to a function or filter driver's <a href="wdf.general_i_o_targets">local I/O target</a>, for a specified device.



## -syntax

````
WDFIOTARGET WdfDeviceGetIoTarget(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -returns
If the operation succeeds, <b>WdfDeviceGetIoTarget</b> returns a handle to a framework I/O target object. If the specified framework device object represents a PDO, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
When a UMDF driver sends a driver-created request to a local I/O target, the request has no associated file object. Some lower targets, such as a HIDClass-enumerated raw PDO, fail requests that have no associated file object. In this situation, a UMDF driver can specify <b>WdfIoTargetOpenLocalTargetByFile</b> to create an I/O target that represents the lower stack (just like a local target) using a file handle. As a result, any driver-created requests sent to this I/O target are associated with the file object corresponding to the handle opened.

 To do so, call the <a href="wdf.wdf_io_target_open_params_init_open_by_file">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a> function before calling <a href="wdf.wdfiotargetopen">WdfIoTargetOpen</a>.

For more information about I/O targets, see <a href="wdf.using_i_o_targets">Using I/O Targets</a>.

The following code example obtains a handle to a specified device's local I/O target.


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
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
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
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>