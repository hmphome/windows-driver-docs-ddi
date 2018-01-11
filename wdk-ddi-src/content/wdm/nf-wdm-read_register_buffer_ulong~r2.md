---
UID: NF.wdm.READ_REGISTER_BUFFER_ULONG~r2
title: READ_REGISTER_BUFFER_ULONG function
author: windows-driver-content
description: The READ_REGISTER_BUFFER_ULONG routine reads a number of ULONG values from the specified register address into a buffer.
old-location: kernel\read_register_buffer_ulong.htm
old-project: kernel
ms.assetid: a80d361e-81d3-483c-8ddb-d5e5a69c8ba4
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: READ_REGISTER_BUFFER_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: READ_REGISTER_BUFFER_ULONG
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
req.irql: Any level (see Remarks section)
req.product: Windows 10 or later.
---

# READ_REGISTER_BUFFER_ULONG function



## -description
The <b>READ_REGISTER_BUFFER_ULONG</b> routine reads a number of ULONG values from the specified register address into a buffer. 



## -syntax

````
VOID READ_REGISTER_BUFFER_ULONG(
  _In_  PULONG Register,
  _Out_ PULONG Buffer,
  _In_  ULONG  Count
);
````


## -parameters

### -param Register [in]

Pointer to the register, which must be a mapped range in memory space.


### -param Buffer [out]

Pointer to a buffer into which an array of ULONG values is read.


### -param Count [in]

Specifies the number of ULONG values to be read into the buffer. 


## -returns
None


## -remarks
The size of the buffer must be large enough to contain at least the specified number of ULONG values.

Callers of <b>READ_REGISTER_BUFFER_ULONG</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
Any level (see Remarks section)

</td>
</tr>
</table>