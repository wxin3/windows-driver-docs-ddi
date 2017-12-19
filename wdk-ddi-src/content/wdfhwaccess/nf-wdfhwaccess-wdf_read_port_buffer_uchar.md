---
UID: NF.wdfhwaccess.WDF_READ_PORT_BUFFER_UCHAR
title: WDF_READ_PORT_BUFFER_UCHAR function
author: windows-driver-content
description: The WDF_READ_PORT_BUFFER_UCHAR function reads a number of bytes from the specified port address into a buffer.
old-location: wdf\wdf_read_port_buffer_uchar.htm
old-project: wdf
ms.assetid: 1A205DD3-FCE2-4EA1-A6B3-CE60300EC651
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WDF_READ_PORT_BUFFER_UCHAR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WDF_READ_PORT_BUFFER_UCHAR
req.alt-loc: Wdfhwaccess.h
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

# WDF_READ_PORT_BUFFER_UCHAR function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_PORT_BUFFER_UCHAR</b> function reads a number of bytes from the specified port address into a buffer.



## -syntax

````
void WDF_READ_PORT_BUFFER_UCHAR(
  _In_  WDFDEVICE Device,
  _In_  PUCHAR    Port,
  _Out_ PUCHAR    Buffer,
  _In_  ULONG     Count 
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


### -param Buffer [out]

A pointer to a buffer into which an array of UCHAR values is read.


### -param Count  [in]

Specifies the number of bytes to be read into the buffer.


## -returns
This function does not return a value.


## -remarks


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
Minimum support

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfhwaccess.h</dt>
</dl>
</td>
</tr>
</table>