---
UID: NF.wdm.ClfsLsnEqual
title: ClfsLsnEqual function
author: windows-driver-content
description: The ClfsLsnEqual routine determines whether two LSNs from the same stream are equal.
old-location: kernel\clfslsnequal.htm
old-project: kernel
ms.assetid: e154c9d5-a131-47db-b0fa-d51154637c56
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ClfsLsnEqual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsLsnEqual
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: Any level
req.product: Windows 10 or later.
---

# ClfsLsnEqual function



## -description
The <b>ClfsLsnEqual</b> routine determines whether two LSNs from the same stream are equal.



## -syntax

````
BOOLEAN ClfsLsnEqual(
  _In_ const CLFS_LSN *plsn1,
  _In_ const CLFS_LSN *plsn2
);
````


## -parameters

### -param plsn1 [in]

A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.


### -param plsn2 [in]

A pointer to a <a href="kernel.clfs_lsn">CLFS_LSN</a> structure that supplies the other LSN to be compared.


## -returns
<b>ClfsLsnEqual</b> returns <b>TRUE</b> if the two LSNs are equal; otherwise, it returns <b>FALSE</b>.


## -remarks
CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnEqual</b>.

LSNs from different streams are not comparable. Do not use <b>ClfsLsnEqual</b>, <a href="kernel.clfslsngreater">ClfsLsnGreater</a>, and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.


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
Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
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
<a href="kernel.clfslsngreater">ClfsLsnGreater</a>
</dt>
<dt>
<a href="kernel.clfslsnless">ClfsLsnLess</a>
</dt>
<dt>
<a href="kernel.clfslsnnull">ClfsLsnNull</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnEqual routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
