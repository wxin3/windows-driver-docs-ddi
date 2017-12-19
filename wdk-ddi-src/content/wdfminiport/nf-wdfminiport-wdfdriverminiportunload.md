---
UID: NF.wdfminiport.WdfDriverMiniportUnload
title: WdfDriverMiniportUnload function
author: windows-driver-content
description: The WdfDriverMiniportUnload method deletes a specified miniport driver's framework driver object.
old-location: wdf\wdfdriverminiportunload.htm
old-project: wdf
ms.assetid: 57220a12-e53d-482a-afb6-09bfbbf0d870
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfDriverMiniportUnload
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfminiport.h
req.include-header: Wdfminiport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDriverMiniportUnload
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDriverMiniportUnload function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDriverMiniportUnload</b> method deletes a specified miniport driver's framework driver object.



## -syntax

````
VOID WdfDriverMiniportUnload(
  _In_ WDFDRIVER Driver
);
````


## -parameters

### -param Driver [in]

A handle to the driver's framework driver object that the driver obtained from a previous call to <a href="wdf.wdfdrivercreate">WdfDriverCreate</a> or <a href="wdf.wdfgetdriver">WdfGetDriver</a>.


## -returns
None


## -remarks
A miniport driver calls the <b>WdfDriverMiniportUnload</b> method when the miniport driver is about to be unloaded. The method calls the driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> event callback function and deletes the driver's framework driver object.

Typically, a miniport driver calls <b>WdfDriverMiniportUnload</b> from within a driver-supplied unload routine that is defined by the port driver's architecture.

For more information about miniport drivers, see <a href="wdf.creating_kmdf_miniport_drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.

The following code example deletes a specified miniport driver's framework driver object.


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
<dt>Wdfminiport.h (include Wdfminiport.h)</dt>
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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a>
</dt>
<dt>
<a href="wdf.wdfdeviceminiportcreate">WdfDeviceMiniportCreate</a>
</dt>
<dt>
<a href="wdf.wdfdrivercreate">WdfDriverCreate</a>
</dt>
<dt>
<a href="wdf.wdfgetdriver">WdfGetDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDriverMiniportUnload method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
