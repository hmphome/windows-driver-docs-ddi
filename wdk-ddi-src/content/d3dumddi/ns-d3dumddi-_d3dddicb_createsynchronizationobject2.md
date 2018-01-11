---
UID: NS.D3DUMDDI._D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
title: _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: Describes a synchronization object that the pfnCreateSynchronizationObject2Cb function creates.
old-location: display\d3dddicb_createsynchronizationobject2.htm
old-project: display
ms.assetid: 090fe0df-d2b4-4bfd-a3f3-38bc228337ab
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2, D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
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

# _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 structure



## -description
Describes a synchronization object that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a> function creates.



## -syntax

````
typedef struct _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 {
  D3DDDI_SYNCHRONIZATIONOBJECTINFO2 Info;
  D3DKMT_HANDLE                     hSyncObject;
} D3DDDICB_CREATESYNCHRONIZATIONOBJECT2;
````


## -struct-fields

### -field Info

[in] A <a href="display.d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure that contains information about the kernel-mode synchronization object to create.


### -field hSyncObject

[out] A <b>D3DKMT_HANDLE</b> value that represents a kernel-mode handle to the created kernel-mode GPU synchronization object.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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
<a href="display.d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb.md">pfnCreateSynchronizationObject2Cb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
