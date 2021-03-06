---
UID: NS:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECTINFO
title: "_D3DDDI_SYNCHRONIZATIONOBJECTINFO"
author: windows-driver-content
description: The D3DDDI_SYNCHRONIZATIONOBJECTINFO structure contains information about a synchronization object.
old-location: display\d3dddi_synchronizationobjectinfo.htm
old-project: display
ms.assetid: 786934f5-b0ec-4ee9-8bf0-f32b64295b96
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_SYNCHRONIZATIONOBJECTINFO, D3DDDI_SYNCHRONIZATIONOBJECTINFO structure [Display Devices], D3D_other_Structs_86538364-14f8-4e40-bf0e-2e9f836729b8.xml, _D3DDDI_SYNCHRONIZATIONOBJECTINFO, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECTINFO, display.d3dddi_synchronizationobjectinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_SYNCHRONIZATIONOBJECTINFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECTINFO
---

# _D3DDDI_SYNCHRONIZATIONOBJECTINFO structure


## -description


The D3DDDI_SYNCHRONIZATIONOBJECTINFO structure contains information about a synchronization object.


## -struct-fields




### -field Type

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544669">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a>-typed value that indicates the type of synchronization object.


### -field SynchronizationMutex

A structure that contains information about a synchronization mutex. If the <b>Type</b> member is equal to D3DDDI_SYNCHRONIZATION_MUTEX, the union in D3DDDI_SYNCHRONIZATIONOBJECTINFO holds a SynchronizationMutex structure, which contains the following member:


### -field SynchronizationMutex.InitialState

A Boolean value that indicates whether the synchronization mutex is initially owned by an object. A value of <b>TRUE</b> indicates that the mutex is owned; <b>FALSE</b> indicates that the mutex is not owned. 


### -field Semaphore

A structure that contains information about a semaphore. If the <b>Type</b> member is equal to D3DDDI_SEMAPHORE, the union in D3DDDI_SYNCHRONIZATIONOBJECTINFO holds a Semaphore structure, which contains the following members:


### -field Semaphore.MaxCount

The maximum number of events that an object can be waiting for. 


### -field Semaphore.InitialCount

The initial number of events that an object is waiting for. 


### -field Reserved

A structure that is reserved for future use. This structure contains the following member:


### -field Reserved.Reserved

An array of 32-bit values that are reserved for future use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544157">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544669">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a>
 

 

