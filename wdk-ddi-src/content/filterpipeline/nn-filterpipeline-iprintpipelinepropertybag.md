---
UID : NN:filterpipeline.IPrintPipelinePropertyBag
title : IPrintPipelinePropertyBag
author : windows-driver-content
description : The IPrintPipelinePropertyBag interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. IprintPipelinePropertyBag inherits from the IUnknown interface.
old-location : print\iprintpipelinepropertybag.htm
old-project : print
ms.assetid : 3997291f-0af3-4fa8-8d36-20ff36551f42
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IXpsPartIterator, IXpsPartIterator::Reset, Reset
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : filterpipeline.h
req.include-header : Filterpipeline.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPrintPipelinePropertyBag
req.alt-loc : filterpipeline.h
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
req.typenames : EXpsFontRestriction
---

# IPrintPipelinePropertyBag interface

The <code>IPrintPipelinePropertyBag</code> interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the <a href="..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md">IPrintPipelineFilter</a> interface. <code>IprintPipelinePropertyBag</code> inherits from the <b>IUnknown</b> interface.

The properties of the property bag are described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff561066">Print Pipeline Property Bag</a>.

## Methods

<p>The <b>IPrintPipelinePropertyBag</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [filterpipeline.IPrintPipelinePropertyBag.AddProperty](nf-filterpipeline-iprintpipelinepropertybag-addproperty.md) | The AddProperty method adds a property to a property bag. |
| [filterpipeline.IPrintPipelinePropertyBag.DeleteProperty](nf-filterpipeline-iprintpipelinepropertybag-deleteproperty.md) | The DeleteProperty method deletes a property from a property bag. |
| [filterpipeline.IPrintPipelinePropertyBag.GetProperty](nf-filterpipeline-iprintpipelinepropertybag-getproperty.md) | The GetProperty method gets a property from a property bag. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h (include Filterpipeline.h) |
| **DLL** |  |