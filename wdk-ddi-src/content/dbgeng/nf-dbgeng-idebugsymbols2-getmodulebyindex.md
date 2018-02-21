---
UID: NF:dbgeng.IDebugSymbols2.GetModuleByIndex
title: IDebugSymbols2::GetModuleByIndex method
author: windows-driver-content
description: The GetModuleByIndex method returns the location of the module with the specified index.
old-location: debugger\getmodulebyindex.htm
old-project: debugger
ms.assetid: a33f8a78-4026-4424-af42-2ad359054556
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSymbols::GetModuleByIndex, dbgeng/IDebugSymbols3::GetModuleByIndex, GetModuleByIndex method [Windows Debugging], IDebugSymbols interface, IDebugSymbols2 interface [Windows Debugging], GetModuleByIndex method, GetModuleByIndex method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging], GetModuleByIndex method, GetModuleByIndex, IDebugSymbols_0406a71f-e9eb-4acd-93e8-1637ee2506df.xml, IDebugSymbols::GetModuleByIndex, IDebugSymbols2::GetModuleByIndex, IDebugSymbols3::GetModuleByIndex, IDebugSymbols2, debugger.getmodulebyindex, GetModuleByIndex method [Windows Debugging], IDebugSymbols interface [Windows Debugging], GetModuleByIndex method, IDebugSymbols, GetModuleByIndex method [Windows Debugging], IDebugSymbols2 interface, dbgeng/IDebugSymbols2::GetModuleByIndex
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
-	IDebugSymbols.GetModuleByIndex
-	IDebugSymbols2.GetModuleByIndex
-	IDebugSymbols3.GetModuleByIndex
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetModuleByIndex method
The <b>GetModuleByIndex</b> method returns the location of the module with the specified index.

## Syntax

````
HRESULT GetModuleByIndex(
  [in]  ULONG    Index,
  [out] PULONG64 Base
);
````

## Parameters

`Index`

Specifies the index of the module whose location is requested.

`Base`

Receives the location in the target's memory address space of the module.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not loaded, and information about the module was not available.

</td>
</tr>
</table>

## Remarks

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |