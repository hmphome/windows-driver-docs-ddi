---
UID: NS:bthioctl._BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST
title: "_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST"
author: windows-driver-content
description: The BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to a combined SDP service and attribute search. This structure is passed as the input buffer to the IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH IOCTL.
old-location: bltooth\bth_sdp_service_attribute_search_request.htm
old-project: bltooth
ms.assetid: 28255569-57ce-44b7-9d53-9e8797b914c5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure [Bluetooth Devices], PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure pointer [Bluetooth Devices], _BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, bltooth.bth_sdp_service_attribute_search_request, bth_structs_0e06cbd7-0737-4786-bdc3-c9c1e980e3a3.xml, bthioctl/BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, bthioctl/PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthioctl.h
api_name:
-	BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST
product:
- Windows
targetos: Windows
req.typenames: BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST, *PBTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST
---

# _BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure


## -description


The BTH_SDP_SERVICE_ATTRIBUTE_SEARCH_REQUEST structure contains information pertinent to a combined
  SDP service and attribute search. This structure is passed as the input buffer to the 
  <a href="https://msdn.microsoft.com/f0955e88-df80-4f53-bc5f-5a38a840aab4">
  IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a> IOCTL.


## -struct-fields




### -field HANDLE_SDP_FIELD_NAME

 


### -field searchFlags



#### 


### -field uuids

An array of UUIDs that represent the services for which to query. Each entry can be a 2-byte,
     4-byte, or 16-byte type, and there can be a maximum of 12 entries. The array can be terminated before
     all 12 entries are used if a UUID entry contains all zeros.


### -field range

A variable-length array of 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=50714">SdpAttributeRange</a> structures that
     contains the range of SDP attributes for which to search.


#### - hConnection

A handle to the remote SDP server that is returned by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536688">IOCTL_BTH_SDP_CONNECT</a> IOCTL.


## -remarks



The Bluetooth driver stack determines the number of array items in the 
    <b>range</b> member by examining the length of IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH input buffer.
    Because of this, the
    <b>Parameters.DeviceIoControl.InputBufferLength</b> member passed when the IOCTL is called must be
    calculated exactly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536688">IOCTL_BTH_SDP_CONNECT</a>



<a href="https://msdn.microsoft.com/f0955e88-df80-4f53-bc5f-5a38a840aab4">
   IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=50714">SdpAttributeRange</a>
 

 

