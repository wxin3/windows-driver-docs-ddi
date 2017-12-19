---
UID: NF.ndis.NdisClCloseAddressFamily
title: NdisClCloseAddressFamily function
author: windows-driver-content
description: NdisClCloseAddressFamily releases the association between a client protocol and a call manager's or MCM driver's registered AF for a particular NIC to which the client is bound.
old-location: netvista\ndisclcloseaddressfamily.htm
old-project: NetVista
ms.assetid: ae6b9133-bb98-4858-bef5-1cbe0ae0dd4f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisClCloseAddressFamily
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClCloseAddressFamily (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClCloseAddressFamily (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisClCloseAddressFamily
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisClCloseAddressFamily function



## -description
<b>NdisClCloseAddressFamily</b> releases
  the association between a client protocol and a call manager's or MCM driver's registered AF for a
  particular NIC to which the client is bound.



## -syntax

````
NDIS_STATUS NdisClCloseAddressFamily(
  _In_ NDIS_HANDLE NdisAfHandle
);
````


## -parameters

### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle returned by 
     <a href="netvista.ndisclopenaddressfamilyex">
     NdisClOpenAddressFamilyEx</a>.


## -returns
When 
      <b>
      NdisClCloseAddressFamily</b> returns anything other than NDIS_STATUS_PENDING, the client should make
      an internal call to its 
      <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
      ProtocolClCloseAfComplete</a> function. Otherwise, NDIS calls the client's 
      <i>
      ProtocolClCloseAfComplete</i> function when this operation is completed.

If 
      <b>
      NdisClCloseAddressFamily</b> returns NDIS_STATUS_PENDING, a client that is waiting for its 
      <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
      ProtocolClCloseAfComplete</a> function to be called should not block the current thread since this
      could cause a deadlock. This is particularly important when a client calls 
      <b>NdisClCloseAddressFamily</b> in the
      context of handling an 
      <a href="netvista.ndiscmnotifycloseaddressfamily">
      NdisCmNotifyCloseAddressFamily</a> request. In this case, the call manager may not close the address
      family until after the client has returned from handling the 
      <b>NdisCmNotifyCloseAddressFamily</b> request. If the client blocks the
      current thread, the client will never complete the handling of the 
      <b>NdisCmNotifyCloseAddressFamily</b> request, thus causing a deadlock.


## -remarks
A client commonly calls 
    <b>NdisClCloseAddressFamily</b> from its
    
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function, after it closes all the client's open VCs on the binding with
    calls to 
    <a href="netvista.ndisclclosecall">NdisClCloseCall</a> and/or 
    <a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>. A client can
    also call 
    <b>NdisClCloseAddressFamily</b> in the
    context of processing an 
    <a href="netvista.ndiscmnotifycloseaddressfamily">
    NdisCmNotifyCloseAddressFamily</a> request.

NDIS calls a client's 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function whenever an underlying NIC to which that client is bound is being
    removed from the machine or is being reconfigured. A PnP reconfiguration of the underlying miniport
    driver causes the call manager or MCM driver to reregister the address family it supports over that NIC.
    This, in turn, causes a subsequent call to the client's 
    <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
    ProtocolCoAfRegisterNotify</a> function. In either scenario, the client's 
    <i>
    ProtocolUnbindAdapterEx</i> function must call 
    <b>NdisClCloseAddressFamily</b> with any
    outstanding 
    <i>NdisAfHandle</i> it is currently using that depends on the underlying miniport
    driver.

As a general guideline, a client should release all the resources it allocated for connection-oriented
    communications through the miniport driver before its 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function calls 
    <a href="netvista.ndiscloseadapterex">NdisCloseAdapterEx</a>.

The 
    <i>NdisAfHandle</i> passed to 
    <b>NdisClCloseAddressFamily</b> becomes
    invalid for the client as soon as this call occurs.

Before a call to 
    <b>NdisClCloseAddressFamily</b>, the
    client may use the 
    <i>NdisAfHandle</i> while the AF is open or while a 
    <a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">
    ProtocolClNotifyCloseAf</a> operation is pending. If the 
    <i>
    ProtocolClNotifyCloseAf</i> function returns NDIS_STATUS_PENDING, use the handle in the 
    <a href="netvista.ndisclnotifycloseaddressfamilycomplete">
    NdisClNotifyCloseAddressFamilyComplete</a> call after the close operation completes.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/0e4b48c8-4b6d-4b6a-8d0a-9d66809fadc2">NdisClCloseAddressFamily (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisClCloseAddressFamily (NDIS
   5.1)</b>) in Windows XP.

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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_protocol_driver_function">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisclclosecall">NdisClCloseCall</a>
</dt>
<dt>
<a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>
</dt>
<dt>
<a href="netvista.ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisClCloseAddressFamily function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
