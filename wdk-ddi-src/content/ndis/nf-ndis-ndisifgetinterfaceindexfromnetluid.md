---
UID: NF.ndis.NdisIfGetInterfaceIndexFromNetLuid
title: NdisIfGetInterfaceIndexFromNetLuid function
author: windows-driver-content
description: The NdisIfGetInterfaceIndexFromNetLuid function gets the network interface index that is associated with a NET_LUID value.
old-location: netvista\ndisifgetinterfaceindexfromnetluid.htm
old-project: NetVista
ms.assetid: 6aaa4ae9-fd3c-4cdd-ac37-0533c45143af
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisIfGetInterfaceIndexFromNetLuid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisIfGetInterfaceIndexFromNetLuid
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Interfaces_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisIfGetInterfaceIndexFromNetLuid function



## -description
The 
  <b>NdisIfGetInterfaceIndexFromNetLuid</b> function gets the network interface index that is associated with
  a 
  <a href="netvista.net_luid">NET_LUID</a> value.



## -syntax

````
NDIS_STATUS NdisIfGetInterfaceIndexFromNetLuid(
  _In_  NET_LUID     NetLuid,
  _Out_ PNET_IFINDEX pIfIndex
);
````


## -parameters

### -param NetLuid [in]

A 
     <a href="netvista.net_luid">NET_LUID</a> value that identifies a network
     interface.


### -param pIfIndex [out]

A pointer to a caller-supplied interface index variable. If 
     <b>NdisIfGetInterfaceIndexFromNetLuid</b> succeeds, NDIS writes the network interface index that is
     associated with the specified NET_LUID to this variable.


## -returns
<b>NdisIfGetInterfaceIndexFromNetLuid</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_INTERFACE_NOT_FOUND</b></dt>
</dl><b>NdisIfGetInterfaceIndexFromNetLuid</b> failed because the specified NET_LUID was not present in the
       list of registered interfaces.

 


## -remarks
NDIS drivers can call the 
    <b>NdisIfGetInterfaceIndexFromNetLuid</b> function to get the network interface index that is associated
    with a 
    <a href="netvista.net_luid">NET_LUID</a> value.

For the interfaces that the NDIS proxy provider service manages, NDIS provides the interface index and
    NET_LUID in various driver initialization structures:

Miniport drivers can obtain the interface index and NET_LUID for a miniport adapter in the 
      <a href="netvista.ndis_miniport_init_parameters">
      NDIS_MINIPORT_INIT_PARAMETERS</a> structure.

Filter drivers can obtain the interface index and NET_LUID for a filter module in the 
      <a href="netvista.ndis_filter_attach_parameters">
      NDIS_FILTER_ATTACH_PARAMETERS</a> structure.

Protocol drivers can obtain the interface index and NET_LUID of the highest and the lowest
      interfaces on a driver stack in the 
      <a href="netvista.ndis_bind_parameters">NDIS_BIND_PARAMETERS</a> structure.

NDIS assigns an interface index to a network interface when the interface provider calls the 
    <a href="netvista.ndisifregisterinterface">NdisIfRegisterInterface</a> function.
    An interface provider calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff565890">NDIS_MAKE_NET_LUID</a> macro to create the
    NET_LUID value before it registers an interface.

The interface index value can change without a computer restart. Deregistering and re-registering an
    interface that is associated with a NET_LUID value might result in different interface index values. Do
    not confuse the interface index with the NET_LUID index that persists after a computer restarts.

NDIS provides the 
    <a href="netvista.ndisifgetnetluidfrominterfaceindex">
    NdisIfGetNetLuidFromInterfaceIndex</a> function to get the NET_LUID value that is associated with a
    specified interface index.


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
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_interfaces_function">Irql_Interfaces_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_bind_parameters">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_filter_attach_parameters">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565890">NDIS_MAKE_NET_LUID</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndisifgetnetluidfrominterfaceindex">
   NdisIfGetNetLuidFromInterfaceIndex</a>
</dt>
<dt>
<a href="netvista.ndisifregisterinterface">NdisIfRegisterInterface</a>
</dt>
<dt>
<a href="netvista.net_luid">NET_LUID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisIfGetInterfaceIndexFromNetLuid function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
