---
UID: NF.wdm.InsertHeadList
title: InsertHeadList function
author: windows-driver-content
description: The InsertHeadList routine inserts an entry at the head of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\insertheadlist.htm
old-project: kernel
ms.assetid: c3ad9d93-93e1-406b-9a58-26dcbf428b50
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: InsertHeadList
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
req.alt-api: InsertHeadList
req.alt-loc: Wdm.h
req.ddi-compliance: IoAllocateFree, IoReuseIrp, MarkingQueuedIrps, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (See Remarks section)
req.product: Windows 10 or later.
---

# InsertHeadList function



## -description
The <b>InsertHeadList</b> routine inserts an entry at the head of a doubly linked list of <a href="kernel.list_entry">LIST_ENTRY</a> structures.



## -syntax

````
VOID InsertHeadList(
  _Inout_ PLIST_ENTRY ListHead,
  _Inout_ PLIST_ENTRY Entry
);
````


## -parameters

### -param ListHead [in, out]

Pointer to the <a href="kernel.list_entry">LIST_ENTRY</a> structure that represents the head of the list.


### -param Entry [in, out]

Pointer to a <a href="kernel.list_entry">LIST_ENTRY</a> structure that represents the entry to be inserted into the list. 


## -returns
None


## -remarks
<b>InsertHeadList</b> updates <i>ListHead</i>-&gt;<b>Flink</b> to point to <i>Entry</i>. It updates <i>Entry</i>-&gt;<b>Flink</b> to point to the old first entry in the list, and sets <i>Entry</i>-&gt;<b>Blink</b> to <i>ListHead</i>. The <b>Blink</b> field of the original first entry is also updated to point to <i>Entry</i>.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InsertHeadList</b> can be running at any IRQL. If <b>InsertHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.


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
Any level (See Remarks section)

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_ioallocatefree">IoAllocateFree</a>, <a href="devtest.wdm_ioreuseirp">IoReuseIrp</a>, <a href="devtest.wdm_markingqueuedirps">MarkingQueuedIrps</a>, <a href="devtest.wdm_removelockcheck">RemoveLockCheck</a>, <a href="devtest.wdm_removelockforward">RemoveLockForward</a>, <a href="devtest.wdm_removelockforward2">RemoveLockForward2</a>, <a href="devtest.wdm_removelockforwarddevicecontrol">RemoveLockForwardDeviceControl</a>, <a href="devtest.wdm_removelockforwarddevicecontrol2">RemoveLockForwardDeviceControl2</a>, <a href="devtest.wdm_removelockforwarddevicecontrolinternal">RemoveLockForwardDeviceControlInternal</a>, <a href="devtest.wdm_removelockforwarddevicecontrolinternal2">RemoveLockForwardDeviceControlInternal2</a>, <a href="devtest.wdm_removelockforwardread">RemoveLockForwardRead</a>, <a href="devtest.wdm_removelockforwardread2">RemoveLockForwardRead2</a>, <a href="devtest.wdm_removelockforwardwrite">RemoveLockForwardWrite</a>, <a href="devtest.wdm_removelockforwardwrite2">RemoveLockForwardWrite2</a>, <a href="devtest.wdm_removelockrelease2">RemoveLockRelease2</a>, <a href="devtest.wdm_removelockreleasecleanup">RemoveLockReleaseCleanup</a>, <a href="devtest.wdm_removelockreleaseclose">RemoveLockReleaseClose</a>, <a href="devtest.wdm_removelockreleasecreate">RemoveLockReleaseCreate</a>, <a href="devtest.wdm_removelockreleasedevicecontrol">RemoveLockReleaseDeviceControl</a>, <a href="devtest.wdm_removelockreleaseinternaldevicecontrol">RemoveLockReleaseInternalDeviceControl</a>, <a href="devtest.wdm_removelockreleasepower">RemoveLockReleasePower</a>, <a href="devtest.wdm_removelockreleaseread">RemoveLockReleaseRead</a>, <a href="devtest.wdm_removelockreleaseshutdown">RemoveLockReleaseShutdown</a>, <a href="devtest.wdm_removelockreleasesystemcontrol">RemoveLockReleaseSystemControl</a>, <a href="devtest.wdm_removelockreleasewrite">RemoveLockReleaseWrite</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exinterlockedinsertheadlist">ExInterlockedInsertHeadList</a>
</dt>
<dt>
<a href="kernel.initializelisthead">InitializeListHead</a>
</dt>
<dt>
<a href="kernel.inserttaillist">InsertTailList</a>
</dt>
<dt>
<a href="kernel.islistempty">IsListEmpty</a>
</dt>
<dt>
<a href="kernel.removeheadlist">RemoveHeadList</a>
</dt>
<dt>
<a href="kernel.removetaillist">RemoveTailList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InsertHeadList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
