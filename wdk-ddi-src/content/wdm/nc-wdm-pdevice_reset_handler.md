---
UID: NC:wdm.PDEVICE_RESET_HANDLER
title: PDEVICE_RESET_HANDLER
author: windows-driver-content
description: The DeviceReset routine is used to reset and recover a malfunctioning device.
old-location: kernel\devicereset.htm
old-project: kernel
ms.assetid: A5AA5E73-3DC1-4977-9B64-9E0FB3E6609E
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PDEVICE_RESET_HANDLER, ResetDevice, ResetDevice routine [Kernel-Mode Driver Architecture], kernel.devicereset, wdm/ResetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	ResetDevice
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PDEVICE_RESET_HANDLER callback


## -description


The <i>DeviceReset</i> routine is used to reset and recover a malfunctioning device.


## -parameters




### -param InterfaceContext [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939397">DEVICE_RESET_INTERFACE_STANDARD</a> structure for the interface.


### -param ResetType [in]

The type of reset being  requested. Set this parameter to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/dn939400">DEVICE_RESET_TYPE</a> enumeration values.

<ul>
<li><b>FunctionLevelDeviceReset</b>. Specify this value to request a function-level reset, which is restricted to a specific device.</li>
<li><b>PlatformLevelDeviceReset</b>. Specify this value to request a platform-level reset, which affects a specific device and all other devices that are connected to it via the same power rail or reset line.</li>
</ul>
For more information about how function-level and platform-level resets are implemented in the device stack, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a>.


### -param Flags [in]

Set to 0. Currently, no flags are defined for this routine.


### -param ResetParameters [in, optional]

If the caller is requesting a  function-level device reset, this optional parameter can point to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn939576">FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS</a> structure that specifies a callback routine that is called when the reset is completed.


## -returns



This routine returns STATUS_SUCCESS if the requested operation succeeds. Otherwise, it returns an appropriate an NTSTATUS error code. 




## -remarks



If a function driver detects that the device is not functioning correctly, it should first attempt a function-level reset. If a function-level reset does not fix the issue, then the driver can attempt a more invasive platform-level reset, but a platform-level reset should only be used as the final option.

For more information about function-level and platform-level resets, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
 

 

