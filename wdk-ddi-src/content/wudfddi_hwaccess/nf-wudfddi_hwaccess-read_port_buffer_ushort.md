---
UID: NF.wudfddi_hwaccess.READ_PORT_BUFFER_USHORT
title: READ_PORT_BUFFER_USHORT function
author: windows-driver-content
description: The READ_PORT_BUFFER_USHORT function reads a number of USHORT values from the specified port address into a buffer.
old-location: wdf\read_port_buffer_ushort.htm
old-project: wdf
ms.assetid: 1707617F-3EFC-41AA-BE06-72CA254EEBDA
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: READ_PORT_BUFFER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi_hwaccess.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: READ_PORT_BUFFER_USHORT
req.alt-loc: Wudfddi_hwaccess.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# READ_PORT_BUFFER_USHORT function



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_PORT_BUFFER_USHORT</b> function reads a number of USHORT values from the specified port address into a buffer.



## -syntax

````
void READ_PORT_BUFFER_USHORT(
  _In_  IWDFDevice3 *pDevice,
  _In_  PUSHORT     Port,
  _Out_ PUSHORT     Buffer,
  _In_  ULONG       Count 
);
````


## -parameters

### -param pDevice [in]

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


### -param Buffer [out]

A pointer to a buffer into which an array of USHORT values is read.


### -param Count  [in]

Specifies the number of USHORT values to be read into the buffer.


## -returns
This function does not return a value.


## -remarks
For more information, see <a href="wdf.reading_and_writing_to_device_registers_in_umdf_1_x_drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.


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
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi_hwaccess.h</dt>
</dl>
</td>
</tr>
</table>