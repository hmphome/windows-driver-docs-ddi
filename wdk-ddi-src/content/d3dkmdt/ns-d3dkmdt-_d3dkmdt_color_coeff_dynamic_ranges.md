---
UID: NS.D3DKMDT._D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
title: _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
author: windows-driver-content
description: The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor.
old-location: display\d3dkmdt_color_coeff_dynamic_ranges.htm
old-project: display
ms.assetid: 7fdd1d52-c406-4da7-adff-4300e795be00
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES, D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
req.alt-loc: d3dkmdt.h
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

# _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure



## -description
The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor.



## -syntax

````
typedef struct _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES {
  UINT FirstChannel;
  UINT SecondChannel;
  UINT ThirdChannel;
  UINT FourthChannel;
} D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES;
````


## -struct-fields

### -field FirstChannel

The bit depth of the first color channel.


### -field SecondChannel

The bit depth of the second color channel.


### -field ThirdChannel

The bit depth of the third color channel.


### -field FourthChannel

Reserved.


## -remarks
The <b>VidPnTargetColorCoeffDynamicRanges</b> member of the <a href="display.d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmdt_color_basis">D3DKMDT_COLOR_BASIS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
