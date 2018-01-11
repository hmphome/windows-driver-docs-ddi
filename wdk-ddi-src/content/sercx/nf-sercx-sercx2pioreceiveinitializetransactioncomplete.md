---
UID: NF.sercx.SerCx2PioReceiveInitializeTransactionComplete
title: SerCx2PioReceiveInitializeTransactionComplete function
author: windows-driver-content
description: The SerCx2PioReceiveInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new PIO-receive transaction.
old-location: serports\sercx2pioreceiveinitializetransactioncomplete.htm
old-project: serports
ms.assetid: 66F8DA69-F4AD-45BE-A211-184E87882908
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2PioReceiveInitializeTransactionComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCx2PioReceiveInitializeTransactionComplete
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# SerCx2PioReceiveInitializeTransactionComplete function



## -description
The <b>SerCx2PioReceiveInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new PIO-receive transaction.



## -syntax

````
VOID SerCx2PioReceiveInitializeTransactionComplete(
  [in] SERCX2PIORECEIVE PioReceive,
  [in] BOOLEAN          InitSuccess
);
````


## -parameters

### -param PioReceive [in]

A <a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns
None.


## -remarks
Before SerCx2 starts a PIO-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller hardware. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2PioReceiveInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2PioReceiveInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioReceiveInitializeTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.


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
Available starting with Windows 8.1.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
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
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a>
</dt>
<dt>
<a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a>
</dt>
<dt>
<a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioReceiveInitializeTransactionComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
