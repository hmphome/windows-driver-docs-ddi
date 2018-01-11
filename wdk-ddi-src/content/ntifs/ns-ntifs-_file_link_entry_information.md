---
UID: NS.NTIFS._FILE_LINK_ENTRY_INFORMATION
title: _FILE_LINK_ENTRY_INFORMATION
author: windows-driver-content
description: The FILE_LINK_ENTRY_INFORMATION structure describes a single NTFS hard link to an existing file.
old-location: ifsk\file_link_entry_information.htm
old-project: ifsk
ms.assetid: b42edb45-3f4f-4f65-aede-8f51149dda78
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _FILE_LINK_ENTRY_INFORMATION, PFILE_LINK_ENTRY_INFORMATION, *PFILE_LINK_ENTRY_INFORMATION, FILE_LINK_ENTRY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_LINK_ENTRY_INFORMATION
req.alt-loc: ntifs.h
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

# _FILE_LINK_ENTRY_INFORMATION structure



## -description
The <b>FILE_LINK_ENTRY_INFORMATION</b> structure describes a single NTFS hard link to an existing file.



## -syntax

````
typedef struct _FILE_LINK_ENTRY_INFORMATION {
  ULONG    NextEntryOffset;
  LONGLONG ParentFileId;
  ULONG    FileNameLength;
  WCHAR    FileName;
} FILE_LINK_ENTRY_INFORMATION, *PFILE_LINK_ENTRY_INFORMATION;
````


## -struct-fields

### -field NextEntryOffset

The offset, in bytes, to the next <b>FILE_LINK_ENTRY_INFORMATION</b> structure, or 0 if the current structure is the last  <b>FILE_LINK_ENTRY_INFORMATION</b> structure.


### -field ParentFileId

The ID of the parent directory of the link.


### -field FileNameLength

The length, in characters, of the <b>FileName</b> for the link.


### -field FileName

The name of the link.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include FltKernel.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.file_links_information">FILE_LINKS_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_LINK_ENTRY_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
