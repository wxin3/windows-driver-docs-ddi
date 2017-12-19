---
UID: NF.ntifs.CcUnpinData
title: CcUnpinData function
author: windows-driver-content
description: The CcUnpinData routine releases cached file data that was mapped or pinned by an earlier call to CcMapData, CcPinRead, or CcPreparePinWrite.
old-location: ifsk\ccunpindata.htm
old-project: ifsk
ms.assetid: a06bbe25-9841-4aeb-9d51-257dd1472027
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: CcUnpinData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcUnpinData
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
---

# CcUnpinData function



## -description
The <b>CcUnpinData</b> routine releases cached file data that was mapped or pinned by an earlier call to <a href="ifsk.ccmapdata">CcMapData</a>, <a href="ifsk.ccpinread">CcPinRead</a>, or <a href="ifsk.ccpreparepinwrite">CcPreparePinWrite</a>.



## -syntax

````
VOID CcUnpinData(
  _In_ PVOID Bcb
);
````


## -parameters

### -param Bcb [in]

Pointer to a buffer control block (BCB) for the data to be released.


## -returns
None


## -remarks
<b>CcUnpinData</b> frees the BCB and performs any other necessary cleanup.

Every successful call to <a href="ifsk.ccmapdata">CcMapData</a>, <a href="ifsk.ccpinread">CcPinRead</a>, or <a href="ifsk.ccpreparepinwrite">CcPreparePinWrite</a> must be matched by a subsequent call to <b>CcUnpinData</b>. 

BCBs that have been modified by <a href="ifsk.ccsetbcbownerpointer">CcSetBcbOwnerPointer</a> cannot be unpinned by calling <b>CcUnpinData</b>. <a href="ifsk.ccunpindataforthread">CcUnpinDataForThread</a> must be called instead.


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
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="ifsk.ccmapdata">CcMapData</a>
</dt>
<dt>
<a href="ifsk.ccpinread">CcPinRead</a>
</dt>
<dt>
<a href="ifsk.ccpreparepinwrite">CcPreparePinWrite</a>
</dt>
<dt>
<a href="ifsk.ccsetbcbownerpointer">CcSetBcbOwnerPointer</a>
</dt>
<dt>
<a href="ifsk.ccunpindataforthread">CcUnpinDataForThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcUnpinData routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
