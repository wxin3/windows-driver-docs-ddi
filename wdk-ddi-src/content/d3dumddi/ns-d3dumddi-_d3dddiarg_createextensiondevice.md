---
UID: NS.D3DUMDDI._D3DDDIARG_CREATEEXTENSIONDEVICE
title: _D3DDDIARG_CREATEEXTENSIONDEVICE
author: windows-driver-content
description: The D3DDDIARG_CREATEEXTENSIONDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) extension device to create.
old-location: display\d3dddiarg_createextensiondevice.htm
old-project: display
ms.assetid: 33076a24-8856-4533-b4ab-ec1d7bdb083d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDIARG_CREATEEXTENSIONDEVICE, D3DDDIARG_CREATEEXTENSIONDEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_CREATEEXTENSIONDEVICE
req.alt-loc: d3dumddi.h
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

# _D3DDDIARG_CREATEEXTENSIONDEVICE structure



## -description
The D3DDDIARG_CREATEEXTENSIONDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) extension device to create. 



## -syntax

````
typedef struct _D3DDDIARG_CREATEEXTENSIONDEVICE {
  const GUID          *pGuid;
  DXVADDI_PRIVATEDATA *pPrivate;
  HANDLE              hExtension;
} D3DDDIARG_CREATEEXTENSIONDEVICE;
````


## -struct-fields

### -field pGuid

[in] A pointer to the GUID that represents the DirectX VA extension type. The Microsoft Direct3D runtime calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function to query for the supported extension GUIDs.


### -field pPrivate

[in] A pointer to the <a href="display.dxvaddi_privatedata">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to create the extension device. 


### -field hExtension

[in/out] A handle to the extension device. The user-mode display driver must set this handle to a value that the Direct3D runtime can use to identify the extension device in subsequent calls.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a>
</dt>
<dt>
<a href="display.dxvaddi_privatedata">DXVADDI_PRIVATEDATA</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEEXTENSIONDEVICE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
