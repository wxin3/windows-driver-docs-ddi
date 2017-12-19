---
UID: NF.wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can specify a configuration by using a URB.
old-location: wdf\wdf_usb_device_select_config_params_init_urb.htm
old-project: wdf
ms.assetid: 087888ce-e08a-4f9f-adac-419a638e65bd
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB
req.alt-loc: wdfusb.h
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

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</b> function initializes a <a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can specify a configuration by using a <a href="buses.urb">URB</a>. 



## -syntax

````
VOID WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB(
  _Out_ PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS Params,
  _In_  PURB                                 Urb
);
````


## -parameters

### -param Params [out]

A pointer to the driver's <a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.


### -param Urb [in]

A pointer to a <a href="buses.urb">URB</a> structure.


## -returns
None


## -remarks
The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</b> function zeros the <a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeUrb</b> and sets the <b>Types.Urb.Urb</b> member to the <i>Urb</i> pointer.

To initialize a <a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:


<a href="wdf.wdf_usb_device_select_config_params_init_deconfig">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>



<a href="wdf.wdf_usb_device_select_config_params_init_single_interface">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>



<a href="wdf.wdf_usb_device_select_config_params_init_multiple_interfaces">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>



<a href="wdf.wdf_usb_device_select_config_params_init_interfaces_descriptors">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>


<b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</b>


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.urb">URB</a>
</dt>
<dt>
<a href="wdf.wdf_usb_device_select_config_params">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
