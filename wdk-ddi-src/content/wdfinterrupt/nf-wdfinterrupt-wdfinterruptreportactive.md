---
UID: NF.wdfinterrupt.WdfInterruptReportActive
title: WdfInterruptReportActive function
author: windows-driver-content
description: The WdfInterruptReportActive informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines.
old-location: wdf\wdfinterruptreportactive.htm
old-project: wdf
ms.assetid: 9A7B4181-0592-4C40-BC5A-99AFFA57846C
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfInterruptReportActive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WdfInterruptReportActive
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfInterruptReportActive function



## -description
<p class="CCE_Message">[Applies to KMDF only]


   
  The <b>WdfInterruptReportActive</b> informs the system that the interrupt is active and the driver is ready to process interrupt requests on the associated lines.



## -syntax

````
void WdfInterruptReportActive(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters

### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns
This method does not return a value.


## -remarks
Only drivers that implement functional state power management call <b>WdfInterruptReportActive</b>.

   

A driver does not need to call <b>WdfInterruptReportActive</b> immediately after creating an interrupt.  The driver should only call <b>WdfInterruptReportActive</b> after having previously called <a href="wdf.wdfinterruptreportinactive">WdfInterruptReportInactive</a>.

Typically, a driver calls <b>WdfInterruptReportActive</b> from either its  <a href="kernel.componentactiveconditioncallback">ComponentActiveConditionCallback</a> routine, or from <a href="kernel.componentidlestatecallback">ComponentIdleStateCallback</a> when <i>State</i> is 0 (indicating the fully on F0 state).

If your driver calls this method on an operating system earlier than Windows 8, <a href="wdf.using_kmdf_verifier">the framework's verifier</a> reports an error.

For more information, see <a href="wdf.supporting_functional_power_states">Supporting Functional Power States</a>.

The following example shows how a driver might call <b>WdfInterruptReportActive</b> from the <a href="kernel.componentidlestatecallback">ComponentIdleStateCallback</a> routine of a KMDF driver. The driver registers a single component by calling <a href="wdf.wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.


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
Minimum support

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfinterrupt.h (include Wdf.h)</dt>
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
&lt;=DISPATCH_LEVEL

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
<a href="wdf.wdfinterruptreportinactive">WdfInterruptReportInactive</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptReportActive method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
