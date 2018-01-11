---
UID: NF.wudfddi.IWDFCmResourceList.GetCount
title: IWDFCmResourceList::GetCount method
author: windows-driver-content
description: The GetCount method returns the number of resource descriptors that are contained in this interface's resource list.
old-location: wdf\iwdfcmresourcelist_getcount.htm
old-project: wdf
ms.assetid: 91F88EC2-C0BD-42E1-8C57-437909E2CCA2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFCmResourceList, IWDFCmResourceList::GetCount, GetCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFCmResourceList.GetCount
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFCmResourceList::GetCount method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>GetCount</b> method returns the number of resource descriptors that are contained in this interface's resource list.



The <b>GetCount</b> method returns the number of resource descriptors that are contained in this interface's resource list.



## -syntax

````
ULONG GetCount();
````


## -parameters


## -returns
<b>GetCount</b> returns the number of resource descriptors that are contained in this interface's resource list.

<b>GetCount</b> returns the number of resource descriptors that are contained in this interface's resource list.

<b>GetCount</b> returns the number of resource descriptors that are contained in this interface's resource list.


## -remarks
Typically, a UMDF driver calls the <b>GetCount</b> method from its <a href="wdf.ipnpcallbackhardware2_onpreparehardware">OnPrepareHardware</a> method. For more information about parsing hardware resources, see <a href="wdf.finding_and_mapping_hardware_resources_in_a_umdf_driver">Finding and Mapping Hardware Resources in a UMDF Driver</a>.

See example code in <a href="wdf.iwdfdevice3_mapiospace">IWDFDevice3::MapIoSpace</a>.


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
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfcmresourcelist.md">IWDFCmResourceList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFCmResourceList::GetCount method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
