---
UID: NF.wdm.WRITE_PORT_ULONG~r3
title: WRITE_PORT_ULONG function
author: windows-driver-content
description: The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address.
old-location: kernel\write_port_ulong.htm
old-project: kernel
ms.assetid: fe7c8a20-dadb-4c8d-b208-8fbbf8c719a6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WRITE_PORT_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WRITE_PORT_ULONG
req.alt-loc: Hal.lib,Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
req.product: Windows 10 or later.
---

# WRITE_PORT_ULONG function



## -description
The <b>WRITE_PORT_ULONG</b> routine writes a ULONG value to the specified port address.



## -syntax

````
 VOID WRITE_PORT_ULONG(
  _In_ PULONG Port,
  _In_ ULONG  Value
);
````


## -parameters

### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Value [in]

Specifies a ULONG value to be written to the port. 


## -returns
None


## -remarks
Callers of <b>WRITE_PORT_ULONG</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.


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
Library

</th>
<td width="70%">
<dl>
<dt>Hal.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level (see Remarks section)

</td>
</tr>
</table>