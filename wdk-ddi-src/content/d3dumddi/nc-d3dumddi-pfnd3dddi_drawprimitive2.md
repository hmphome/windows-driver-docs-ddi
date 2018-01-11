---
UID: NC.d3dumddi.PFND3DDDI_DRAWPRIMITIVE2
title: PFND3DDDI_DRAWPRIMITIVE2
author: windows-driver-content
description: The DrawPrimitive2 function draws nonindexed primitives in which the Microsoft Direct3D runtime has transformed the vertex data.
old-location: display\drawprimitive2.htm
old-project: display
ms.assetid: a81080f0-fbb3-4616-9324-642b60befcb3
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrawPrimitive2
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_DRAWPRIMITIVE2 callback



## -description
The <b>DrawPrimitive2</b> function draws nonindexed primitives in which the Microsoft Direct3D runtime has transformed the vertex data.



## -prototype

````
PFND3DDDI_DRAWPRIMITIVE2 DrawPrimitive2;

__checkReturn HRESULT APIENTRY DrawPrimitive2(
  _In_       HANDLE                   hDevice,
  _In_ const D3DDDIARG_DRAWPRIMITIVE2 *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="display.d3dddiarg_drawprimitive2">D3DDDIARG_DRAWPRIMITIVE2</a> structure that describes the primitive to draw.


## -returns
<b>DrawPrimitive2</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.


## -remarks
Stream zero contains transform vertices and is the only stream that should be accessed. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_drawprimitive2">D3DDDIARG_DRAWPRIMITIVE2</a>
</dt>
<dt>
<a href="display.d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWPRIMITIVE2 callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
