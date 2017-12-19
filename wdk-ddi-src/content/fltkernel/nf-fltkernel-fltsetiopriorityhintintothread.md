---
UID: NF.fltkernel.FltSetIoPriorityHintIntoThread
title: FltSetIoPriorityHintIntoThread function
author: windows-driver-content
description: The FltSetIoPriorityHintIntoThread routine is used by a minifilter driver to set the IO priority information in a thread.
old-location: ifsk\fltsetiopriorityhintintothread.htm
old-project: ifsk
ms.assetid: 924fadbe-2703-43f8-985c-db5a7bb960a6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltSetIoPriorityHintIntoThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltSetIoPriorityHintIntoThread
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
---

# FltSetIoPriorityHintIntoThread function



## -description
The <b>FltSetIoPriorityHintIntoThread</b> routine is used by a minifilter driver to set the IO priority information in a thread.



## -syntax

````
NTSTATUS FltSetIoPriorityHintIntoThread(
  _In_ PETHREAD         Thread,
  _In_ IO_PRIORITY_HINT PriorityHint
);
````


## -parameters

### -param Thread [in]

A pointer to the thread to modify. This parameter is required and cannot be <b>NULL</b>. 


### -param PriorityHint [in]

The  <a href="kernel.io_priority_hint">IO_PRIORITY_HINT</a> enumeration value to set for the thread information pointed to by <i>Thread</i>.


## -returns
If the IO Priority value passed to the <i>PriorityHint</i> parameter is successfully applied to the <i>Thread</i>, <b>FltSetIoPriorityHintIntoThread</b> returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>The value of the <i>PriorityHint</i> parameter is invalid. This is an error code. 

 


## -remarks
This routine is NONPAGED and can be called from paging IO paths.


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
Version

</th>
<td width="70%">
Available in starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.fltapplypriorityinfothread">FltApplyPriorityInfoThread</a>
</dt>
<dt>
<a href="ifsk.fltgetiopriorityhint">FltGetIoPriorityHint</a>
</dt>
<dt>
<a href="ifsk.fltgetiopriorityhintfromcallbackdata">FltGetIoPriorityHintFromCallbackData</a>
</dt>
<dt>
<a href="ifsk.fltgetiopriorityhintfromfileobject">FltGetIoPriorityHintFromFileObject</a>
</dt>
<dt>
<a href="ifsk.fltgetiopriorityhintfromthread">FltGetIoPriorityHintFromThread</a>
</dt>
<dt>
<a href="ifsk.fltretrieveiopriorityinfo">FltRetrieveIoPriorityInfo</a>
</dt>
<dt>
<a href="ifsk.fltsetiopriorityhintintocallbackdata">FltSetIoPriorityHintIntoCallbackData</a>
</dt>
<dt>
<a href="ifsk.fltsetiopriorityhintintofileobject">FltSetIoPriorityHintIntoFileObject</a>
</dt>
<dt>
<a href="kernel.io_priority_hint">IO_PRIORITY_HINT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetIoPriorityHintIntoThread routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
