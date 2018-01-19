---
UID : NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
title : D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
author : windows-driver-content
description : Contains values for alpha fill modes.
old-location : display\d3d12ddi_video_process_alpha_fill_mode.htm
old-project : display
ms.assetid : 74F07876-5502-4B57-9128-624F6066AF5B
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020, D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
req.alt-loc : D3d12umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020
---

# D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 Enumeration
Contains values for alpha fill modes.

## Syntax
````
typedef enum D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020 { 
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_OPAQUE         = 0,
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_BACKGROUND     = 1,
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_DESTINATION    = 2,
  D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_SOURCE_STREAM  = 3
} D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020;
````

## Constants

<table>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_BACKGROUND</td>
<td>Alpha values inside the target rectangle are set to the alpha value specified in the background color.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_DESTINATION</td>
<td>Existing alpha values remain unchanged in the output surface.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_OPAQUE</td>
<td>Alpha values inside the target rectangle are set to opaque.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_0020_SOURCE_STREAM</td>
<td>Alpha values are taken from an input stream, scaled, and copied to the corresponding destination rectangle for that stream. The input stream is specified in the <b>AlphaFillModeSourceStreamIndex</b> member of the <b>D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_PARAMETERS</b> structure. If the input stream does not have alpha data, the video processor sets the alpha values in the target rectangle to opaque. If the input stream is disabled or the source rectangle is empty, the alpha values in the target rectangle are not modified.</td>
</tr>
</table>

## Remarks

The alpha fill mode is used in <b>D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_PARAMETERS</b>.  The <b>D3D12DDI_VIDEO_PROCESS_ALPHA_FILL_MODE_OPAQUE</b> flag is always supported.  The background, destination, and source stream modes are only supported when the driver reports <b>D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAG_ALPHA_FILL</b>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |