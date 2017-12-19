---
UID: NF.ntintsafe.RtlShortMult
title: RtlShortMult function
author: windows-driver-content
description: Multiplies one value of type SHORT by another.
old-location: kernel\rtlshortmult.htm
old-project: kernel
ms.assetid: 15DCCCF1-72B1-4944-9BF0-ACAF1DEB9243
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlShortMult
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlShortMult
req.alt-loc: Ntintsafe.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# RtlShortMult function



## -description
Multiplies one value of type <b>SHORT</b> by another.



## -syntax

````
NTSTATUS RtlShortMult(
  _In_  SHORT sMultiplicand,
  _In_  SHORT sMultiplier,
  _Out_ SHORT *psResult
);
````


## -parameters

### -param sMultiplicand [in]

The value to be multiplied by <i>sMultiplier</i>.


### -param sMultiplier [in]

The value by which to multiply <i>sMultiplicand</i>.


### -param psResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>