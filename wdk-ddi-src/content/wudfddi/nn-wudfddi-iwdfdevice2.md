---
UID : NN:wudfddi.IWDFDevice2
title : IWDFDevice2
author : windows-driver-content
description : Drivers obtain the IWDFDevice2 interface by calling IWDFDevice::QueryInterface.
old-location : wdf\iwdfdevice2.htm
old-project : wdf
ms.assetid : f4d3d2cf-8877-4071-8e75-f971803beca4
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.9
req.alt-api : IWDFDevice2
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---

# IWDFDevice2 interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

Drivers obtain the <b>IWDFDevice2</b> interface by calling <b>IWDFDevice::QueryInterface</b>.

## Methods

<p>The <b>IWDFDevice2</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IWDFDevice2.AssignS0IdleSettings](nf-wudfddi-iwdfdevice2-assigns0idlesettings.md) | The AssignS0IdleSettings method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state. |
| [wudfddi.IWDFDevice2.AssignSxWakeSettings](nf-wudfddi-iwdfdevice2-assignsxwakesettings.md) | The AssignSxWakeSettings method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state. |
| [wudfddi.IWDFDevice2.CreateRemoteInterface](nf-wudfddi-iwdfdevice2-createremoteinterface.md) | The CreateRemoteInterface method creates a remote interface object that represents a device interface. |
| [wudfddi.IWDFDevice2.CreateRemoteTarget](nf-wudfddi-iwdfdevice2-createremotetarget.md) | The CreateRemoteTarget method creates a remote target object that represents a remote I/O target. |
| [wudfddi.IWDFDevice2.CreateSymbolicLinkWithReferenceString](nf-wudfddi-iwdfdevice2-createsymboliclinkwithreferencestring.md) | TheCreateSymbolicLinkWithReferenceString method creates a symbolic link name, and optionally, a reference string, for a device. |
| [wudfddi.IWDFDevice2.GetDeviceStackIoTypePreference](nf-wudfddi-iwdfdevice2-getdevicestackiotypepreference.md) | The GetDeviceStackIoTypePreference method retrieves the buffer access methods that the framework is using for a device. |
| [wudfddi.IWDFDevice2.GetSystemPowerAction](nf-wudfddi-iwdfdevice2-getsystempoweraction.md) | The GetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer. |
| [wudfddi.IWDFDevice2.RegisterRemoteInterfaceNotification](nf-wudfddi-iwdfdevice2-registerremoteinterfacenotification.md) | The RegisterRemoteInterfaceNotification method registers a driver to receive a notification when a specified device interface becomes available. |
| [wudfddi.IWDFDevice2.ResumeIdle](nf-wudfddi-iwdfdevice2-resumeidle.md) | The ResumeIdle method informs the framework that the device is not in use and can be placed in a device low-power state if it remains idle. |
| [wudfddi.IWDFDevice2.StopIdle](nf-wudfddi-iwdfdevice2-stopidle.md) | The StopIdle method informs the framework that the device must be placed in its working (D0) power state. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |