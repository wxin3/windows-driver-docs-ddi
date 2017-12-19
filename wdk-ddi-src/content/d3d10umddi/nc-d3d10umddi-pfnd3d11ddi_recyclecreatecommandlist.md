---
UID: NC.d3d10umddi.PFND3D11DDI_RECYCLECREATECOMMANDLIST
title: PFND3D11DDI_RECYCLECREATECOMMANDLIST
author: windows-driver-content
description: The RecycleCreateCommandList function creates a command list and makes a previously unused DDI handle completely valid again.
old-location: display\recyclecreatecommandlist.htm
old-project: display
ms.assetid: c387545e-2891-401d-b7ca-ee7549a52603
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RecycleCreateCommandList is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RecycleCreateCommandList
req.alt-loc: d3d10umddi.h
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

# PFND3D11DDI_RECYCLECREATECOMMANDLIST callback



## -description
The <i>RecycleCreateCommandList</i> function creates a command list and makes a previously unused DDI handle completely valid again.



## -prototype

````
PFND3D11DDI_RECYCLECREATECOMMANDLIST RecycleCreateCommandList;

HRESULT APIENTRY RecycleCreateCommandList(
  _In_       D3D10DDI_HDEVICE              hDevice,
  _In_ const D3D11DDIARG_CREATECOMMANDLIST *pCreateCommandList,
  _In_       D3D11DDI_HCOMMANDLIST         hCommandList,
  _In_       D3D11DDI_HRTCOMMANDLIST       hRTCommandList
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pCreateCommandList [in]

 [in] A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createcommandlist.md">D3D11DDIARG_CREATECOMMANDLIST</a> structure that describes the parameters that the user-mode display driver uses to create a command list.  


### -param hCommandList [in]

 A handle to the driver's private data for the command list. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md">CalcPrivateCommandListSize</a> function. The handle is just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its command list. 


### -param hRTCommandList [in]

 A handle to the command list that the driver should use, when it calls back into the Direct3D runtime. 


## -returns
<i>RecycleCreateCommandList</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The command list is successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>RecycleCreateCommandList</i> could not allocate memory that is required for it to complete.

 


## -remarks
The driver is only required to implement <i>RecycleCreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability, which can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

For more information about <i>RecycleCreateCommandList</i>, see <a href="https://msdn.microsoft.com/7bede247-680d-4fd3-a10b-6ef63f0a88ec">Optimization for Small Command Lists</a>.


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
RecycleCreateCommandList is supported beginning with the Windows 7 operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize.md">CalcPrivateCommandListSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs~r1.md">D3D11DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createcommandlist.md">D3D11DDIARG_CREATECOMMANDLIST</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_RECYCLECREATECOMMANDLIST callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
