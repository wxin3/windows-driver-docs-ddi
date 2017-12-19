---
UID: NF.wdm.PushEntryList
title: PushEntryList function
author: windows-driver-content
description: The PushEntryList routine inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\pushentrylist.htm
old-project: kernel
ms.assetid: 19f387d3-6c00-4c71-8114-61c53654613c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PushEntryList
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
req.alt-api: PushEntryList
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
req.irql: Any level (See Remarks section)
req.product: Windows 10 or later.
---

# PushEntryList function



## -description
The <b>PushEntryList</b> routine inserts an entry at the beginning of a singly linked list of <a href="kernel.single_list_entry">SINGLE_LIST_ENTRY</a> structures.



## -syntax

````
VOID PushEntryList(
  _Inout_ PSINGLE_LIST_ENTRY ListHead,
  _Inout_ PSINGLE_LIST_ENTRY Entry
);
````


## -parameters

### -param ListHead [in, out]

Pointer to the <a href="kernel.single_list_entry">SINGLE_LIST_ENTRY</a> structure that serves as the list header.


### -param Entry [in, out]

Pointer to SINGLE_LIST_ENTRY structure that represents the entry to be inserted on the list.


## -returns
None


## -remarks
<b>PushEntryList</b> sets <i>ListHead</i>-&gt;<b>Next</b> to <i>Entry</i>, and <i>Entry</i>-&gt;<b>Next</b> to point to the old first entry of the list.

For information about using this routine when implementing a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>PushEntryList</b> can be running at any IRQL. If <b>PushEntryList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.


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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exinterlockedpushentrylist">ExInterlockedPushEntryList</a>
</dt>
<dt>
<a href="kernel.popentrylist">PopEntryList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PushEntryList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
