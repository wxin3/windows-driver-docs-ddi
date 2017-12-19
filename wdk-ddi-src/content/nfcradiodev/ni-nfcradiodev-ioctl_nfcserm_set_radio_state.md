---
UID: NI.nfcradiodev.IOCTL_NFCSERM_SET_RADIO_STATE
title: IOCTL_NFCSERM_SET_RADIO_STATE
author: windows-driver-content
description: This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcserm_set_radio_state.htm
old-project: nfpdrivers
ms.assetid: 721AE7FE-927C-4EBA-B33D-C5A5A986951C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NFC_CX_RF_DISCOVERY_CONFIG, NFC_CX_RF_DISCOVERY_CONFIG, PNFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcradiodev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFCSERM_SET_RADIO_STATE
req.alt-loc: nfcradiodev.h
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
---

# IOCTL_NFCSERM_SET_RADIO_STATE IOCTL



## -description
This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.



## -ioctlparameters

### -input-buffer

<a href="nfpdrivers._nfcrm_set_radio_state_"> NFCRM_SET_RADIO_STATE structure</a>



### -input-buffer-length
sizeof(NFCRM_SET_RADIO_STATE)


### -output-buffer
None


### -output-buffer-length
None


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Nfcradiodev.h</dt>
</dl>
</td>
</tr>
</table>