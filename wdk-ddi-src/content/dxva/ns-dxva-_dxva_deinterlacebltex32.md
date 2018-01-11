---
UID: NS.DXVA._DXVA_DEINTERLACEBLTEX32
title: _DXVA_DeinterlaceBltEx32
author: windows-driver-content
description: The DXVA_DeinterlaceBltEx structure describes parameters for deinterlace or frame-rate conversion, for combining the deinterlaced or frame-rate converted video with any supplied video substreams, and for writing the combined output to a destination surface. It is used for forwarding 32-bit DXVA_DeinterlaceBltEx calls on 64-bit drivers.
old-location: display\dxva_deinterlacebltex32.htm
old-project: display
ms.assetid: ae88acca-5d29-4cca-acae-613632d565d8
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXVA_DeinterlaceBltEx32, DXVA_DeinterlaceBltEx32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_DeinterlaceBltEx32
req.alt-loc: dxva.h
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

# _DXVA_DeinterlaceBltEx32 structure



## -description
The DXVA_DeinterlaceBltEx structure describes parameters for deinterlace or frame-rate conversion, for combining the deinterlaced or frame-rate converted video with any supplied video substreams, and for writing the combined output to a destination surface. It is used for forwarding  32-bit <a href="display.dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a> calls on 64-bit drivers. 



## -syntax

````
typedef struct _DXVA_DeinterlaceBltEx32 {
  DWORD              Size;
  DXVA_AYUVsample2   BackgroundColor;
  RECT               rcTarget;
  REFERENCE_TIME     rtTarget;
  DWORD              NumSourceSurfaces;
  FLOAT              Alpha;
  DXVA_VideoSample32 Source[MAX_DEINTERLACE_SURFACES];
  DWORD              DestinationFormat;
  DWORD              DestinationFlags;
} DXVA_DeinterlaceBltEx32;
````


## -struct-fields

### -field Size

Specifies the size of the structure, in bytes.


### -field BackgroundColor

Specifies a <a href="display.dxva_ayuvsample2">DXVA_AYUVsample2</a> structure that identifies background color and opacity level. For Windows Server 2003 with SP1 and Windows XP with SP2, the opacity level is not used and should be ignored by the driver.


### -field rcTarget

Specifies a pointer to a <a href="display.rect">RECT</a> structure that describes the location within the destination surface to which the output image is written. Note that the output image is restricted to the pixels within the <b>rcTarget</b> rectangle--that is, every pixel within this rectangle must be written to; pixels outside this rectangle must not be modified. 


### -field rtTarget

Identifies the location of the output frame within the sequence of input frames. If only deinterlacing is performed, the target time should coincide with either the starting display time of a sample, as defined in the <a href="display.dxva_videosample32">DXVA_VideoSample32</a> structure, or the midpoint between the starting display time and the ending display time. For more information, see Remarks.

If a frame-rate conversion is requested, the <b>rtTarget</b> time can be different from any of the <b>rtStart</b> times of the samples.


### -field NumSourceSurfaces

Specifies the number of valid surfaces passed in the <b>Source</b> array.


### -field Alpha

Specifies the planar-transparency value of the output image as it is written to the destination surface. For Windows Server 2003 with SP1 and Windows XP with SP2, this value is always 1.0F, which indicates that the overall image is opaque and that no alpha blending on the overall image is required.


### -field Source

Specifies an array of DXVA_VideoSample32 structures that describe the input samples that are required for the deinterlacing, frame-rate conversion, and substream-compositing operations. For information about how input samples are arranged in this array, see <a href="https://msdn.microsoft.com/99110b1a-1511-44f5-a4bb-a5e38fd41fff">Input Buffer Order</a>.


### -field DestinationFormat

Specifies format information for the destination surface. For Windows Server 2003 with SP1 and Windows XP with SP2, this member is set to 0.


### -field DestinationFlags

Specifies a collection of flags that indicate changes in the current destination surface from the previous destination surface. This member is a bitwise-OR of one or more of the flags in the <a href="display.dxva_destinationflags">DXVA_DestinationFlags</a> enumeration type.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxva_deinterlacebobdeviceclass_deinterlacebltex">DeinterlaceBltEx</a>
</dt>
<dt>
<a href="display.dxva_deinterlacecaps">DXVA_DeinterlaceCaps</a>
</dt>
<dt>
<a href="display.dxva_destinationflags">DXVA_DestinationFlags</a>
</dt>
<dt>
<a href="display.dxva_videosample32">DXVA_VideoSample32</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_DeinterlaceBltEx32 structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
