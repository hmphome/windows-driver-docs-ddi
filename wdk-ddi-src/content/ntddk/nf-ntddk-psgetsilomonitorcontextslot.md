---
UID: NF.ntddk.PsGetSiloMonitorContextSlot
title: PsGetSiloMonitorContextSlot function
author: windows-driver-content
description: This routine returns the silo context slot that was allocated by the monitor during the registration.
old-location: kernel\psgetsilomonitorcontextslot.htm
old-project: kernel
ms.assetid: 0871EA8C-4F59-451E-89FB-8A0D44219456
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PsGetSiloMonitorContextSlot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsGetSiloMonitorContextSlot
req.alt-loc: ntddk.h
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

# PsGetSiloMonitorContextSlot function



## -description
This routine returns the silo context slot that was allocated by the monitor during the registration.



## -syntax

````
ULONG PsGetSiloMonitorContextSlot(
  _In_ PSILO_MONITOR Monitor
);
````


## -parameters

### -param Monitor [in]

A pointer to the silo monitor.


## -returns
A valid silo context slot.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1607

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>