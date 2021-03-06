---
UID: NF:wdm.RtlCmEncodeMemIoResource
title: RtlCmEncodeMemIoResource function
author: windows-driver-content
description: The RtlCmEncodeMemIoResource routine updates a CM_PARTIAL_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses.
old-location: kernel\rtlcmencodememioresource.htm
old-project: kernel
ms.assetid: 69b978a2-3895-42fc-a87a-a97064d02e7a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlCmEncodeMemIoResource, RtlCmEncodeMemIoResource routine [Kernel-Mode Driver Architecture], k109_62e5d339-a7ba-43ff-9886-bbae38b4957a.xml, kernel.rtlcmencodememioresource, wdm/RtlCmEncodeMemIoResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlCmEncodeMemIoResource
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlCmEncodeMemIoResource function


## -description


The <b>RtlCmEncodeMemIoResource</b> routine updates a <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to describe a range of memory or I/O port addresses.


## -parameters




### -param Descriptor [in]

A pointer to the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure to update. 


### -param Type [in]

The resource type of the memory. This parameter can be <b>CmResourceTypeMemory</b>, <b>CmResourceTypeMemoryLarge</b>, or <b>CmResourceTypePort</b>.


### -param Length [in]

The length, in bytes, of the range of allocated addresses.


### -param Start [in]

The starting address of the range of memory or I/O port addresses.


## -returns



<b>RtlCmEncodeMemIoResource</b> returns an NTSTATUS value. This routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure has been updated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified value for <i>Length</i> cannot be encoded in a <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One or more of the specified parameters are invalid.

</td>
</tr>
</table>
 




## -remarks



Addresses that are larger than 32 bits in length must satisfy certain alignment restrictions or else the routine returns STATUS_UNSUCCESSFUL.

<table>
<tr>
<th>Address length</th>
<th>Alignment restriction</th>
</tr>
<tr>
<td>
40 bits

</td>
<td>
Lowest 8 bits must be zero.

</td>
</tr>
<tr>
<td>
48 bits

</td>
<td>
Lowest 16 bits must be zero.

</td>
</tr>
<tr>
<td>
64 bits

</td>
<td>
Lowest 32 bits must be zero.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561768">RtlCmDecodeMemIoResource</a>
 

 

