---
UID : NN:filterpipeline.IXpsDocument
title : IXpsDocument
author : windows-driver-content
description : The IXpsDocument interface represents the root of an XPS document.
old-location : print\ixpsdocument.htm
old-project : print
ms.assetid : 1d4a9ad3-6ac1-44c3-9ddd-0dc5f996d70d
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
req.alt-api : IXpsDocument
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

# IXpsDocument interface

The <code>IXpsDocument</code> interface represents the root of an XPS document.

## Methods

<p>The <b>IXpsDocument</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [filterpipeline.IXpsDocument.GetThumbnail](nf-filterpipeline-ixpsdocument-getthumbnail.md) | The GetThumbnail method gets the document thumbnail object. |
| [filterpipeline.IXpsDocument.SetThumbnail](nf-filterpipeline-ixpsdocument-setthumbnail.md) | The SetThumbnail method removes the current thumbnail object from the document and inserts a new one. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h (include Filterpipeline.h) |
| **DLL** |  |