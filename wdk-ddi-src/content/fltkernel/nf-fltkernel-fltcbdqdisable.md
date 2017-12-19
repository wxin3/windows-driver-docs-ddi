---
UID: NF.fltkernel.FltCbdqDisable
title: FltCbdqDisable function
author: windows-driver-content
description: FltCbdqDisable disables a minifilter driver's callback data queue.
old-location: ifsk\fltcbdqdisable.htm
old-project: ifsk
ms.assetid: 7024d611-533c-43d3-91cf-a678b8359793
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltCbdqDisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltCbdqDisable
req.alt-loc: fltkernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
---

# FltCbdqDisable function



## -description
<i>FltCbdqDisable</i> disables a minifilter driver's callback data queue. 



## -syntax

````
VOID FltCbdqDisable(
  _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq
);
````


## -parameters

### -param Cbdq [in, out]

Pointer to the callback data queue. 


## -returns
None 


## -remarks
<i>FltCbdqDisable</i> disables a callback data queue so that no more items can be added to it. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A minifilter driver normally calls <i>FltCbdqDisable</i> during instance teardown or minifilter driver unload. After calling this routine, the minifilter driver should empty, or <i>drain</i>, the queue. This can be done by calling <a href="ifsk.fltcbdqremovenextio">FltCbdqRemoveNextIo</a> repeatedly until no more items remain in the queue. 

See <a href="ifsk.fltcbdqinitialize">FltCbdqInitialize</a> for details on how to create a callback data queue. Use <a href="ifsk.fltcbdqinsertio">FltCbdqInsertIo</a> to add an I/O request to the queue. Use <a href="ifsk.fltcbdqremoveio">FltCbdqRemoveIo</a> to remove a particular I/O request from the queue, or <a href="ifsk.fltcbdqremovenextio">FltCbdqRemoveNextIo</a> to remove the next available I/O request.

To reenable the queue after disabling it, call <a href="ifsk.fltcbdqenable">FltCbdqEnable</a>. 

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="kernel.exinitializeresourcelite">resource variable</a>, the caller of <i>FltCbdqDisable</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL. 


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
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks section.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data_queue">FLT_CALLBACK_DATA_QUEUE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="ifsk.fltcbdqenable">FltCbdqEnable</a>
</dt>
<dt>
<a href="ifsk.fltcbdqinitialize">FltCbdqInitialize</a>
</dt>
<dt>
<a href="ifsk.fltcbdqinsertio">FltCbdqInsertIo</a>
</dt>
<dt>
<a href="ifsk.fltcbdqremoveio">FltCbdqRemoveIo</a>
</dt>
<dt>
<a href="ifsk.fltcbdqremovenextio">FltCbdqRemoveNextIo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCbdqDisable function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
