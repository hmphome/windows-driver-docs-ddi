---
UID: NF.ntifs.IoCheckEaBufferValidity
title: IoCheckEaBufferValidity function
author: windows-driver-content
description: The IoCheckEaBufferValidity routine checks whether the specified extended attribute (EA) buffer is valid.
old-location: ifsk\iocheckeabuffervalidity.htm
old-project: ifsk
ms.assetid: 1f9a4fcb-0e70-4f13-bd38-e87bee909a26
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IoCheckEaBufferValidity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCheckEaBufferValidity
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
---

# IoCheckEaBufferValidity function



## -description
The <b>IoCheckEaBufferValidity</b> routine checks whether the specified extended attribute (EA) buffer is valid.



## -syntax

````
NTSTATUS IoCheckEaBufferValidity(
  _In_  PFILE_FULL_EA_INFORMATION EaBuffer,
  _In_  ULONG                     EaLength,
  _Out_ PULONG                    ErrorOffset
);
````


## -parameters

### -param EaBuffer [in]

Pointer to the buffer containing the EAs to be checked.


### -param EaLength [in]

Length, in bytes, of <i>EaBuffer</i>.


### -param ErrorOffset [out]

Pointer to a variable that receives the offset of the offending entry in the EA buffer if an error is found. This variable is only valid if an error occurs.


## -returns
<b>IoCheckEaBufferValidity</b> returns STATUS_SUCCESS if the EA buffer is valid; otherwise it returns STATUS_EA_LIST_INCONSISTENT.


## -remarks
<b>IoCheckEaBufferValidity</b> checks each FILE_FULL_EA_INFORMATION entry in the specified EA buffer to ensure that the following conditions are met:

The entire entry must fall within the buffer.

The value of <b>EaName</b> must be a null-terminated character array.

The value of <b>EaNameLength</b> must match the length in bytes of the <b>EaName</b> array (not including the zero-terminator).

For all entries except the last, the value of <b>NextEntryOffset</b> must be greater than zero and must fall on a ULONG boundary.

In addition, <b>IoCheckEaBufferValidity</b> checks the EA buffer to ensure that the following conditions are met:

The length passed in <i>EaLength</i> matches the actual length of the buffer.

The actual buffer length is nonnegative.

To be valid, the EA buffer must meet all of these conditions.


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt; DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.file_full_ea_information">FILE_FULL_EA_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_ea">IRP_MJ_QUERY_EA</a>
</dt>
<dt>
<a href="ifsk.irp_mj_set_ea">IRP_MJ_SET_EA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCheckEaBufferValidity function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
