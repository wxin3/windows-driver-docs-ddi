---
UID: NF.ufxclient.UfxDevicePortDetectCompleteEx
title: UfxDevicePortDetectCompleteEx function
author: windows-driver-content
description: Notifies UFX about the port type that was detected, and optionally requests an action.
old-location: buses\ufxdeviceportdetectcompleteex.htm
old-project: UsbRef
ms.assetid: EB3A65B5-EB21-45CA-B26D-F57A28F9F2CB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UfxDevicePortDetectCompleteEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UfxDevicePortDetectCompleteEx
req.alt-loc: ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# UfxDevicePortDetectCompleteEx function



## -description
Notifies UFX about the port type that was detected, and optionally requests an action.



## -syntax

````
VOID UfxDevicePortDetectCompleteEx(
  [in] UFXDEVICE       UfxDevice,
  [in] USBFN_PORT_TYPE PortType,
  [in] USBFN_ACTION    Action
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="buses.ufxdevicecreate">UfxDeviceCreate</a>.


### -param PortType [in]

Contains an enumeration value of type <a href="buses.usbfn_port_type">USBFN_PORT_TYPE</a>.


### -param Action [in]

Contains an enumeration value of type <a href="buses.usbfn_action">USBFN_ACTION</a>.


## -returns
This method does not return a value.


## -remarks
The client driver calls <b>UfxDevicePortDetectCompleteEx</b> after port detection is complete, typically from its <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_port_detect.md">EVT_UFX_DEVICE_PORT_DETECT</a> callback function. On some platforms, UFX may use the reported port type to notify the battery manager of the maximum current it can draw from the USB port.

  
If the <i>Action</i> parameter is set to <b>UsbfnActionNoCad</b>, UFX does not notify the battery manager at all.


If the <i>Action</i> parameter is set to <b>UsbfnActionDetectProprietaryCharger</b>, UFX requests that the client driver initiate proprietary charger detection by calling the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_detect.md">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback function.


The following snippet shows how a client driver calls <b>UfxDevicePortDetectCompleteEx</b>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL

</td>
</tr>
</table>