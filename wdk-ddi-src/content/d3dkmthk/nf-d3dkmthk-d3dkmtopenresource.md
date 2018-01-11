---
UID: NF.d3dkmthk.D3DKMTOpenResource
title: D3DKMTOpenResource function
author: windows-driver-content
description: The D3DKMTOpenResource function opens a shared resource.
old-location: display\d3dkmtopenresource.htm
old-project: display
ms.assetid: 787ace79-c9ba-4e3e-9cee-0d07ef50ba35
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3DKMTOpenResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTOpenResource
req.alt-loc: Gdi32.dll,API-MS-Win-DX-D3DKmt-l1-1-0.dll,API-MS-Win-DX-D3DKmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
---

# D3DKMTOpenResource function



## -description
The <b>D3DKMTOpenResource</b> function opens a shared resource.



## -syntax

````
NTSTATUS D3DKMTOpenResource(
  _Inout_ D3DKMT_OPENRESOURCE *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="display.d3dkmt_openresource">D3DKMT_OPENRESOURCE</a> structure that contains parameters for opening a shared resource.


## -returns
<b>D3DKMTOpenResource</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The resource was successfully opened.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a> values.

The following code example demonstrates how an OpenGL ICD can use <a href="display.d3dkmtqueryresourceinfo">D3DKMTQueryResourceInfo</a> and <b>D3DKMTOpenResource</b> to open a shared resource.


## -remarks


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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Gdi32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Gdi32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_openresource">D3DKMT_OPENRESOURCE</a>
</dt>
<dt>
<a href="display.d3dkmtqueryresourceinfo">D3DKMTQueryResourceInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenResource function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
