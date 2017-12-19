---
UID: NF.hwnclx.HwNProcessAddDevicePostDeviceCreate
title: HwNProcessAddDevicePostDeviceCreate function
author: windows-driver-content
description: Creates I/O queues. It should be called after the client driver’s EVT_WDF_DRIVER_DEVICE_ADD callback function is invoked and the device object has been created.
old-location: gpiobtn\hwnprocessadddevicepostdevicecreate.htm
old-project: gpiobtn
ms.assetid: 907cdeac-e2f0-48fa-bbf0-082c0fce6401
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: HwNProcessAddDevicePostDeviceCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwNProcessAddDevicePostDeviceCreate
req.alt-loc: Mshwnclxstub.lib,Mshwnclxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mshwnclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# HwNProcessAddDevicePostDeviceCreate function



## -description

			
             Creates I/O queues. It should be called after the client driver’s <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a> callback function is invoked and the device object has been created. 



## -syntax

````
FORCEINLINE NTSTATUS  HwNProcessAddDevicePostDeviceCreate(
  _In_ WDFDRIVER  Driver,
  _In_ WDFDEVICE  Device,
  _In_ LPGUID     DeviceGuid
);
````


## -parameters

### -param Driver [in]

Handle to the client drivers framework driver object. 


### -param Device [in]

Handle to the framework device object. 


### -param DeviceGuid [in]

Pointer to the GUID for the client driver. Valid values are defined in Hwn.h, which ships with Window SDK.


## -returns
Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

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
Header

</th>
<td width="70%">
<dl>
<dt>Hwnclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Mshwnclxstub.lib</dt>
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
<dt><a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a></dt>
<dt>
<a href="gpiobtn.hardware_notifications_reference">Hardware notifications reference</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HwNProcessAddDevicePostDeviceCreate function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
