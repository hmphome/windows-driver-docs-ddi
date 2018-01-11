---
UID: NS.WINDOT11._DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
title: _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
author: windows-driver-content
description: the DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure is returned in a NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE indication.
old-location: netvista\_dot11_wfd_discover_complete_parameters.htm
old-project: NetVista
ms.assetid: 0CAB1436-357F-4F9F-98F8-F05B3D86B00A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, *PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS
req.alt-loc: Windot11.h
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

# _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  NDIS_STATUS        Status;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  ULONG              uListOffset;
  ULONG              uListLength;
} DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS, *PDOT11_WFD_DISCOVER_COMPLETE_PARAMETERS;
````


## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_DISCOVER_COMPLETE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field Status

The appropriate status code for the device discovery operation. If this value is not <b>NDIS_STATUS_SUCCESS</b>, the rest of the members in this structure must be set to 0.


### -field uNumOfEntries

The total number of discovered devices in the list at <b>uListOffset</b>. The number of entries cannot exceed <b>DOT11_WFD_DISCOVER_COMPLETE_MAX_LIST_SIZE</b>.


### -field uTotalNumOfEntries

The total number of discovered devices in actually discovered  by the driver. The number of entries cannot exceed <b>DOT11_WFD_DISCOVER_COMPLETE_MAX_LIST_SIZE</b>.


### -field uListOffset

The offset in the <b>StatusBuffer</b> of <a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a> where the list of <a href="netvista._dot11_wfd_device_entry">DOT11_WFD_DEVICE_ENTRY</a> elements begins.


### -field uListLength

The length, in bytes of the device list at <b>uListOffset</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451704">NDIS_STATUS_DOT11_WFD_DISCOVER_COMPLETE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20 DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
