---
UID: NF.fltkernel.FltCloseSectionForDataScan
title: FltCloseSectionForDataScan function
author: windows-driver-content
description: The FltCloseSectionForDataScan routine closes a section object associated with a file stream.
old-location: ifsk\fltclosesectionfordatascan.htm
old-project: ifsk
ms.assetid: 2B3C52FD-80D7-4ECA-9B33-7916FB47B0B2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltCloseSectionForDataScan
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCloseSectionForDataScan routine is available starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltCloseSectionForDataScan
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
---

# FltCloseSectionForDataScan function



## -description
The <b>FltCloseSectionForDataScan</b> routine closes a section object associated with a file stream.



## -syntax

````
NTSTATUS FltCloseSectionForDataScan(
  _In_ PFLT_CONTEXT SectionContext
);
````


## -parameters

### -param SectionContext [in]

A pointer to the section context to close. 


## -returns
<b>FltCloseSectionForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The section context was not properly created. An allocated section context must first be passed to <a href="ifsk.fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>. This is an error code. 
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The section context is already closed.

 


## -remarks
Minifilters use the <b>FltCloseSectionForDataScan</b> routine to deallocate  and remove a section context from a file object. All previously allocated section contexts passed to <a href="ifsk.fltcreatesectionfordatascan">FltCreateSectionForDataScan</a> must be passed to <b>FltCloseSectionForDataScan</b>. Otherwise, minifilters can call <a href="ifsk.fltreleasecontext">FltReleaseContext</a> if the section context was allocated with <a href="ifsk.fltallocatecontext">FltAllocateContext</a> but no section was created with  <b>FltCreateSectionForDataScan</b>.

After <b>FltCloseSectionForDataScan</b> returns, operations that conflict with the section  described by <i>SectionContext</i> will not be synchronized by the filter manager.


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
The <b>FltCloseSectionForDataScan</b> routine is available starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltallocatecontext">FltAllocateContext</a>
</dt>
<dt>
<a href="ifsk.fltcreatesectionfordatascan">FltCreateSectionForDataScan</a>
</dt>
<dt>
<a href="ifsk.fltdeletecontext">FltDeleteContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCloseSectionForDataScan routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
