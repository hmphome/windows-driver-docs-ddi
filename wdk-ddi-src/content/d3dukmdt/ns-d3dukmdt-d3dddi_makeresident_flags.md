---
UID: NS.D3DUKMDT.D3DDDI_MAKERESIDENT_FLAGS
title: D3DDDI_MAKERESIDENT_FLAGS
author: windows-driver-content
description: D3DDDI_MAKERESIDENT_FLAGS is used with MakeResident (pfnMakeResidentCb or D3DKMTMakeResident) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dddi_makeresident_flags.htm
old-project: display
ms.assetid: 1EC4F8EE-1284-4752-8941-F1C31415BF29
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3DDDI_MAKERESIDENT_FLAGS, D3DDDI_MAKERESIDENT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MAKERESIDENT_FLAGS
req.alt-loc: d3dukmdt.h
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
---

# D3DDDI_MAKERESIDENT_FLAGS structure



## -description
<b>D3DDDI_MAKERESIDENT_FLAGS</b> is used with <b>MakeResident</b> (<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a> or <a href="display.d3dkmtmakeresident">D3DKMTMakeResident</a>) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.



## -syntax

````
typedef struct D3DDDI_MAKERESIDENT_FLAGS {
  union {
    struct {
      UINT CantTrimFurther  :1;
      UINT MustSucceed  :1;
      UINT Reserved  :30;
    };
    UINT Value;
  };
} D3DDDI_MAKERESIDENT_FLAGS;
````


## -struct-fields

### -field CantTrimFurther

This flag should be used after the user mode driver has trimmed all other possible resources in the device and require the current resource to be made resident in order to make forward progress on a particular single atomic operation.


### -field MustSucceed

This flag may only be set if <b>CantTrimFurther</b> is also set. It indicates that the resource being made resident is critical to the device forward progress. If the video memory manager can’t satisfy the request the device will be put in error.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

The consolidated value of the structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

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
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a>
</dt>
<dt>
<a href="display.d3dkmtmakeresident">D3DKMTMakeResident</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MAKERESIDENT_FLAGS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
