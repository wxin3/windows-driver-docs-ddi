---
UID: NE.urstypes._URS_ROLE
title: _URS_ROLE
author: windows-driver-content
description: Defines values for roles supported by a USB dual-role controller.
old-location: buses\urs_role.htm
old-project: UsbRef
ms.assetid: A1ED9DBD-67FF-4AE7-8E5E-016C2C89A79E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _URS_ROLE, PURS_ROLE, URS_ROLE, *PURS_ROLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: urstypes.h
req.include-header: Urstypes.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: URS_ROLE, *PURS_ROLE
req.alt-loc: Urstypes.h
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

# _URS_ROLE enumeration



## -description
Defines values for roles supported by a USB dual-role controller.



## -syntax

````
typedef enum _URS_ROLE { 
  UrsRoleNone      = 0,
  UrsRoleHost,
  UrsRoleFunction
} URS_ROLE, *PURS_ROLE;
````


## -enum-fields

### -field UrsRoleNone

Internal use only. Must be 0.


### -field UrsRoleHost

Indicates the host role of the controller.


### -field UrsRoleFunction

Indicates the function role of the controller.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Urstypes.h (include Urstypes.h)</dt>
</dl>
</td>
</tr>
</table>