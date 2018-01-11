---
UID: NF.wudfddi_hwaccess.WRITE_PORT_BUFFER_ULONG
title: WRITE_PORT_BUFFER_ULONG function
author: windows-driver-content
description: The WRITE_PORT_BUFFER_ULONG function writes a number of ULONG values from a buffer to the specified port address.
old-location: wdf\write_port_buffer_ulong.htm
old-project: wdf
ms.assetid: B5C6FA66-617E-4DB1-A62A-3F3F41E971B0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WRITE_PORT_BUFFER_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi_hwaccess.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: WRITE_PORT_BUFFER_ULONG
req.alt-loc: Wudfddi_hwaccess.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# WRITE_PORT_BUFFER_ULONG function



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_PORT_BUFFER_ULONG</b> function writes a number of ULONG values from a buffer to the specified port address.




## -syntax

````
void WRITE_PORT_BUFFER_ULONG(
  _In_ IWDFDevice3 *pDevice,
  _In_ PULONG      Port,
  _In_ PULONG      Buffer,
  _In_ ULONG       Count 
);
````


## -parameters

### -param pDevice [in]

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.


### -param Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.


### -param Buffer [in]

A pointer to a buffer from which an array of ULONG values is to be written.



### -param Count  [in]

Specifies the number of ULONG values to be written to the buffer.


## -returns
This function does not return a value.


## -remarks
For more information, see <a href="wdf.reading_and_writing_to_device_registers_in_umdf_1_x_drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.


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
<dt>Wudfddi_hwaccess.h</dt>
</dl>
</td>
</tr>
</table>