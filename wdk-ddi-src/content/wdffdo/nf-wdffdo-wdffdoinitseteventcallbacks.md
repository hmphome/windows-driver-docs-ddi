---
UID: NF.wdffdo.WdfFdoInitSetEventCallbacks
title: WdfFdoInitSetEventCallbacks function
author: windows-driver-content
description: The WdfFdoInitSetEventCallbacks method registers a framework-based function driver's event callback functions, for a specified device.
old-location: wdf\wdffdoinitseteventcallbacks.htm
old-project: wdf
ms.assetid: 0a47ea47-590c-4395-b38e-d1f1fb1929e1
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfFdoInitSetEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfFdoInitSetEventCallbacks
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfFdoInitSetEventCallbacks function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoInitSetEventCallbacks</b> method registers a framework-based function driver's event callback functions, for a specified device.



## -syntax

````
VOID WdfFdoInitSetEventCallbacks(
  _In_ PWDFDEVICE_INIT          DeviceInit,
  _In_ PWDF_FDO_EVENT_CALLBACKS FdoEventCallbacks
);
````


## -parameters

### -param DeviceInit [in]

A pointer to a <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


### -param FdoEventCallbacks [in]

A pointer to a driver-allocated <a href="wdf.wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure.


## -returns
None


## -remarks
Before calling <b>WdfFdoInitSetEventCallbacks</b>, the driver must allocate a <a href="wdf.wdf_fdo_event_callbacks">WDF_FDO_EVENT_CALLBACKS</a> structure and fill in the structure with pointers to the driver's event callback functions.

The driver must call <b>WdfFdoInitSetEventCallbacks</b> before calling <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="wdf.creating_a_framework_device_object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitSetEventCallbacks</b> method, see <a href="wdf.creating_device_objects_in_a_function_driver">Creating Device Objects in a Function Driver</a>.

The following code example initializes a WDF_FDO_EVENT_CALLBACKS structure and then calls <b>WdfFdoInitSetEventCallbacks</b>.


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
<dt>Wdffdo.h (include Wdf.h)</dt>
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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_deviceinitapi">DeviceInitAPI</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_fdo_event_callbacks_init">WDF_FDO_EVENT_CALLBACKS_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitSetEventCallbacks method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
