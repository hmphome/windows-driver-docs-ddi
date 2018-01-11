---
UID: NF.ks.KsInitializeDeviceProfile
title: KsInitializeDeviceProfile function
author: windows-driver-content
description: The KsInitializeDeviceProfile API must be called by all miniport drivers to initialize the profile store and publish the device profiles.
old-location: stream\ksinitializedeviceprofile.htm
old-project: stream
ms.assetid: E6AD21CE-C218-439F-A8F7-8E1AAF307A57
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsInitializeDeviceProfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ksmedia.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsInitializeDeviceProfile
req.alt-loc: ks.lib,ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsInitializeDeviceProfile function



## -description
The <b>KsInitializeDeviceProfile</b> API must be called by all miniport drivers to initialize the profile store and publish the device profiles.




## -syntax

````
 __drv_maxIRQL(PASSIVE_LEVEL) KSDDKAPI NTSTATUS NTAPI KsInitializeDeviceProfile(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters

### -param FilterFactory [in]

This is the <a href="stream.ksfilterfactory">KSFILTERFACTORY</a> that was created by the camera driver to uniquely identify the camera’s filter factory.


## -returns
If the provided <b>KSFILTERFACTORY</b> does not contain a device interface associated with the <b>KSCATEGORY_VIDEO_CAMERA</b>, this API call will fail with <b>STATUS_INVALID_PARAMETER</b>.


## -remarks
It is required that the <b>ReferenceGuid</b> field of the <a href="stream.ksfilter_descriptor">KSFILTER_DESCRIPTOR</a> structure contained with the <b>KSFILTERFACTORY</b> be set with a unique GUID for this filter type.  And the <b>Flags</b> field of the <b>KSFILTER_DESCRIPTOR</b> has the <b>KSFILTER_FLAG_PRIORITIZE_REFERENCEGUID</b> flag set.

To delete all profiles from the profile store associated with the device interface for this <b>KSFILTERFACTORY</b>, the driver may call <b>KsInitializeDeviceProfile</b> followed immediately by <a href="stream.kspersistdeviceprofile">KsPersistDeviceProfile</a>.  This would result in an empty profile information, which would remove the profile information from the profile store.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>