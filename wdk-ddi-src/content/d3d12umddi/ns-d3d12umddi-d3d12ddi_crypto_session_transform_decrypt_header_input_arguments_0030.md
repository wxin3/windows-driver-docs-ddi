---
UID: NS.D3D12UMDDI.D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
title: D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
author: windows-driver-content
description: Crypto session transform decrypt header input arguments.
old-location: display\d3d12ddi-crypto-session-transform-decrypt-header-input-arguments-0030.htm
old-project: display
ms.assetid: 49367166-11bd-4a4e-aa47-e91dbe9a3df8
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030
req.alt-loc: d3d12umddi.h
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

# D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030 structure



## -description
Crypto session transform decrypt header input arguments.



## -syntax

````
typedef struct _D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030 {
  BOOL           Enable;
  const void *   pSliceHeaders;
  UINT64         SliceHeadersSize;
  const DWORD *  pSliceHeadersOffsets;
  UINT64         SliceHeaderCount;
  const void *   pContext;
  UINT64         ContextSize;
} D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030, D3D12DDI_CRYPTO_SESSION_TRANSFORM_DECRYPT_HEADER_INPUT_ARGUMENTS_0030;
````


## -struct-fields

### -field Enable

Enable.


### -field pSliceHeaders

Slice headers.


### -field SliceHeadersSize

Slice header size.


### -field pSliceHeadersOffsets

Slice header offsets.


### -field SliceHeaderCount

Slice header count.


### -field pContext

Context.


### -field ContextSize

Context size.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>