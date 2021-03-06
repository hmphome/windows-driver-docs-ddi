---
UID: NI:ntdddisk.IOCTL_DISK_SET_CACHE_INFORMATION
title: IOCTL_DISK_SET_CACHE_INFORMATION
author: windows-driver-content
description: Sets disk cache configuration data.
old-location: storage\ioctl_disk_set_cache_information.htm
old-project: storage
ms.assetid: ae1ca621-4862-4345-bb51-4a1c31e00542
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_SET_CACHE_INFORMATION, IOCTL_DISK_SET_CACHE_INFORMATION control code [Storage Devices], k307_4f1b855c-4788-48e9-bc26-7addf3c7e3a9.xml, ntdddisk/IOCTL_DISK_SET_CACHE_INFORMATION, storage.ioctl_disk_set_cache_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_SET_CACHE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_SET_CACHE_INFORMATION IOCTL


## -description



Sets disk cache configuration data.




## -ioctlparameters




### -input-buffer

The input buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_INFO_LENGTH_MISMATCH.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS or STATUS_INFO_LENGTH_MISMATCH if the input buffer is not large enough. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552580">DISK_CACHE_INFORMATION</a>
 

 

