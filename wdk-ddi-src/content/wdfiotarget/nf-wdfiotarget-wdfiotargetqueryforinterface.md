---
UID: NF.wdfiotarget.WdfIoTargetQueryForInterface
title: WdfIoTargetQueryForInterface function
author: windows-driver-content
description: The WdfIoTargetQueryForInterface method obtains access to the GUID-identified, driver-defined interface of a remote I/O target.
old-location: wdf\wdfiotargetqueryforinterface.htm
old-project: wdf
ms.assetid: 213d0ee8-96f1-4927-be87-1b504b3f3478
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfIoTargetQueryForInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfIoTargetQueryForInterface
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfIoTargetQueryForInterface function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetQueryForInterface</b> method obtains access to the GUID-identified, driver-defined interface of a <a href="wdf.general_i_o_targets">remote I/O target</a>.



## -syntax

````
NTSTATUS WdfIoTargetQueryForInterface(
  _In_     WDFIOTARGET IoTarget,
  _In_     LPCGUID     InterfaceType,
  _Out_    PINTERFACE  Interface,
  _In_     USHORT      Size,
  _In_     USHORT      Version,
  _In_opt_ PVOID       InterfaceSpecificData
);
````


## -parameters

### -param IoTarget [in]

A handle to a remote I/O target object that was obtained from a previous call to <a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>.


### -param InterfaceType [in]

A pointer to a GUID that identifies the interface.


### -param Interface [out]

A pointer to a driver-allocated structure that receives the requested interface. This structure is defined by the driver that exports the requested interface and must begin with an <a href="kernel.interface">INTERFACE</a> structure.


### -param Size [in]

The size, in bytes, of the driver-allocated structure that <i>Interface</i> points to.


### -param Version [in]

The version number of the requested interface. The driver that exports the requested interface defines the format of this value.


### -param InterfaceSpecificData [in, optional]

Additional interface-specific information. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfIoTargetQueryForInterface</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>IoTarget</i>, <i>InterfaceType</i>, or <i>Interface</i> parameter is <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl> the framework could not allocate a request to send to another driver.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Your driver can call <b>WdfIoTargetQueryForInterface</b> to obtain access to a driver-defined interface that was created by a driver in a different driver stack. To access a driver-defined interface that was created by a driver that is in the same driver stack as your driver, your driver must call <a href="wdf.wdffdoqueryforinterface">WdfFdoQueryForInterface</a>.

Framework-based drivers define interfaces by calling <a href="wdf.wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>. For more information about driver-defined interfaces, see <a href="wdf.using_driver_defined_interfaces">Using Driver-Defined Interfaces</a>.

The following code example attempts to gain access to a specified remote I/O target's interface. GUID_RAWPDO_INTERFACE_STANDARD is the GUID that identifies the interface.


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
Header

</th>
<td width="70%">
<dl>
<dt>Wdfiotarget.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.interface">INTERFACE</a>
</dt>
<dt>
<a href="wdf.wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>
</dt>
<dt>
<a href="wdf.wdffdoqueryforinterface">WdfFdoQueryForInterface</a>
</dt>
<dt>
<a href="wdf.wdfiotargetcreate">WdfIoTargetCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetQueryForInterface method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
