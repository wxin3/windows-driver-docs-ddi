---
UID: NC.wdfdmaenabler.EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP
title: EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP
author: windows-driver-content
description: A driver's EvtDmaEnablerSelfManagedIoStop event callback function stops a DMA device's self-managed I/O operations.
old-location: wdf\evtdmaenablerselfmanagediostop.htm
old-project: wdf
ms.assetid: b334588a-7a92-4542-8f45-13c363ce22f0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS, PWDF_REMOVE_LOCK_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: EvtDmaEnablerSelfManagedIoStop
req.alt-loc: WdfDmaEnabler.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP callback



## -description
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDmaEnablerSelfManagedIoStop</i> event callback function stops a DMA device's self-managed I/O operations.



## -prototype

````
EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP EvtDmaEnablerSelfManagedIoStop;

NTSTATUS EvtDmaEnablerSelfManagedIoStop(
  _In_ WDFDMAENABLER DmaEnabler
)
{ ... }
````


## -parameters

### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns
<i>EvtDmaEnablerSelfManagedIoStop</i> must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 


## -remarks
To register an <i>EvtDmaEnablerSelfManagedIoStop</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerSelfManagedIoStop</i> callback function, see <a href="wdf.supporting_power_management_for_dma_devices">Supporting Power Management for DMA Devices</a>.

To define an <i>EvtDmaEnablerSelfManagedIoStop</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDmaEnablerSelfManagedIoStop</i> callback function that is named <i>MyDmaEnablerSelfManagedIoStop</i>, use the <b>EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP</b> function type is defined in the WdfDmaEnabler.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
<dt>WdfDmaEnabler.h (include Wdf.h)</dt>
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
<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start.md">EvtDmaEnablerSelfManagedIoStart</a>
</dt>
<dt>
<a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>
</dt>
<dt>
<a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
