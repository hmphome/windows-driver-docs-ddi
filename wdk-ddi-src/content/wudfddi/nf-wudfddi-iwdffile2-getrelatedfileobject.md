---
UID: NF.wudfddi.IWDFFile2.GetRelatedFileObject
title: IWDFFile2::GetRelatedFileObject method
author: windows-driver-content
description: The GetRelatedFileObject method retrieves the IWDFFile interface of a related file object, which is a file object that has a technology-specific relationship with another file object.
old-location: wdf\iwdffile2_getrelatedfileobject.htm
old-project: wdf
ms.assetid: 0ac5c19a-b3ec-4f1e-a018-2c11cc18e58d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFFile2, IWDFFile2::GetRelatedFileObject, GetRelatedFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFFile2.GetRelatedFileObject
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFFile2::GetRelatedFileObject method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetRelatedFileObject</b> method retrieves the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface of a <i>related file object</i>, which is a file object that has a technology-specific relationship with another file object.



## -syntax

````
void GetRelatedFileObject(
  [out] IWDFFile **ppRelatedFileObj
);
````


## -parameters

### -param ppRelatedFileObj [out]

The address of a location that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface of a UMDF file object. This file object is related to the file object that exposes the <a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a> interface's parent <b>IWDFFile</b> interface.


## -returns
None.


## -remarks
Use of related file objects is technology-specific. For example, <a href="https://msdn.microsoft.com/dcd28218-b3bf-4e5d-b1a7-6910103afb96">kernel streaming</a> uses related file objects to represent the parent filters of child pins.

For more information about related file objects, see the <b>GetRelatedFileObject</b> member of the kernel-mode <a href="kernel.file_object">FILE_OBJECT</a> structure.

The following code example retrieves the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface of a related file object, from the <b>IWDFFile</b> interface that a driver's <a href="wdf.iqueuecallbackcreate_oncreatefile">IQueueCallbackCreate::OnCreateFile</a>  callback function receives.


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
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile2::GetRelatedFileObject method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
