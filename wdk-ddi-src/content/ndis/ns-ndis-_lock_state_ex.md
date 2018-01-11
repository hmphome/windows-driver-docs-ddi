---
UID: NS.NDIS._LOCK_STATE_EX
title: _LOCK_STATE_EX
author: windows-driver-content
description: The LOCK_STATE_EX structure tracks the state of a read/write lock.
old-location: netvista\lock_state_ex.htm
old-project: NetVista
ms.assetid: 558b6fba-a1d8-4255-bca6-e2d83afe9e46
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _LOCK_STATE_EX, *PLOCK_STATE_EX, LOCK_STATE_EX, PLOCK_STATE_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LOCK_STATE_EX
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# _LOCK_STATE_EX structure



## -description
The <b>LOCK_STATE_EX</b> structure tracks the state of a read/write lock. This structure is opaque to NDIS
   drivers.



## -syntax

````
typedef struct _LOCK_STATE_EX {
  ;      // Reserved for NDIS.
} LOCK_STATE_EX, *PLOCK_STATE_EX;
````


## -struct-fields


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.20 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.lock_state">LOCK_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20LOCK_STATE_EX structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
