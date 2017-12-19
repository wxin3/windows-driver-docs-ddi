---
UID: NI.bthhfpddi.IOCTL_BTHHFP_MIC_SET_VOLUME
title: IOCTL_BTHHFP_MIC_SET_VOLUME
author: windows-driver-content
description: The IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL sets the volume level of the microphone for the Bluetooth device.
old-location: audio\ioctl_bthhfp_mic_set_volume.htm
old-project: audio
ms.assetid: 438BB68B-9E09-4033-B38E-C1C28D00D43C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTHHFP_MIC_SET_VOLUME
req.alt-loc: Bthhfpddi.h
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

# IOCTL_BTHHFP_MIC_SET_VOLUME IOCTL



## -description
The <b>IOCTL_BTHHFP_MIC_SET_VOLUME</b> 
   IOCTL sets the  volume level of the microphone for the Bluetooth device.



## -ioctlparameters

### -input-buffer
A LONG that represents the volume level in 1/65536 decibels.


### -input-buffer-length
The size of a LONG.


### -output-buffer
N/A


### -output-buffer-length
N/A


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
N/A


## -remarks
The audio driver sends this request when handling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a> node in the KS topology of the microphone path. The request’s input parameter is the same as the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property value.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthhfpddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.bluetooth_hfp_ddi_ioctls">Bluetooth HFP DDI IOCTLs</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_MIC_SET_VOLUME control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
