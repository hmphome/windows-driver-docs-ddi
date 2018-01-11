---
UID: NF.wsk.WskReleaseProviderNPI
title: WskReleaseProviderNPI function
author: windows-driver-content
description: The WskReleaseProviderNPI function releases a Network Programming Interface (NPI) that was captured with WskCaptureProviderNPI.
old-location: netvista\wskreleaseprovidernpi.htm
old-project: NetVista
ms.assetid: 6b0b995a-61db-4bdf-a896-74d91bd192e7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WskReleaseProviderNPI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskReleaseProviderNPI
req.alt-loc: Netio.lib,Netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WskReleaseProviderNPI function



## -description
The 
  <b>WskReleaseProviderNPI</b> function releases a 
  <a href="netvista.network_programming_interface">Network Programming Interface
  (NPI)</a> that was captured with 
  <a href="netvista.wskcaptureprovidernpi">WskCaptureProviderNPI</a>.



## -syntax

````
VOID WskReleaseProviderNPI(
  _In_ PWSK_REGISTRATION WskRegistration
);
````


## -parameters

### -param WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="netvista.wskregister">WskRegister</a> that identifies a WSK
     application's registration instance.


## -returns
None


## -remarks
For each call to
    <b>WskCaptureProviderNPI</b> that returns a success code, there must be exactly one corresponding 
    <b>WskReleaseProviderNPI</b> call that uses
    the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskCaptureProviderNPI</b>.


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
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Netio.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wskcaptureprovidernpi">WskCaptureProviderNPI</a>
</dt>
<dt>
<a href="netvista.wsk_registration">WSK_REGISTRATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WskReleaseProviderNPI function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
