---
UID: NC:storport.HW_PROCESS_SERVICE_REQUEST
title: HW_PROCESS_SERVICE_REQUEST
author: windows-driver-content
description: The HwStorProcessServiceRequest callback routine receives the device control IRP that contains the IOCTL_MINIPORT_PROCESS_SERVICE_IRP request when a caller, such as a user-mode application or kernel-mode driver, requires a &#0034;reverse callback&#0034; operation.
old-location: storage\hwstorprocessservicerequest.htm
old-project: storage
ms.assetid: bdcaf9a7-4c79-407b-bec4-182f3a1d1f37
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HW_PROCESS_SERVICE_REQUEST, HwStorProcessServiceRequest, HwStorProcessServiceRequest routine [Storage Devices], storage.hwstorprocessservicerequest, storport/HwStorProcessServiceRequest, storvmini_50b0d1a2-74bf-4ee4-a9f7-3c30f1a81507.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorProcessServiceRequest
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_PROCESS_SERVICE_REQUEST callback


## -description


The <b>HwStorProcessServiceRequest</b> callback routine receives the device control  IRP that contains the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff560432">IOCTL_MINIPORT_PROCESS_SERVICE_IRP</a> request when a caller, such as a user-mode application or kernel-mode driver, requires a "reverse callback" operation. The I/O is completed by the miniport driver when it needs to tell the caller of something or needs the caller to do something.


## -parameters




### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.


### -param Irp

A pointer to the I/O request.


## -returns



None




## -remarks



The name <b>HwStorProcessServiceRequest</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_PROCESS_SERVICE_REQUEST (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  Irp
  );</pre>
</td>
</tr>
</table></span></div>
The port driver calls the Storport virtual miniport driver's <b>HwStorProcessServiceRequest</b> routine at PASSIVE_LEVEL. The virtual miniport driver completes the IRP by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567043">StorPortCompleteServiceIrp</a> routine.


#### Examples

To define an <b>HwStorProcessServiceRequest</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorProcessServiceRequest</b> callback routine that is named <i>MyHwProcessServiceRequest</i>, use the <b>HW_PROCESS_SERVICE_REQUEST</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_PROCESS_SERVICE_REQUEST MyHwProcessServiceRequest;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
MyHwProcessServiceRequest (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  Irp
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_PROCESS_SERVICE_REQUEST</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_PROCESS_SERVICE_REQUEST</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560432">IOCTL_MINIPORT_PROCESS_SERVICE_IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567043">StorPortCompleteServiceIrp</a>
 

 

