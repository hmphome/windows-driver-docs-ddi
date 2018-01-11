---
UID: NS.UCXUSBDEVICE._UCX_USBDEVICE_CHARACTERISTIC
title: _UCX_USBDEVICE_CHARACTERISTIC
author: windows-driver-content
description: Stores the characteristics of an device.
old-location: buses\ucx_usbdevice_characteristic.htm
old-project: UsbRef
ms.assetid: 31BF5607-51EA-4FBF-A754-872FBD45915D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UCX_USBDEVICE_CHARACTERISTIC, PUCX_USBDEVICE_CHARACTERISTIC, *PUCX_USBDEVICE_CHARACTERISTIC, UCX_USBDEVICE_CHARACTERISTIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCX_USBDEVICE_CHARACTERISTIC
req.alt-loc: Ucxusbdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_CHARACTERISTIC structure



## -description
Stores the characteristics of an device. 



## -syntax

````
typedef struct _UCX_USBDEVICE_CHARACTERISTIC {
  ULONG                             Size;
  UCX_USBDEVICE_CHARACTERISTIC_TYPE CharacteristicType;
  union {
    UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY PathDelay;
  };
} UCX_USBDEVICE_CHARACTERISTIC, *PUCX_USBDEVICE_CHARACTERISTIC;
````


## -struct-fields

### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="buses.ucx_usbdevice_characteristic_type">UCX_USBDEVICE_CHARACTERISTIC_TYPE</a>-type value that indicates the type of device characteristic.


### -field PathDelay

A <a href="buses.ucx_usbdevice_characteristic_path_delay">UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</a>-typed value that indicates the path delay values for the endpoint.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ucxusbdevice.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCX_USBDEVICE_CHARACTERISTIC structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
