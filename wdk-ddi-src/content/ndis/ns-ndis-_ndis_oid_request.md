---
UID: NS.NDIS._NDIS_OID_REQUEST
title: _NDIS_OID_REQUEST
author: windows-driver-content
description: To query or set OID information, NDIS submits NDIS_OID_REQUEST structures to filter drivers and miniport drivers.
old-location: netvista\ndis_oid_request.htm
old-project: NetVista
ms.assetid: 3a5e151d-2a2d-4477-a736-8a5f3d3820a2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_OID_REQUEST, NDIS_OID_REQUEST, PNDIS_OID_REQUEST, *PNDIS_OID_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_OID_REQUEST
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# _NDIS_OID_REQUEST structure



## -description
To query or set OID information, NDIS submits NDIS_OID_REQUEST structures to filter drivers and
  miniport drivers.



## -syntax

````
typedef struct _NDIS_OID_REQUEST {
  NDIS_OBJECT_HEADER  Header;
  NDIS_REQUEST_TYPE   RequestType;
  NDIS_PORT_NUMBER    PortNumber;
  UINT                Timeout;
  PVOID               RequestId;
  NDIS_HANDLE         RequestHandle;
  union _REQUEST_DATA {
    struct _QUERY {
      NDIS_OID Oid;
      PVOID    InformationBuffer;
      UINT     InformationBufferLength;
      UINT     BytesWritten;
      UINT     BytesNeeded;
    } QUERY_INFORMATION;
    struct _SET {
      NDIS_OID Oid;
      PVOID    InformationBuffer;
      UINT     InformationBufferLength;
      UINT     BytesRead;
      UINT     BytesNeeded;
    } SET_INFORMATION;
    struct _METHOD {
      NDIS_OID Oid;
      PVOID    InformationBuffer;
      ULONG    InputBufferLength;
      ULONG    OutputBufferLength;
      ULONG    MethodId;
      UINT     BytesWritten;
      UINT     BytesRead;
      UINT     BytesNeeded;
    } METHOD_INFORMATION;
  } DATA;
  UCHAR               NdisReserved[NDIS_OID_REQUEST_NDIS_RESERVED_SIZE * sizeof(PVOID)];
  UCHAR               MiniportReserved[2*sizeof(PVOID)];
  UCHAR               SourceReserved[2*sizeof(PVOID)];
  UCHAR               SupportedRevision;
  UCHAR               Reserved1;
  USHORT              Reserved2;
} NDIS_OID_REQUEST, *PNDIS_OID_REQUEST;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_OID_REQUEST structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_OID_REQUEST, the 
     <b>Revision</b> member to NDIS_OID_REQUEST_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_OID_REQUEST_REVISION_1.


### -field RequestType

The request type as one of the 
     <a href="netvista.ndis_request_type">NDIS_REQUEST_TYPE</a> enumeration
     values.


### -field PortNumber

The port to which the request is sent. If the port is unknown or default, this member is
     zero.


### -field Timeout

A time-out, in seconds, for the request. NDIS can reset the driver or cancel the request if the
     time-out expires before the driver completes the request.


### -field RequestId

An identifier for the request. If a miniport driver must complete a request immediately and it
     completes the request with a status of NDIS_STATUS_INDICATION_REQUIRED, the miniport driver uses this 
     <b>RequestId</b> value to set the 
     <b>RequestId</b> member of the associated 
     <a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a> structure. 
     

NDIS or overlying drivers can also use the 
     <b>RequestId</b> to cancel a request. When a miniport driver receives a
     cancellation request, the miniport driver cancels any pending requests with a matching 
     <b>RequestId</b>. If 
     <b>RequestId</b> is zero, the miniport driver can ignore this member. For more
     information about status indications, see the following Remarks section.


### -field RequestHandle

A handle that identifies the source that issued the OID request. If a miniport driver must complete
      the request immediately and completes the request with a status of NDIS_STATUS_INDICATION_REQUIRED, the
      miniport driver uses this 
      <b>RequestHandle</b> value to set the 
      <b>DestinationHandle</b> member of the associated NDIS_STATUS_INDICATION
      structure. In this case, NDIS will send only the subsequent status indication to the source that issued
      the OID request.

For more information about status indications, see the following Remarks section.


### -field DATA

A union that defines the request data. The information in the data varies according to the type of
     request as specified by the 
     <b>RequestType</b> member. The following member structures are specified:


### -field QUERY_INFORMATION

This structure contains the parameters for an <b>NdisRequestQueryInformation</b> or
       <b>NdisRequestQueryStatistics</b> request type. This structure is specified as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
struct _QUERY
  {
    NDIS_OID    Oid;
    PVOID       InformationBuffer;
    UINT        InformationBufferLength;
    UINT        BytesWritten;
    UINT        BytesNeeded;
  } QUERY_INFORMATION;
</pre>
</td>
</tr>
</table></span></div>

### -field Oid

The object identifier of the requested operation. The value is an OID_
       <i>XXX</i> code.


### -field InformationBuffer

A pointer to a buffer into which the underlying driver or NDIS returns the requested information
       for query-information requests.


### -field InformationBufferLength

The size, in bytes, of the buffer at 
       <b>InformationBuffer</b>. The value at 
       <b>Oid</b> determines the value appropriate to this member.


### -field BytesWritten

The number of bytes that the underlying driver or NDIS transfers into the buffer at 
       <b>InformationBuffer</b> for query-information requests. If the 
       <a href="netvista.ndisoidrequest">NdisOidRequest</a> function returns
       NDIS_STATUS_INVALID_LENGTH, the value of this member is meaningless.


### -field BytesNeeded

The number of bytes that are required to return query information requested by the given OID_
        <i>XXX</i> code.

If 
        <b>NdisOidRequest</b> returns NDIS_STATUS_SUCCESS, the value of this member is
        meaningless. If the 
        <b>InformationBufferLength</b> is too small for the given OID_
        <i>XXX</i> on a query request, this member indicates how large a buffer is
        required to satisfy the request.

</dd>
</dl>

### -field SET_INFORMATION

This structure contains the parameters for an <b>NdisRequestSetInformation</b> request type. This structure
       is specified as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
struct _SET
  {
    NDIS_OID    Oid;
    PVOID       InformationBuffer;
    UINT        InformationBufferLength;
    UINT        BytesRead;
    UINT        BytesNeeded;
  } SET_INFORMATION;
</pre>
</td>
</tr>
</table></span></div>

### -field Oid

The object identifier of the requested operation. The value is an OID_
       <i>XXX</i> code.


### -field InformationBuffer

A pointer to a buffer from which the underlying driver reads caller-supplied information for
       set-information requests.


### -field InformationBufferLength

The size, in bytes, of the buffer at 
       <b>InformationBuffer</b>. The value at 
       <b>Oid</b> determines the value appropriate to this member.


### -field BytesRead

The number of bytes that the underlying driver read from the buffer at 
       <b>InformationBuffer</b> for set-information requests.


### -field BytesNeeded

The number of bytes that are required to carry out the set operation requested by the given OID_
        <i>XXX</i> code.

If 
        <b>NdisOidRequest</b> returns NDIS_STATUS_SUCCESS, the value of this member is
        meaningless. If the buffer at 
        <b>InformationBuffer</b> does not contain sufficient data for the given OID_
        <i>XXX</i> on a set request, this member indicates how much data is required.

</dd>
</dl>

### -field METHOD_INFORMATION

This structure contains the parameters for an <b>NdisRequestMethod</b> request type. This structure is
       specified as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
struct _METHOD
  {
    NDIS_OID            Oid;
    PVOID               InformationBuffer;
    ULONG               InputBufferLength;
    ULONG               OutputBufferLength;
    ULONG               MethodId;
    UINT                BytesWritten;
    UINT                BytesRead;
    UINT                BytesNeeded;
  } METHOD_INFORMATION;
</pre>
</td>
</tr>
</table></span></div>

### -field Oid

The object identifier of the requested operation. The value is an OID_
       <i>XXX</i> code.


### -field InformationBuffer

A pointer to a buffer into which the underlying driver or NDIS returns the requested information
        for query operations or from which the underlying driver reads caller-supplied information for set
        operations. These operations are specific to the type of <b>NdisRequestMethod</b> request type that is being
        made.

<div class="alert"><b>Note</b>  This buffer is used for both set-information and query-information requests. As
        a result, data in the buffer for the set-information request would be overwritten by data that is
        returned for the query-information request. The exact usage depends on the requested operation as
        specified by the 
        <b>Oid</b> member.</div>
<div> </div>

### -field InputBufferLength

The size, in bytes, of the buffer at 
       <b>InformationBuffer</b>. The value at 
       <b>Oid</b> determines the value appropriate to this member.


### -field OutputBufferLength

The number of bytes in the buffer at 
       <b>InformationBuffer</b> that the driver can write.


### -field MethodId

The method to run for a method OID. A method OID request can support multiple operations as
       defined by 
       <b>MethodId</b>. It can be any value that is greater or equal to zero. Zero
       indicates the default method. NDIS can define public method OIDs with some predefined methods.
       Miniport drivers can define custom method OIDs. For more information about custom OIDs, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569641">OID_GEN_SUPPORTED_GUIDS</a>.


### -field BytesWritten

The number of bytes that the underlying driver or NDIS transfers into the buffer at 
        <b>InformationBuffer</b> for query-information requests. If the 
        <a href="netvista.ndisoidrequest">NdisOidRequest</a> function returns
        NDIS_STATUS_INVALID_LENGTH, the value of this member is meaningless.

For method OIDs, 
        <b>BytesWritten</b> should be less than or equal to the value in the 
        <b>OutputBufferLength</b> member.


### -field BytesRead

The number of bytes that the underlying driver read from the buffer at 
        <b>InformationBuffer</b> for set-information requests.

For method OIDs, 
        <b>BytesRead</b> should be less than or equal to the value in the 
        <b>InputBufferLength</b> member.


### -field BytesNeeded

The number of bytes that are required to return query information or to carry out the set
        operation requested by the given OID_
        <i>XXX</i> code.

If 
        <b>NdisOidRequest</b> returns NDIS_STATUS_SUCCESS, the value of this member is
        meaningless. If the 
        <b>InformationBufferLength</b> is too small for the given OID_
        <i>XXX</i> on a query, this member indicates how large a buffer is required to
        satisfy the request. If the buffer at 
        <b>InformationBuffer</b> does not contain sufficient data for the given OID_
        <i>XXX</i> on a set, this member indicates how much data is required.

</dd>
</dl>
</dd>
</dl>

### -field NdisReserved

An area that is reserved for NDIS.


### -field MiniportReserved

An area that is reserved for the miniport driver.


### -field SourceReserved

An area that is reserved for the originating driver. Reserved for the allocator of the
     NDIS_OID_REQUEST structure. This is usually an NDIS protocol driver or an NDIS filter driver.


### -field SupportedRevision

The revision of an NDIS structure that was supported by an NDIS 6.0 or later driver when it
     handled an OID request. A revisioned structure is any NDIS 6.0 structure that has an 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure inside it.
     When the driver succeeds in setting an OID, it must set 
     <b>SupportedRevision</b> to the revision number of the structure that it
     supported. For more information about NDIS version information, see 
     <a href="netvista.specifying_ndis_version_information">Specifying NDIS Version
     Information</a>.


### -field Reserved1

Reserved for future use.


### -field Reserved2

Reserved for future use.


## -remarks
A protocol driver or a filter driver should allocate nonpaged memory for the buffer at 
    <b>InformationBuffer</b> and for the NDIS_OID_REQUEST structure. Using data that
    is allocated from paged memory can cause fatal page faults because the underlying drivers run at IRQL =
    DISPATCH_LEVEL to carry out the requested operation.

NDIS_OID_REQUEST contains a DATA substructure for each type of operation that a protocol driver can
    request of an underlying driver. Before calling 
    <a href="netvista.ndisoidrequest">NdisOidRequest</a>, the protocol driver fills
    in the relevant members of the substructure that represents the query or set operation it specified in
    the 
    <b>Oid</b> member. NDIS or the underlying driver fills in the remaining members
    before it returns control to the caller.

Some OID requests allow a miniport driver to provide an OID completion status with a status
    indication. In this case, the miniport driver returns NDIS_STATUS_INDICATION_REQUIRED for the completion
    status of the OID request. A miniport driver cannot return this status unless the particular OID allows
    it. To determine if this status is allowed, see the OID reference page.

If a status indication is associated with an OID request where the miniport driver returned
    NDIS_STATUS_INDICATION_REQUIRED, the driver making the status indication must set the 
    <b>DestinationHandle</b> and 
    <b>RequestId</b> members in the 
    <a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a> structure.

In this case, the driver sets the 
    <b>DestinationHandle</b> and 
    <b>RequestId</b> members to the values from the 
    <b>RequestHandle</b> and 
    <b>RequestId</b> members in the NDIS_OID_REQUEST structure, respectively.

For example, in wireless networking, the processing of an OID request can take a very long time to
    complete. In this case, the miniport driver can complete the OID request immediately and provide a status
    indication later to provide the final result for the OID request.

The 
    <b>NdisRequestGeneric</b><i>n</i>(1-4) types are available for miniport drivers that create their own internal
    requests. To implement such a request, a miniport driver assigns an internal variable to one of these
    generic types.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_request_type">NDIS_REQUEST_TYPE</a>
</dt>
<dt>
<a href="netvista.ndis_status_indication">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="netvista.ndisoidrequest">NdisOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569641">OID_GEN_SUPPORTED_GUIDS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_OID_REQUEST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
