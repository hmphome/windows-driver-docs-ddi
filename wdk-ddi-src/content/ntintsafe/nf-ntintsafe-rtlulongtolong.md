---
UID: NF.ntintsafe.RtlULongToLong
title: RtlULongToLong function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type LONG.
old-location: kernel\rtlulongtolong.htm
old-project: kernel
ms.assetid: EA30B409-8953-488B-A8AB-84A3FBED1A20
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlULongToLong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlULongToLong
req.alt-loc: Ntintsafe.h
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

# RtlULongToLong function



## -description
Converts a value of type <b>ULONG</b> to a value of type <b>LONG</b>.



## -syntax

````
NTSTATUS RtlULongToLong(
  _In_  ULONG ulOperand,
  _Out_ LONG  *plResult
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.


### -param plResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>