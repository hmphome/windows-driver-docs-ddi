---
UID : NF:engextcpp.ExtRemoteData.GetUchar
title : ExtRemoteData::GetUchar method
author : windows-driver-content
description : The GetUChar method returns a UCHAR version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location : debugger\extremotedata_getuchar.htm
old-project : debugger
ms.assetid : 2c4b7f40-210a-44fa-b7d4-150355d6b75b
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : EngExtCpp_Ref_687a7887-560a-4565-8417-ec46cc1ee254.xml, ExtRemoteData class [Windows Debugging], GetUchar method, ExtRemoteData, GetUchar method [Windows Debugging], debugger.extremotedata_getuchar, GetUchar, ExtRemoteData::GetUchar, GetUchar method [Windows Debugging], ExtRemoteData class
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : engextcpp.hpp
req.include-header : Engextcpp.hpp
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : engextcpp.hpp
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetUchar method
The <b>GetUChar</b> method returns a UCHAR version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.

## Syntax

````
UCHAR GetUchar();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetUChar</b> returns the UCHAR version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.

## Remarks

The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(UCHAR)</code>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544016">ExtRemoteData::GetChar</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetUchar method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>