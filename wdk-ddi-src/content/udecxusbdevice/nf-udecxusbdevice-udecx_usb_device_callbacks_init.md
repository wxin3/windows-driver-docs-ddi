---
UID: NF.udecxusbdevice.UDECX_USB_DEVICE_CALLBACKS_INIT
title: UDECX_USB_DEVICE_CALLBACKS_INIT function
author: windows-driver-content
description: Initializes a UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure before a UdecxUsbDeviceCreate call.
old-location: buses\udecx_usb_device_callbacks_init.htm
old-project: UsbRef
ms.assetid: ACBF5E07-9F36-4DF9-B72B-1BF159CE27A7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: UDECX_USB_DEVICE_CALLBACKS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UDECX_USB_DEVICE_CALLBACKS_INIT
req.alt-loc: Udecxstub.lib,Udecxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UDECX_USB_DEVICE_CALLBACKS_INIT function



## -description
Initializes a <a href="buses.udecx_usb_device_state_change_callbacks">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure before a <a href="buses.udecxusbdevicecreate">UdecxUsbDeviceCreate</a> call.



## -syntax

````
FORCEINLINE void UDECX_USB_DEVICE_CALLBACKS_INIT(
  _Out_ PUDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS Callbacks
);
````


## -parameters

### -param Callbacks [out]

A pointer to a <a href="buses.udecx_usb_device_state_change_callbacks">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure to initialize.


## -returns
This method does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>UdecxUsbDevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Udecxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.udecxusbdevicecreate">UdecxUsbDeviceCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UDECX_USB_DEVICE_CALLBACKS_INIT method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
