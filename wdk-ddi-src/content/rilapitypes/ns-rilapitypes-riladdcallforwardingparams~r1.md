---
UID: NS.RILAPITYPES.RILADDCALLFORWARDINGPARAMS~R1
title: RILADDCALLFORWARDINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladdcallforwardingparams_2.htm
old-project: NetVista
ms.assetid: 96adad09-fe54-469a-b57d-4df68750968c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILADDCALLFORWARDINGPARAMS, *LPRILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS
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
req.alt-api: RILADDCALLFORWARDINGPARAMS
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

# RILADDCALLFORWARDINGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILADDCALLFORWARDINGPARAMS {
  DWORD                            dwExecutor;
  RILCALLFORWARDINGSETTINGSREASON  dwReason;
  RILCALLFORWARDINGSETTINGS        rcfsSettings;
} RILADDCALLFORWARDINGPARAMS, RILADDCALLFORWARDINGPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwReason


### -field rcfsSettings


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