---
UID: NS.D3DUMDDI.D3DDDIARG_PRESENTMULTIPLANEOVERLAY
title: D3DDDIARG_PRESENTMULTIPLANEOVERLAY
author: windows-driver-content
description: Specifies a multiplane overlay resource to display.
old-location: display\d3dddiarg_presentmultiplaneoverlay.htm
old-project: display
ms.assetid: 862441ee-8a6e-4ddc-8dba-d3d990f45cfc
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3DDDIARG_PRESENTMULTIPLANEOVERLAY, D3DDDIARG_PRESENTMULTIPLANEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_PRESENTMULTIPLANEOVERLAY
req.alt-loc: D3dumddi.h
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

# D3DDDIARG_PRESENTMULTIPLANEOVERLAY structure



## -description
Specifies a multiplane overlay resource to display.



## -syntax

````
typedef struct D3DDDIARG_PRESENTMULTIPLANEOVERLAY {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID    VidPnSourceId;
  D3DDDI_PRESENTFLAGS               Flags;
  D3DDDI_FLIPINTERVAL_TYPE          FlipInterval;
  UINT                              PresentPlaneCount;
  D3DDDI_PRESENT_MULTIPLANE_OVERLAY *pPresentPlanes;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  UINT                              Reserved;
#endif 
} D3DDDIARG_PRESENTMULTIPLANEOVERLAY;
````


## -struct-fields

### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.


### -field Flags

[in] A <a href="display.d3dddi_presentflags">D3DDDI_PRESENTFLAGS</a> structure that identifies, in bit-field flags, how to display.


### -field FlipInterval

[in] A value of type <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a> that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). 


### -field PresentPlaneCount

[in] The number of overlay planes that are available to display.


### -field pPresentPlanes

[in] A pointer to a structure of type <a href="display.d3dddi_present_multiplane_overlay">D3DDDI_PRESENT_MULTIPLANE_OVERLAY</a> that  describes the overlay plane to display.


### -field Reserved

[in] Reserved for system use. The driver should ignore this member.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_flipinterval_type.md">D3DDDI_FLIPINTERVAL_TYPE</a>
</dt>
<dt>
<a href="display.d3dddi_present_multiplane_overlay">D3DDDI_PRESENT_MULTIPLANE_OVERLAY</a>
</dt>
<dt>
<a href="display.d3dddi_presentflags">D3DDDI_PRESENTFLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_PRESENTMULTIPLANEOVERLAY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
