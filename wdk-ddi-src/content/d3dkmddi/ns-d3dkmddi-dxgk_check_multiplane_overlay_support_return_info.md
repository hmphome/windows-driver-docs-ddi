---
UID: NS.D3DKMDDI.DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
title: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
author: windows-driver-content
description: Specifies limitations on hardware support of multiplane overlays.
old-location: display\dxgk_check_multiplane_overlay_support_return_info.htm
old-project: display
ms.assetid: EA440D77-18E6-4EB4-8621-50C3233DFEA6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
req.alt-loc: D3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO structure



## -description
Specifies limitations on hardware support of multiplane overlays.



## -syntax

````
typedef struct DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO {
  union {
    struct {
      UINT FailingPlane;
      UINT TryAgain;
      UINT Reserved  :27;
    };
    UINT Value;
  };
} DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO;
````


## -struct-fields

### -field FailingPlane

The zero-based index of the first overlay plane in the list of planes that the hardware cannot support. For example, if planes 0 and 1 could have been supported, but not plane 2, then the driver should set <b>FailingPlane</b> to 2.

Setting this member is equivalent to setting the first 4 bits of the 32-bit <b>Value</b> member (0x0000000F).


### -field TryAgain

The multiplane overlay configuration isn't supported because of a transient condition, which isn't permanent and should end soon. Therefore the support check call should be tried again and will probably succeed after another one or two VSync intervals.

Setting this member is equivalent to setting the fifth bit of the 32-bit <b>Value</b> member (0x00000010).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A 32-bit value that identifies the hardware support limitations.


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>