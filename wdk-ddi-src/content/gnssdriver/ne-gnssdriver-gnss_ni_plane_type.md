---
UID: NE:gnssdriver.GNSS_NI_PLANE_TYPE
title: GNSS_NI_PLANE_TYPE
author: windows-driver-content
description: This enumeration indicates the plane type of a network initiated (NI) request represented by the GNSS_NI_REQUEST_PARAM structure.
old-location: sensors\gnss_ni_plane_type.htm
old-project: sensors
ms.assetid: F06FFABA-D7AB-4301-9F73-CE4BBB0B8AA6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GNSS_NI_CP, GNSS_NI_PLANE_TYPE, GNSS_NI_PLANE_TYPE enumeration [Sensor Devices], GNSS_NI_SUPL, GNSS_NI_V2UPL, gnssdriver/GNSS_NI_CP, gnssdriver/GNSS_NI_PLANE_TYPE, gnssdriver/GNSS_NI_SUPL, gnssdriver/GNSS_NI_V2UPL, sensors.gnss_ni_plane_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_NI_PLANE_TYPE
product:
- Windows
targetos: Windows
req.typenames: GNSS_NI_PLANE_TYPE
---

# GNSS_NI_PLANE_TYPE enumeration


## -description


This enumeration indicates the plane type of a network initiated (NI) request represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925191">GNSS_NI_REQUEST_PARAM</a> structure.


## -enum-fields




### -field GNSS_NI_SUPL

Indicates the plane type of the request is SUPL.


### -field GNSS_NI_CP

Indicates the plane type of the request is CP.


### -field GNSS_NI_V2UPL

Indicates plane type of the request is V2UPL.

