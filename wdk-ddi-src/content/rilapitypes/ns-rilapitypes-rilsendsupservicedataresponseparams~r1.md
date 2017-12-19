---
UID: NS.RILAPITYPES.RILSENDSUPSERVICEDATARESPONSEPARAMS~R1
title: RILSENDSUPSERVICEDATARESPONSEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendsupservicedataresponseparams_2.htm
old-project: NetVista
ms.assetid: 2b5ac749-9097-43bf-a0e6-a18374f15a86
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILSENDSUPSERVICEDATARESPONSEPARAMS, RILSENDSUPSERVICEDATARESPONSEPARAMS, *LPRILSENDSUPSERVICEDATARESPONSEPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDSUPSERVICEDATARESPONSEPARAMS
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILSENDSUPSERVICEDATARESPONSEPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSENDSUPSERVICEDATARESPONSEPARAMS {
  DWORD     dwExecutor;
  DWORD     dwDataSize;
  WCHAR [1] wszData;
} RILSENDSUPSERVICEDATARESPONSEPARAMS, RILSENDSUPSERVICEDATARESPONSEPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwDataSize


### -field wszData


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>