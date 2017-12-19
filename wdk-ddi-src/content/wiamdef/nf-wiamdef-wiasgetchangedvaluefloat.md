---
UID: NF.wiamdef.wiasGetChangedValueFloat
title: wiasGetChangedValueFloat function
author: windows-driver-content
description: The wiasGetChangedValueFloat function determines whether a property with a floating-point value has been changed by an application.
old-location: image\wiasgetchangedvaluefloat.htm
old-project: Image
ms.assetid: 934ea038-e8fb-446d-8ba8-1cde56d3af87
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: wiasGetChangedValueFloat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiasGetChangedValueFloat
req.alt-loc: Wiaservc.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
req.product: Windows 10 or later.
---

# wiasGetChangedValueFloat function



## -description
The <b>wiasGetChangedValueFloat </b>function determines whether a property with a floating-point value has been changed by an application.



## -syntax

````
HRESULT _stdcall wiasGetChangedValueFloat(
  _In_  BYTE                    *pWiasContext,
  _In_  WIA_PROPERTY_CONTEXT    *pContext,
        BOOL                    bNoValidation,
        PROPID                  propID,
  _Out_ WIAS_CHANGED_VALUE_INFO *pValInfo
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.


### -param pContext [in]

Pointer to a <a href="image.wia_property_context">WIA_PROPERTY_CONTEXT</a> structure that contains the current property context.


### -param bNoValidation 

Indicates whether the property's current value should be validated against its set of valid values. If this parameter is set to <b>TRUE</b>, the function does not perform validation on the property. If it is <b>FALSE</b>, the function performs data validation. 


### -param propID 

Specifies the property identifier of the property being tested.


### -param pValInfo [out]

Pointer to a <a href="image.wias_changed_value_info">WIAS_CHANGED_VALUE_INFO</a> structure that contains the current and previous values of the property.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## -remarks
The driver should validate the property only after the driver has updated the values of the property. The driver updates the values as a result of property changes requested by the application.


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
Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wiamdef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wiaservc.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Wiaservc.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.wiasgetchangedvalueguid">wiasGetChangedValueGuid</a>
</dt>
<dt>
<a href="image.wiasgetchangedvaluelong">wiasGetChangedValueLong</a>
</dt>
<dt>
<a href="image.wiasgetchangedvaluestr">wiasGetChangedValueStr</a>
</dt>
<dt>
<a href="image.wia_property_context">WIA_PROPERTY_CONTEXT</a>
</dt>
<dt>
<a href="image.wias_changed_value_info">WIAS_CHANGED_VALUE_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiasGetChangedValueFloat function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
