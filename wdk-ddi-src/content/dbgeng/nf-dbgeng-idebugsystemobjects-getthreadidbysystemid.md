---
UID: NF:dbgeng.IDebugSystemObjects.GetThreadIdBySystemId
title: IDebugSystemObjects::GetThreadIdBySystemId method
author: windows-driver-content
description: The GetThreadIdBySystemId method returns the engine thread ID for the specified thread. The thread is specified by its system thread ID.
old-location: debugger\getthreadidbysystemid.htm
old-project: debugger
ms.assetid: 2dcb7703-df66-4795-bf59-d0851c4ccf0f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSystemObjects4::GetThreadIdBySystemId, GetThreadIdBySystemId method [Windows Debugging], IDebugSystemObjects2 interface, GetThreadIdBySystemId method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects2 interface [Windows Debugging], GetThreadIdBySystemId method, dbgeng/IDebugSystemObjects3::GetThreadIdBySystemId, GetThreadIdBySystemId method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects interface [Windows Debugging], GetThreadIdBySystemId method, IDebugSystemObjects3::GetThreadIdBySystemId, IDebugSystemObjects2::GetThreadIdBySystemId, IDebugSystemObjects, dbgeng/IDebugSystemObjects::GetThreadIdBySystemId, GetThreadIdBySystemId method [Windows Debugging], GetThreadIdBySystemId method [Windows Debugging], IDebugSystemObjects3 interface, IDebugSystemObjects3 interface [Windows Debugging], GetThreadIdBySystemId method, debugger.getthreadidbysystemid, IDebugSystemObjects4::GetThreadIdBySystemId, IDebugSystemObjects4 interface [Windows Debugging], GetThreadIdBySystemId method, dbgeng/IDebugSystemObjects2::GetThreadIdBySystemId, GetThreadIdBySystemId, IDebugSystemObjects_d9c3c65f-9078-4be8-b301-dddc789cd8b0.xml, IDebugSystemObjects::GetThreadIdBySystemId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects.GetThreadIdBySystemId
-	IDebugSystemObjects2.GetThreadIdBySystemId
-	IDebugSystemObjects3.GetThreadIdBySystemId
-	IDebugSystemObjects4.GetThreadIdBySystemId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetThreadIdBySystemId method
The <b>GetThreadIdBySystemId</b> method returns the engine thread ID for the specified thread.  The thread is specified by its system thread ID.

## Syntax

````
HRESULT GetThreadIdBySystemId(
  [in]  ULONG  SysId,
  [out] PULONG Id
);
````

## Parameters

`SysId`

Specifies the system thread ID.

`Id`

Receives the engine thread ID.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The target is a kernel-mode target.

</td>
</tr>
</table>

## Remarks

This method is only available in user-mode debugging.

For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |