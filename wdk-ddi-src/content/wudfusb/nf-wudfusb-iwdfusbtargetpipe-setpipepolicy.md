---
UID: NF.wudfusb.IWDFUsbTargetPipe.SetPipePolicy
title: IWDFUsbTargetPipe::SetPipePolicy method
author: windows-driver-content
description: The SetPipePolicy method sets the WinUsb pipe policy.
old-location: wdf\iwdfusbtargetpipe_setpipepolicy.htm
old-project: wdf
ms.assetid: 3c8f5c4a-a1a3-41a9-ae55-f83048aab0ec
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFUsbTargetPipe, IWDFUsbTargetPipe::SetPipePolicy, SetPipePolicy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFUsbTargetPipe.SetPipePolicy
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

# IWDFUsbTargetPipe::SetPipePolicy method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPipePolicy</b> method sets the WinUsb pipe policy.



## -syntax

````
HRESULT SetPipePolicy(
  [in] ULONG PolicyType,
  [in] ULONG ValueLength,
  [in] PVOID Value
);
````


## -parameters

### -param PolicyType [in]

The type of WinUsb pipe policy that the UMDF driver sets.


### -param ValueLength [in]

The size, in bytes, of the buffer that <b>SetPipePolicy</b> supplies for <i>Value</i>.


### -param Value [in]

A pointer to the buffer that contains the WinUsb pipe policy.


## -returns
<b>SetPipePolicy</b> returns one of the following values: 
<dl>
<dt><b>S_OK </b></dt>
</dl>
<a href="wdf.iwdfusbtargetpipe_setpipepolicy">SetPipePolicy</a> successfully set the WinUsb pipe policy. 
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
<a href="wdf.iwdfusbtargetpipe_setpipepolicy">SetPipePolicy</a> encountered an allocation failure.
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>This value corresponds to the error code that the WinUsb API returned.

 


## -remarks
Pipe policy controls the behavior of the USB pipe (for example, time-outs, handling short packets, and so on).

For more information about valid policy types and values that a UMDF driver can pass for the <i>PolicyType</i> and <i>Value</i> parameters, see the <a href="buses.winusb_setpipepolicy">WinUsb_SetPipePolicy</a> function.

For information about the behavior of the pipe policies, see <a href="buses.winusb_functions_for_pipe_policy_modification">WinUSB Functions for Pipe Policy Modification</a>.

The <b>SetPipePolicy</b> method generates a UMDF request and synchronously sends the request to the I/O target.

The following code example sets policy for input and output pipes.


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
<dt>Wudfusb.h (include Wudfusb.h)</dt>
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
<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>
</dt>
<dt>
<a href="buses.winusb_setpipepolicy">WinUsb_SetPipePolicy</a>
</dt>
<dt>
<a href="wdf.iwdfusbtargetpipe_retrievepipepolicy">IWDFUsbTargetPipe::RetrievePipePolicy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::SetPipePolicy method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
