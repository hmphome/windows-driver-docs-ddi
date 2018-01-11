---
UID: NS.WINDOT11.DOT11_PHY_ATTRIBUTES~R1
title: DOT11_PHY_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_phy_attributes.htm
old-project: NetVista
ms.assetid: 9e81144e-e562-4f61-83de-7b7659106de8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: DOT11_PHY_ATTRIBUTES, DOT11_PHY_ATTRIBUTES, *PDOT11_PHY_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_PHY_ATTRIBUTES
req.alt-loc: windot11.h
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
req.product: Windows 10 or later.
---

# DOT11_PHY_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct DOT11_PHY_ATTRIBUTES {
  NDIS_OBJECT_HEADER                  Header;
  DOT11_PHY_TYPE                      PhyType;
  BOOLEAN                             bHardwarePhyState;
  BOOLEAN                             bSoftwarePhyState;
  BOOLEAN                             bCFPollable;
  ULONG                               uMPDUMaxLength;
  DOT11_TEMP_TYPE                     TempType;
  DOT11_DIVERSITY_SUPPORT             DiversitySupport;
  union {
    DOT11_HRDSSS_PHY_ATTRIBUTES HRDSSSAttributes;
    DOT11_OFDM_PHY_ATTRIBUTES   OFDMAttributes;
    DOT11_ERP_PHY_ATTRIBUTES    ERPAttributes;
  };
  ULONG                               uNumberSupportedPowerLevels;
  ULONG                               TxPowerLevels[8];
  ULONG                               uNumDataRateMappingEntries;
  DOT11_DATA_RATE_MAPPING_ENTRY       DataRateMappingEntries[DOT11_RATE_SET_MAX_LENGTH];
  DOT11_SUPPORTED_DATA_RATES_VALUE_V2 SupportedDataRatesValue;
} DOT11_PHY_ATTRIBUTES, *PDOT11_PHY_ATTRIBUTES;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_PHY_ATTRIBUTES structure. This member is formatted as an 
      <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of 
      <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_PHY_ATTRIBUTES_REVISION_1.


### -field Size

This member must be set to 
        sizeof(DOT11_PHY_ATTRIBUTES).

</dd>
</dl>
For more information about these members, see 
      <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field PhyType

The type of the PHY as specified by a 
     <a href="netvista.dot11_phy_type">DOT11_PHY_TYPE</a> enumerator value.


### -field bHardwarePhyState

A Boolean value that specifies the hardware power state of the PHY. If <b>TRUE</b>, the hardware power
      state is enabled. If <b>FALSE</b>, the hardware power state is disabled.

For more information about the PHY's hardware power state, see 
      <a href="netvista.oid_dot11_hardware_phy_state">
      OID_DOT11_HARDWARE_PHY_STATE</a>.

<div class="alert"><b>Note</b>  Whenever the PHY's hardware power state changes, the miniport driver must make an 
      <a href="netvista.ndis_status_dot11_phy_state_changed">
      NDIS_STATUS_DOT11_PHY_STATE_CHANGED</a> media-specific status indication.</div>
<div> </div>

### -field bSoftwarePhyState

A Boolean value that specifies the software power state of the PHY. If <b>TRUE</b>, the software power
      state is enabled. If <b>FALSE</b>, the software power state is disabled.

For more information about the PHY's software power state, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569392">OID_DOT11_NIC_POWER_STATE</a>.

<div class="alert"><b>Note</b>  Whenever the PHY's software power state changes, the miniport driver must make an 
      <a href="netvista.ndis_status_dot11_phy_state_changed">
      NDIS_STATUS_DOT11_PHY_STATE_CHANGED</a> media-specific status indication.</div>
<div> </div>

### -field bCFPollable

A Boolean value that, if set to <b>TRUE</b>, indicates that the 802.11 station supports CF-Poll frames. For
      more information about CF-Poll frames, refer to Clause 9.4 of the IEEE 802.11-2012 standard.

This member is not applicable to the Extensible Access Point (ExtAP) operation mode and is ignored
      when the NIC is in the ExtAP mode.


### -field uMPDUMaxLength

The maximum length, in bytes, of a media access control (MAC) protocol data unit (MPDU) frame that
      the PHY can transmit or receive. For more information, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569387">OID_DOT11_MPDU_MAX_LENGTH</a>.

<div class="alert"><b>Note</b>  Whenever the PHY's software power state changes, the miniport driver must make an
      NDIS_STATUS_DOT11_MPDU_MAX_LENGTH_CHANGED media-specific status indication.</div>
<div> </div>

### -field TempType

The PHY's operating temperature range, defined through a 
      <a href="netvista.dot11_temp_type">DOT11_TEMP_TYPE</a> enumeration value.


### -field DiversitySupport

The PHY's type of antenna diversity, defined through a 
      <a href="netvista.dot11_diversity_support">DOT11_DIVERSITY_SUPPORT</a> enumeration
      value.


### -field HRDSSSAttributes

The PHY-specific attributes of a high-rate direct-sequence spread spectrum (HRDSS) PHY type. The
       miniport driver must use this member only if the 
       <b>PhyType</b> member is set to dot11_phy_type_hrdsss.


### -field OFDMAttributes

The PHY-specific attributes of an orthogonal frequency division multiplexing (OFDM) PHY type. The
       miniport driver must use this member only if the 
       <b>PhyType</b> member is set to dot11_phy_type_ofdm.


### -field ERPAttributes

The PHY-specific attributes of an extended-rate PHY (ERP) type. The miniport driver must use this
       member only if the 
       <b>PhyType</b> member is set to dot11_phy_type_erp.


### -field uNumberSupportedPowerLevels

The number of power levels within the 
      <b>TxPowerLevels</b> array. 
      <b>uNumOfSupportedPowerLevels</b> must have a value from 1 through 8.


### -field TxPowerLevels

An array of the supported transmit power levels in units of milliwatts (mWs). Each power level must
      be a value from 0 through 1000.


### -field uNumDataRateMappingEntries

The number of data rates within the 
      <b>DataRateMappingEntries</b> array.


### -field DataRateMappingEntries

An array of the data rates supported by the PHY. Each entry is formatted as a 
      <a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">
      DOT11_DATA_RATE_MAPPING_ENTRY</a> structure.


### -field SupportedDataRatesValue

An array of the following data rates supported by the PHY:

<ul>
<li>
The transmit data rates supported by the Physical Layer Convergence Procedure (PLCP) and Physical
        Media Dependent (PMD) sublayer of the PHY.

</li>
<li>
The receive data rates supported by the PLCP and PMD of the PHY.

</li>
</ul>
Each entry in the array is formatted as a DOT11_SUPPORTED_DATA_RATES_VALUE_V2 structure.


## -remarks
The 
    <a href="netvista.ndis_miniport_adapter_native_802_11_attributes">
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure contains a member (<b>pExtPhyAttributes</b>) that specifies the address of an array of DOT11_PHY_ATTRIBUTES structures. When
    the miniport driver calls 
    <a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>,
    the driver sets the 
    <i>MiniportAttributes</i> parameter to the address of driver-allocated block of memory which contains an
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the array of DOT11_PHY_ATTRIBUTES
    structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Ndis.h)</dt>
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
<a href="netvista.dot11_diversity_support">DOT11_DIVERSITY_SUPPORT</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_erp_phy_attributes.md">DOT11_ERP_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_hrdsss_phy_attributes.md">DOT11_HRDSSS_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_ofdm_phy_attributes.md">DOT11_OFDM_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.dot11_temp_type">DOT11_TEMP_TYPE</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">DOT11_DATA_RATE_MAPPING_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569370">OID_DOT11_HARDWARE_PHY_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569392">OID_DOT11_NIC_POWER_STATE</a>
</dt>
<dt>
<a href="netvista.dot11_phy_type">DOT11_PHY_TYPE</a>
</dt>
<dt>
<a href="netvista.dot11_supported_data_rates_value_v2">
   DOT11_SUPPORTED_DATA_RATES_VALUE_V2</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_adapter_native_802_11_attributes">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_PHY_ATTRIBUTES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
