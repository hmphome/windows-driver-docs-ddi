---
UID: NF.wudfddi.IWDFIoRequest.Impersonate
title: IWDFIoRequest::Impersonate method
author: windows-driver-content
description: The Impersonate method registers the interface for the method that the framework should call for impersonation.
old-location: wdf\iwdfiorequest_impersonate.htm
old-project: wdf
ms.assetid: beb630e7-9667-4bc2-bf35-69db6cf0b104
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFIoRequest, IWDFIoRequest::Impersonate, Impersonate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFIoRequest.Impersonate
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

# IWDFIoRequest::Impersonate method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Impersonate</b> method registers the interface for the method that the framework should call for impersonation.



## -syntax

````
HRESULT Impersonate(
  [in]           SECURITY_IMPERSONATION_LEVEL ImpersonationLevel,
  [in]           IImpersonateCallback         *pCallback,
  [in, optional] void                         *pvCallbackContext
);
````


## -parameters

### -param ImpersonationLevel [in]

A <a href="wdf.security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>-typed value that identifies the level of impersonation.


### -param pCallback [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iimpersonatecallback.md">IImpersonateCallback</a> interface whose method the framework calls for impersonation.


### -param pvCallbackContext [in, optional]

A pointer to a buffer that contains context information that is related to the impersonation call. The framework passes this context information in a call to the <a href="wdf.iimpersonatecallback_onimpersonate">IImpersonateCallback::OnImpersonate</a> method. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to supply a context. 


## -returns
<b>Impersonate</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
For information about how UMDF and UMDF drivers handle impersonation, see <a href="wdf.handling_client_impersonation">Handling Impersonation</a>.


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
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iimpersonatecallback.md">IImpersonateCallback</a>
</dt>
<dt>
<a href="wdf.iimpersonatecallback_onimpersonate">IImpersonateCallback::OnImpersonate</a>
</dt>
<dt>
<a href="wdf.security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::Impersonate method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
