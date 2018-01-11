---
UID: NF.fwpsk.FwpsAcquireWritableLayerDataPointer0
title: FwpsAcquireWritableLayerDataPointer0 function
author: windows-driver-content
description: The FwpsAcquireWritableLayerDataPointer0 function returns layer-specific data that can be inspected and changed.Note  FwpsAcquireWritableLayerDataPointer0 is a specific version of FwpsAcquireWritableLayerDataPointer.
old-location: netvista\fwpsacquirewritablelayerdatapointer0.htm
old-project: NetVista
ms.assetid: 79816d01-bf27-49d0-b6f1-083b7e87cc4e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FwpsAcquireWritableLayerDataPointer0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsAcquireWritableLayerDataPointer0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FwpsAcquireWritableLayerDataPointer0 function



## -description
The 
  <b>FwpsAcquireWritableLayerDataPointer0</b> function returns layer-specific data that can be inspected and
  changed.



## -syntax

````
NTSTATUS NTAPI FwpsAcquireWritableLayerDataPointer0(
  _In_    UINT64             classifyHandle,
  _In_    UINT64             filterId,
  _In_    UINT32             flags,
  _Out_   PVOID              *writableLayerData,
  _Inout_ FWPS_CLASSIFY_OUT0 *classifyOut
);
````


## -parameters

### -param classifyHandle [in]

A handle for the classify request.
     This handle is obtained by calling 
     <a href="netvista.fwpsacquireclassifyhandle0">
     FwpsAcquireClassifyHandle0</a>.


### -param filterId [in]

The value of the 
     <b>FilterId</b> member of the 
     <a href="netvista.classifyfn">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="netvista.fwps_filter1">FWPS_FILTER1</a>.


### -param flags [in]

Reserved for future use. Set to zero.


### -param writableLayerData [out]

A data buffer that contains the modifiable data for the layer. The supported data types, which are listed in the following Remarks section, are defined as
     structures. On return, the data can be accessed by casting the void pointer to the appropriate structure
     type.


### -param classifyOut [in, out]

Set to the 
     <i>classifyOut</i> parameter of the callout driver's 
     <a href="netvista.classifyfn">classifyFn</a> function. The 
     <i>classifyOut</i> parameter of 
     classifyFn is listed as an output parameter in the header, but it contains enough information on
     input to be useful to the engine when passed to 
     <b>FwpsAcquireWritableLayerDataPointer0</b>.


## -returns
The 
     <b>FwpsAcquireWritableLayerDataPointer0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callback function was successfully registered.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
<b>FwpsAcquireWritableLayerDataPointer0</b> sets the following members of the <a href="netvista.fwps_classify_out0">FWPS_CLASSIFY_OUT0</a> structure:<ul>
<li><i>classifyOut</i>-&gt;<b>actionType</b> = <b>FWP_ACTION_BLOCK</b></li>
<li><i>classifyOut</i>-&gt;<b>rights</b> = ~<b>FWPS_RIGHT_ACTION_WRITE</b></li>
</ul>


For every call to this function, you must make a matching call to 
    <a href="netvista.fwpsapplymodifiedlayerdata0">FwpsApplyModifiedLayerData0</a> to
    finalize the changes that were made, even if your callout driver didn't modify any data. If you do not make the call to <b>FwpsApplyModifiedLayerData0</b>, this could result in the classify not completing correctly.

The following structures are defined to contain modifiable layer data. The pointer set on output as
    the 
    <i>writableLayerData</i> parameter can be cast to one of these types:


<a href="netvista.fwps_bind_request0">FWPS_BIND_REQUEST0</a>



<a href="netvista.fwps_connect_request0">FWPS_CONNECT_REQUEST0</a>



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
Version

</th>
<td width="70%">
Available starting with Windows 7.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.classifyfn">classifyFn</a>
</dt>
<dt>
<a href="netvista.fwps_bind_request0">FWPS_BIND_REQUEST0</a>
</dt>
<dt>
<a href="netvista.fwps_classify_out0">FWPS_CLASSIFY_OUT0</a>
</dt>
<dt>
<a href="netvista.fwps_connect_request0">FWPS_CONNECT_REQUEST0</a>
</dt>
<dt>
<a href="netvista.fwps_filter1">FWPS_FILTER1</a>
</dt>
<dt>
<a href="netvista.fwpsacquireclassifyhandle0">FwpsAcquireClassifyHandle0</a>
</dt>
<dt>
<a href="netvista.fwpsapplymodifiedlayerdata0">FwpsApplyModifiedLayerData0</a>
</dt>
<dt>
<a href="netvista.fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20FwpsAcquireWritableLayerDataPointer0 function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
