---
UID: NC.ks.PFNKSCLOCK_CORRELATEDTIME
title: PFNKSCLOCK_CORRELATEDTIME
author: windows-driver-content
description: KStrClockGetCorrelatedPhysicalTime is a system-supplied routine that retrieves both the current system time minus suspended delta and the corresponding clock tick since boot.
old-location: stream\kstrclockgetcorrelatedphysicaltime.htm
old-project: stream
ms.assetid: 1ae290e4-8b89-45b7-994f-ff48ddb7a7f4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrClockGetCorrelatedPhysicalTime
req.alt-loc: ks.h
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

# PFNKSCLOCK_CORRELATEDTIME callback



## -description
<i>KStrClockGetCorrelatedPhysicalTime</i> is a system-supplied routine that retrieves both the current system time minus suspended delta and the corresponding clock tick since boot.



## -prototype

````
PFNKSCLOCK_CORRELATEDTIME KStrClockGetCorrelatedPhysicalTime;

LONGLONG FASTCALL KStrClockGetCorrelatedPhysicalTime(
  _In_  PFILE_OBJECT FileObject,
  _Out_ PLONGLONG    SystemTime
)
{ ... }
````


## -parameters

### -param FileObject [in]

A pointer to the <a href="kernel.file_object">FILE_OBJECT</a> structure to which a handle was returned when the clock instance was created.


### -param SystemTime [out]

A pointer to a 64-bit integer containing the number of clock ticks since system boot.


## -returns
This routine returns the current system time (minus any suspended delta) as a value of type LONGLONG. This value is specified in 100 nanosecond units.


## -remarks
You can obtain an entry point for this routine by supplying a driver-allocated <a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a> structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a> request.

The system time is acquired from <a href="kernel.kequeryperformancecounter">KeQueryPerformanceCounter</a>.

Both time values are specified in 100 nanosecond units.


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
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564466">KSPROPERTY_CLOCK_FUNCTIONTABLE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksclock_functiontable.md">KSCLOCK_FUNCTIONTABLE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a>
</dt>
<dt>
<a href="kernel.kequeryperformancecounter">KeQueryPerformanceCounter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrClockGetCorrelatedPhysicalTime routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
