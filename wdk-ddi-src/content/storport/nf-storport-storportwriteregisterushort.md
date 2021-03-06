---
UID: NF:storport.StorPortWriteRegisterUshort
title: StorPortWriteRegisterUshort macro
author: windows-driver-content
description: The StorPortWriteRegisterUshort routine transfers a ULONG value to the indicated HBA register address.
old-location: storage\storportwriteregisterushort.htm
old-project: storage
ms.assetid: f4beff75-6177-40c7-a62c-6e24bc54ea58
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortWriteRegisterUshort, StorPortWriteRegisterUshort routine [Storage Devices], storage.storportwriteregisterushort, storport/StorPortWriteRegisterUshort, storprt_f4cd6932-3fd0-435f-87f3-7241a5778073.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortWriteRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWriteRegisterUshort macro


## -description


The <b>StorPortWriteRegisterUshort</b> routine transfers a ULONG value to the indicated HBA register address.


## -parameters




### -param h

TBD


### -param r

TBD


### -param v

TBD






#### - HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


#### - Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory space range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567080">StorPortGetDeviceBase</a>. 


#### - Value [in]

Specifies the USHORT value to be written to the HBA's register.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564878">ScsiPortWriteRegisterUshort</a>
 

 

