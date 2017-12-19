---
UID: NF.wsk.WskRegister
title: WskRegister function
author: windows-driver-content
description: The WskRegister function registers a WSK application, given the application's WSK client Network Programming Interface (NPI).
old-location: netvista\wskregister.htm
old-project: NetVista
ms.assetid: 340933ad-1a71-421c-b1e1-360aa9c441fd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WskRegister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskRegister
req.alt-loc: Netio.lib,Netio.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Netio.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WskRegister function



## -description
The 
  <b>WskRegister</b> function registers a WSK application, given the application's WSK client 
  <a href="netvista.network_programming_interface">Network Programming Interface
  (NPI)</a>.



## -syntax

````
NTSTATUS WskRegister(
  _In_  PWSK_CLIENT_NPI   WskClientNpi,
  _Out_ PWSK_REGISTRATION WskRegistration
);
````


## -parameters

### -param WskClientNpi [in]

A pointer to the client NPI implemented by the WSK application.


### -param WskRegistration [out]

A pointer to a memory location that identifies a WSK application's registration instance. This
     memory location will be initialized by the 
     <b>WskRegister</b> call and will be used by the other 
     <a href="netvista.wsk_registration_functions">WSK registration functions</a>. The
     WSK application should never change the contents of this memory location directly.


## -returns
<b>WskRegister</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The registration succeeded.
<dl>
<dt><b>Other status codes</b></dt>
</dl>The registration failed.

 


## -remarks
A WSK client object can call this function multiple times, but a different 
    <i>WskRegistration</i> parameter must be used for each call in order to create multiple registration
    instances.

For each call to 
    <b>WskRegister</b> that returns a success code, there must be exactly one corresponding 
    <a href="netvista.wskderegister">WskDeregister</a> call that uses the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskRegister</b>.

The block of memory pointed to by 
    <i>WskRegistration</i> must be kept allocated (must not be freed or go out of scope) as long as there are
    outstanding calls to other 
    <a href="netvista.wsk_registration_functions">WSK registration functions</a>.


    
    Using the 
    <b>WskRegister</b> and 
    <a href="netvista.wskderegister">WskDeregister</a> functions is the preferred
    method for registering and unregistering WSK applications. The 
    <a href="netvista.network_module_registrar2">Network Module Registrar</a> remains
    available for compatibility.
    

For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="netvista.registering_a_winsock_kernel_application">Registering a Winsock Kernel
    Application</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Netio.lib</dt>
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
<a href="netvista.wskderegister">WskDeregister</a>
</dt>
<dt>
<a href="netvista.wsk_client_npi">WSK_CLIENT_NPI</a>
</dt>
<dt>
<a href="netvista.wsk_registration">WSK_REGISTRATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WskRegister function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
