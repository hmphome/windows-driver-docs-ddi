---
UID: NF:ndis.NdisCmModifyCallQoSComplete
title: NdisCmModifyCallQoSComplete function
author: windows-driver-content
description: NdisCmModifyCallQoSComplete indicates the completion of the client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to modify the quality of service on a VC.
old-location: netvista\ndiscmmodifycallqoscomplete.htm
old-project: netvista
ms.assetid: 8489dc63-8e92-45c9-b4a8-593b511743b0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisCmModifyCallQoSComplete, NdisCmModifyCallQoSComplete function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_471da783-5fb9-459e-98a1-209e8b11a3b5.xml, ndis/NdisCmModifyCallQoSComplete, netvista.ndiscmmodifycallqoscomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmModifyCallQoSComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmModifyCallQoSComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_CallManager_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCmModifyCallQoSComplete
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmModifyCallQoSComplete function


## -description


<b>NdisCmModifyCallQoSComplete</b> indicates the completion of the client's request, for which the call
  manager previously returned NDIS_STATUS_PENDING, to modify the quality of service on a VC.


## -parameters




### -param Status [in]

Specifies the final status of the client's request to modify the QoS on this VC, either
     NDIS_STATUS_SUCCESS or any CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisVcHandle [in]

Specifies the handle to the VC, obtained from the 
     <i>CallMgrVcContext</i> passed in to the CM's 
     <a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">
     ProtocolCmModifyCallQoS</a> function for this request.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> specifying a QoS
     acceptable to the call manager and underlying miniport driver if 
     <i>Status</i> is set to NDIS_STATUS_SUCCESS.


## -returns



None




## -remarks



A call to 
    <b>NdisCmModifyCallQoSComplete</b> causes NDIS to call the client's 
    <a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
    ProtocolClModifyCallQoSComplete</a> function.

Because the CM can modify the client-supplied call parameters that were input to its 
    <a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">
    ProtocolCmModifyCallQoS</a> function before it calls 
    <b>NdisCmModifyCallQoSComplete</b>, the client's 
    <i>ProtocolClModifyCallQoSComplete</i> function examines the QoS to determine whether it is acceptable to
    the client. 
    <i>ProtocolClModifyCallQoSComplete</i> simply returns control if the client accepts the given call
    parameters. Otherwise, the client tears down the call.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmModifyCallQoSComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmModifyCallQoSComplete</b> instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561636">NdisClModifyCallQoS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563545">NdisMCmModifyCallQosComplete</a>



<a href="https://msdn.microsoft.com/0d925862-49af-4579-b877-c9a033e73be0">
   ProtocolClModifyCallQoSComplete</a>



<a href="https://msdn.microsoft.com/24523677-9f5a-4109-8484-95883a4d1bbf">ProtocolCmModifyCallQoS</a>
 

 

