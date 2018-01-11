---
UID: NF.ntifs.PsDereferenceImpersonationToken
title: PsDereferenceImpersonationToken function
author: windows-driver-content
description: The PsDereferenceImpersonationToken routine decrements the reference count of an impersonation token.
old-location: ifsk\psdereferenceimpersonationtoken.htm
old-project: ifsk
ms.assetid: 8320d4d1-f282-4977-96e7-de6f63d86ec4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PsDereferenceImpersonationToken
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
req.alt-api: PsDereferenceImpersonationToken
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

# PsDereferenceImpersonationToken function



## -description
The <b>PsDereferenceImpersonationToken</b> routine decrements the reference count of an impersonation token.



## -syntax

````
VOID PsDereferenceImpersonationToken(
  _In_ PACCESS_TOKEN ImpersonationToken
);
````


## -parameters

### -param ImpersonationToken [in]

Pointer to the impersonation token whose reference count is to be decremented. If this is a <b>NULL</b> pointer, <b>PsDereferenceImpersonationToken</b> does nothing.


## -returns
None


## -remarks
If the token's reference count reaches zero, the token is deleted.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


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
<a href="ifsk.psimpersonateclient">PsImpersonateClient</a>
</dt>
<dt>
<a href="ifsk.psreferenceimpersonationtoken">PsReferenceImpersonationToken</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsDereferenceImpersonationToken routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
