---
UID: NF.wdbgexts.GetFieldValue
title: GetFieldValue macro
author: windows-driver-content
description: The GetFieldValue macro is a thin wrapper around the GetFieldData function. It is provided as a convenience for reading the value of a member in a structure.
old-location: debugger\getfieldvalue.htm
old-project: Debugger
ms.assetid: 4655bac3-997e-43d9-b628-b4292ae5509d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GetFieldValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetFieldValue
req.alt-loc: wdbgexts.h
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
req.product: Windows 10 or later.
---

# GetFieldValue macro



## -description
The <b>GetFieldValue</b> macro is a thin wrapper around the <a href="debugger.getfielddata">GetFieldData</a> function.  It is provided as a convenience for reading the value of a member in a structure.



## -syntax

````
__inline ULONG GetFieldValue(
   ULONG64 Addr,
   LPCSTR  Type,
   LPCSTR  Field,
   PVOID   OutValue
);
````


## -parameters

### -param Addr 

Specifies the address of the structure in the target's memory.


### -param Type 

Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


### -param Field 

Specifies the name of the member in the structure.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".


### -param OutValue 

Specifies the object into which the member's value is read.


## -remarks
The parameters provided to this macro are the same as those provided to the <b>GetFieldData</b> function except that instead of providing a pointer to a buffer and its size, the variable to hold the returned value can be provided directly.


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
Header

</th>
<td width="70%">
<dl>
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.getfielddata">GetFieldData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20GetFieldValue function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
