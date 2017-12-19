---
UID: NF.wdm.IoSetNextIrpStackLocation
title: IoSetNextIrpStackLocation function
author: windows-driver-content
description: The IoSetNextIrpStackLocation routine sets the IRP stack location in a driver-allocated IRP to that of the caller.
old-location: kernel\iosetnextirpstacklocation.htm
old-project: kernel
ms.assetid: 39a0b4d3-691f-45ca-a616-f3e123026776
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IoSetNextIrpStackLocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetNextIrpStackLocation
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# IoSetNextIrpStackLocation function



## -description
The <b>IoSetNextIrpStackLocation</b> routine sets the IRP stack location in a driver-allocated IRP to that of the caller.



## -syntax

````
VOID IoSetNextIrpStackLocation(
  _Inout_ PIRP Irp
);
````


## -parameters

### -param Irp [in, out]

Pointer to the IRP whose stack location is to be set. 


## -returns
None


## -remarks
In general, this routine is seldom used by drivers. It is primarily used by drivers that require their own stack location in an IRP that they have allocated, on their own, to send to another driver.

<b>IoSetNextIrpStackLocation</b> is generally not needed because either:

The driver received the IRP it is passing from another, higher-level driver, and so it already owns a stack location,

Or, the driver allocated the IRP but does not need its own stack location because it can keep everything that it needs in a context block whose address can be passed to its <i>IoCompletion</i> routine.

Care should be taken if this routine is called, especially when allocating the IRP with <b>IoAllocateIrp</b> or <b>IoMakeAssociatedIrp</b>. The writer of the allocating driver must remember that a caller-specific stack location is not included in the number of stack locations required by the lower-level drivers to which it sends IRPs with <b>IoCallDriver</b>. A driver must explicitly specify a stack location for itself in its call to <b>IoAllocateIrp</b> or <b>IoMakeAssociatedIrp</b> if it calls <b>IoSetNextIrpStackLocation</b> with the IRP returned by either routine.

A driver cannot call <b>IoSetNextIrpStackLocation</b> with any IRP it allocates by calling <b>IoBuildAsynchronousFsdRequest</b>, <b>IoBuildDeviceIoControlRequest</b>, or <b>IoBuildSynchronousFsdRequest</b>. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_stack_location">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="kernel.ioallocateirp">IoAllocateIrp</a>
</dt>
<dt>
<a href="kernel.iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>
</dt>
<dt>
<a href="kernel.iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>
</dt>
<dt>
<a href="kernel.iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="kernel.iocalldriver">IoCallDriver</a>
</dt>
<dt>
<a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetNextIrpStackLocation routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
