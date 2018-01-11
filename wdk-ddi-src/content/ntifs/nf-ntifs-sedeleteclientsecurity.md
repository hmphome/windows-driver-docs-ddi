---
UID: NF.ntifs.SeDeleteClientSecurity
title: SeDeleteClientSecurity macro
author: windows-driver-content
description: The SeDeleteClientSecurity routine deletes a client security context.
old-location: ifsk\sedeleteclientsecurity.htm
old-project: ifsk
ms.assetid: 413469b9-2f6c-4f4d-8723-80645a72744c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SeDeleteClientSecurity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeDeleteClientSecurity
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
req.irql: PASSIVE_LEVEL
---

# SeDeleteClientSecurity macro



## -description
The <b>SeDeleteClientSecurity</b> routine deletes a client security context.



## -syntax

````
VOID SeDeleteClientSecurity(
  _In_ PSECURITY_CLIENT_CONTEXT ClientContext
);
````


## -parameters

### -param ClientContext [in]

Pointer to the client security context structure to be deleted.


## -remarks
<b>SeDeleteClientSecurity</b> deletes a client security context structure and performs any necessary cleanup, such as removing any client token references.

Each call to <b>SeCreateClientSecurity</b> or <b>SeCreateClientSecurityFromSubjectContext</b> must be matched by a subsequent call to <b>SeDeleteClientSecurity</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 


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
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.secreateclientsecurity">SeCreateClientSecurity</a>
</dt>
<dt>
<a href="ifsk.secreateclientsecurityfromsubjectcontext">SeCreateClientSecurityFromSubjectContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeDeleteClientSecurity routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
