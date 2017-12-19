---
UID: NC.d3dkmddi.DXGKDDI_DESTROYOVERLAY
title: DXGKDDI_DESTROYOVERLAY
author: windows-driver-content
description: The DxgkDdiDestroyOverlay function disables overlay hardware and deletes the specified overlay handle.
old-location: display\dxgkddidestroyoverlay.htm
old-project: display
ms.assetid: ea4672a2-ba21-42d4-9ff3-4fa611f86c90
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiDestroyOverlay
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGKDDI_DESTROYOVERLAY callback



## -description
The <i>DxgkDdiDestroyOverlay</i> function disables overlay hardware and deletes the specified overlay handle.



## -prototype

````
DXGKDDI_DESTROYOVERLAY DxgkDdiDestroyOverlay;

NTSTATUS APIENTRY DxgkDdiDestroyOverlay(
  _In_ const HANDLE hOverlay
)
{ ... }
````


## -parameters

### -param hOverlay [in]

[in] A handle to the overlay to destroy. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="display.dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a> structure. 


## -returns
<i>DxgkDdiDestroyOverlay</i> returns STATUS_SUCCESS, or an appropriate error result if overlay hardware is not successfully disabled.


## -remarks
<i>DxgkDdiDestroyOverlay</i> should be made pageable.


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
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DESTROYOVERLAY callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
