---
UID: NS.NTDDRILAPITYPES.RILEMERGENCYNUMBER
title: RILEMERGENCYNUMBER
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumber.htm
old-project: NetVista
ms.assetid: 1725c893-1c36-40d2-99d7-e163020fc4fc
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILEMERGENCYNUMBER, *LPRILEMERGENCYNUMBER, LPRILEMERGENCYNUMBER, RILEMERGENCYNUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILEMERGENCYNUMBER
req.alt-loc: ntddrilapitypes.h
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

# RILEMERGENCYNUMBER structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILEMERGENCYNUMBER {
  DWORD     cbSize;
  DWORD     dwParams;
  DWORD     dwExecutor;
  HUICCAPP  hUiccApp;
  DWORD     dwCategory;
  WCHAR [8] wszEmergencyNumber;
} RILEMERGENCYNUMBER, RILEMERGENCYNUMBER;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwCategory


### -field wszEmergencyNumber


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>