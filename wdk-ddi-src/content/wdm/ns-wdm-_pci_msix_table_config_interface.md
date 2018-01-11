---
UID: NS.WDM._PCI_MSIX_TABLE_CONFIG_INTERFACE
title: _PCI_MSIX_TABLE_CONFIG_INTERFACE
author: windows-driver-content
description: The PCI_MSIX_TABLE_CONFIG_INTERFACE structure enables device drivers to modify their MSI-X interrupt settings. This structure describes the GUID_MSIX_TABLE_CONFIG_INTERFACE interface.
old-location: kernel\pci_msix_table_config_interface.htm
old-project: kernel
ms.assetid: 0809a963-a0e7-49ca-b483-c39f1606051e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PCI_MSIX_TABLE_CONFIG_INTERFACE, PPCI_MSIX_TABLE_CONFIG_INTERFACE, *PPCI_MSIX_TABLE_CONFIG_INTERFACE, PCI_MSIX_TABLE_CONFIG_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCI_MSIX_TABLE_CONFIG_INTERFACE
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _PCI_MSIX_TABLE_CONFIG_INTERFACE structure



## -description
The <b>PCI_MSIX_TABLE_CONFIG_INTERFACE</b> structure enables device drivers to modify their MSI-X interrupt settings. This structure  describes the <a href="kernel.guid_msix_table_config_interface">GUID_MSIX_TABLE_CONFIG_INTERFACE</a> interface.



## -syntax

````
typedef struct _PCI_MSIX_TABLE_CONFIG_INTERFACE {
  USHORT                     Size;
  USHORT                     Version;
  PVOID                      Context;
  PINTERFACE_REFERENCE       InterfaceReference;
  PINTERFACE_DEREFERENCE     InterfaceDereference;
  PPCI_MSIX_SET_ENTRY        SetTableEntry;
  PPCI_MSIX_MASKUNMASK_ENTRY MaskTableEntry;
  PPCI_MSIX_MASKUNMASK_ENTRY UnmaskTableEntry;
  PPCI_MSIX_GET_ENTRY        GetTableEntry;
  PPCI_MSIX_GET_TABLE_SIZE   GetTableSize;
} PCI_MSIX_TABLE_CONFIG_INTERFACE, *PPCI_MSIX_TABLE_CONFIG_INTERFACE;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version.


### -field Context

A pointer to interface-specific context information. 


### -field InterfaceReference

A pointer to an <a href="kernel.interfacereference">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="kernel.interfacedereference">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SetTableEntry

A pointer to the interface's <a href="..\wdm\nc-wdm-pci_msix_set_entry.md">SetTableEntry</a> routine.


### -field MaskTableEntry

A pointer to the interface's <a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">MaskTableEntry</a> routine.


### -field UnmaskTableEntry

A pointer to the interface's <a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">UnmaskTableEntry</a> routine.


### -field GetTableEntry

Reserved for future use.


### -field GetTableSize

Reserved for future use.


## -remarks
A driver obtains a pointer to the <b>PCI_MSIX_TABLE_CONFIG_INTERFACE</b> structure by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to <a href="kernel.guid_msix_table_config_interface">GUID_MSIX_TABLE_CONFIG_INTERFACE</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.guid_msix_table_config_interface">GUID_MSIX_TABLE_CONFIG_INTERFACE</a>
</dt>
<dt>
<a href="kernel.interfacedereference">InterfaceDereference</a>
</dt>
<dt>
<a href="kernel.interfacereference">InterfaceReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">MaskTableEntry</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pci_msix_set_entry.md">SetTableEntry</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">UnmaskTableEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_MSIX_TABLE_CONFIG_INTERFACE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
