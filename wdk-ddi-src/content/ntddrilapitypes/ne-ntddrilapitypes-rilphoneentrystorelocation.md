---
UID: NE.ntddrilapitypes.RILPHONEENTRYSTORELOCATION
title: RILPHONEENTRYSTORELOCATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphoneentrystorelocation.htm
old-project: NetVista
ms.assetid: 2a20e9c8-a8f2-4519-a22b-2444c46ba13a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILPHONEENTRYSTORELOCATION, RILPHONEENTRYSTORELOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILPHONEENTRYSTORELOCATION
req.alt-loc: ntddrilapitypes.h
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

# RILPHONEENTRYSTORELOCATION enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILPHONEENTRYSTORELOCATION { 
  RIL_PBLOC_UICCFIXDIALING,
  RIL_PBLOC_OWNNUMBERS,
  RIL_PBLOC_UICCPHONEBOOK,
  RIL_PBLOC_UICCSERVICEDIALING,
  RIL_PBLOC_ALL
} RILPHONEENTRYSTORELOCATION;
````


## -enum-fields

### -field RIL_PBLOC_UICCFIXDIALING


### -field RIL_PBLOC_OWNNUMBERS


### -field RIL_PBLOC_UICCPHONEBOOK


### -field RIL_PBLOC_UICCSERVICEDIALING


### -field RIL_PBLOC_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>