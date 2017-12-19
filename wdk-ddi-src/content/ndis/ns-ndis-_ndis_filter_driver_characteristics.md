---
UID: NS.NDIS._NDIS_FILTER_DRIVER_CHARACTERISTICS
title: _NDIS_FILTER_DRIVER_CHARACTERISTICS
author: windows-driver-content
description: To specify its driver characteristics, a filter driver initializes an NDIS_FILTER_DRIVER_CHARACTERISTICS structure and passes it to NDIS.
old-location: netvista\ndis_filter_driver_characteristics.htm
old-project: NetVista
ms.assetid: 1eb2bae0-70b9-4bc0-9d93-4fc9467f9532
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_FILTER_DRIVER_CHARACTERISTICS, NDIS_FILTER_DRIVER_CHARACTERISTICS, PNDIS_FILTER_DRIVER_CHARACTERISTICS, *PNDIS_FILTER_DRIVER_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_FILTER_DRIVER_CHARACTERISTICS
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# _NDIS_FILTER_DRIVER_CHARACTERISTICS structure



## -description
To specify its driver characteristics, a filter driver initializes an
  NDIS_FILTER_DRIVER_CHARACTERISTICS structure and passes it to NDIS.



## -syntax

````
typedef struct _NDIS_FILTER_DRIVER_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                              Header;
  UCHAR                                           MajorNdisVersion;
  UCHAR                                           MinorNdisVersion;
  UCHAR                                           MajorDriverVersion;
  UCHAR                                           MinorDriverVersion;
  ULONG                                           Flags;
  NDIS_STRING                                     FriendlyName;
  NDIS_STRING                                     UniqueName;
  NDIS_STRING                                     ServiceName;
  SET_OPTIONS_HANDLER                             SetOptionsHandler;
  FILTER_SET_FILTER_MODULE_OPTIONS_HANDLER        SetFilterModuleOptionsHandler;
  FILTER_ATTACH_HANDLER                           AttachHandler;
  FILTER_DETACH_HANDLER                           DetachHandler;
  FILTER_RESTART_HANDLER                          RestartHandler;
  FILTER_PAUSE_HANDLER                            PauseHandler;
  FILTER_SEND_NET_BUFFER_LISTS_HANDLER            SendNetBufferListsHandler;
  FILTER_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER   SendNetBufferListsCompleteHandler;
  FILTER_CANCEL_SEND_HANDLER                      CancelSendNetBufferListsHandler;
  FILTER_RECEIVE_NET_BUFFER_LISTS_HANDLER         ReceiveNetBufferListsHandler;
  FILTER_RETURN_NET_BUFFER_LISTS_HANDLER          ReturnNetBufferListsHandler;
  FILTER_OID_REQUEST_HANDLER                      OidRequestHandler;
  FILTER_OID_REQUEST_COMPLETE_HANDLER             OidRequestCompleteHandler;
  FILTER_CANCEL_OID_REQUEST_HANDLER               CancelOidRequestHandler;
  FILTER_DEVICE_PNP_EVENT_NOTIFY_HANDLER          DevicePnPEventNotifyHandler;
  FILTER_NET_PNP_EVENT_HANDLER                    NetPnPEventHandler;
  FILTER_STATUS_HANDLER                           StatusHandler;
#if (NDIS_SUPPORT_NDIS61)
  FILTER_DIRECT_OID_REQUEST_HANDLER               DirectOidRequestHandler;
  FILTER_DIRECT_OID_REQUEST_COMPLETE_HANDLER      DirectOidRequestCompleteHandler;
  FILTER_CANCEL_DIRECT_OID_REQUEST_HANDLER        CancelDirectOidRequestHandler;
#endif 
#if (NDIS_SUPPORT_NDIS680)
  FILTER_SYNCHRONOUS_OID_REQUEST_HANDLER          SynchronousOidRequestHandler;
  FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE_HANDLER SynchronousOidRequestHandlerComplete;
#endif 
} NDIS_FILTER_DRIVER_CHARACTERISTICS, *PNDIS_FILTER_DRIVER_CHARACTERISTICS;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     filter driver characteristics structure (NDIS_FILTER_DRIVER_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_DRIVER_CHARACTERISTICS.
     

To indicate the version of the NDIS_FILTER_DRIVER_CHARACTERISTICS structure, set the 
     <b>Revision</b> member to one of the following values:




### -field NDIS_FILTER_CHARACTERISTICS_REVISION_3

Added the 
        <b>SynchronousOidRequestHandler</b> and <b>SynchronousOidRequestHandlerComplete</b> members for NDIS 6.80.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_3.


### -field NDIS_FILTER_CHARACTERISTICS_REVISION_2

Added the 
        <b>DirectOidRequestHandler</b>, 
        <b>DirectOidRequestCompleteHandler</b>, and 
        <b>CancelDirectOidRequestHandler</b> members for NDIS 6.1.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_2.


### -field NDIS_FILTER_CHARACTERISTICS_REVISION_1

Original version.

Set the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_DRIVER_CHARACTERISTICS_REVISION_1.

</dd>
</dl>

### -field MajorNdisVersion

The major version of NDIS that the driver is using. The current value is
     0x06.


### -field MinorNdisVersion

The minor NDIS version. The following are the available minor version value settings.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">

### -field 0

</td>
<td width="60%">
NDIS 6

</td>
</tr>
<tr>
<td width="40%">

### -field 20

</td>
<td width="60%">
NDIS 6.20

</td>
</tr>
<tr>
<td width="40%">

### -field 30

</td>
<td width="60%">
NDIS 6.30

</td>
</tr>
<tr>
<td width="40%">

### -field 40

</td>
<td width="60%">
NDIS 6.40

</td>
</tr>
<tr>
<td width="40%">

### -field 50

</td>
<td width="60%">
NDIS 6.50

</td>
</tr>
<tr>
<td width="40%">

### -field 51

</td>
<td width="60%">
NDIS 6.51

</td>
</tr>
<tr>
<td width="40%">

### -field 60

</td>
<td width="60%">
NDIS 6.60

</td>
</tr>
<tr>
<td width="40%">

### -field 70

</td>
<td width="60%">
NDIS 6.70

</td>
</tr>
<tr>
<td width="40%">

### -field 80

</td>
<td width="60%">
NDIS 6.80

</td>
</tr>
</table>
 


### -field MajorDriverVersion

Reserved for the major version number of the filter driver. Filter drivers can specify any value
     that they require.


### -field MinorDriverVersion

Reserved for the minor version number of the filter driver. Filter drivers can specify any value
     that they require.


### -field Flags

Reserved for NDIS.


### -field FriendlyName

A Unicode string that represents the user-readable description of the filter driver.


### -field UniqueName

A Unicode string that represents the unique name for the filter driver. This string must be a GUID, enclosed in curly braces, for example "{5cbf81bd-5055-47cd-9055-a76b2b4e3697}". This GUID must match the one in the <b>NetCfgInstanceId</b> INF file entry in the filter driver's INF file. For more information, see <a href="netvista.inf_file_settings_for_filter_drivers">INF File Settings for Filter Drivers</a>.


### -field ServiceName

A Unicode string that represents the service name of the filter driver. This string must be the service name
     from the AddService directive in the filter driver's INF file. For more information, see <a href="netvista.inf_file_settings_for_filter_drivers">INF File Settings for Filter Drivers</a>.


### -field SetOptionsHandler

Specifies the entry point of the caller's 
     <a href="netvista.filtersetoptions">FilterSetOptions</a> function.


### -field SetFilterModuleOptionsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_set_module_options.md">
     FilterSetModuleOptions</a> function.


### -field AttachHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -field DetachHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a> function.


### -field RestartHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a> function.


### -field PauseHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a> function.


### -field SendNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SendNetBufferListsCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.


### -field CancelSendNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_cancel_send_net_buffer_lists.md">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReceiveNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field ReturnNetBufferListsHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field OidRequestHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function. To bypass
     this function, set this member to <b>NULL</b>.


### -field OidRequestCompleteHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_oid_request_complete.md">
     FilterOidRequestComplete</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field CancelOidRequestHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">
     FilterCancelOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field DevicePnPEventNotifyHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">
     FilterDevicePnPEventNotify</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field NetPnPEventHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_net_pnp_event.md">FilterNetPnPEvent</a> function. To
     bypass this function, set this member to <b>NULL</b>.


### -field StatusHandler

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a> function. To bypass this
     function, set this member to <b>NULL</b>.


### -field DirectOidRequestHandler

The entry point of the caller's 
      <a href="..\ndis\nc-ndis-filter_direct_oid_request.md">
      FilterDirectOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field DirectOidRequestCompleteHandler

The entry point of the caller's 
      <a href="..\ndis\nc-ndis-filter_direct_oid_request_complete.md">
      FilterDirectOidRequestComplete</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field CancelDirectOidRequestHandler

The entry point of the caller's 
      <a href="..\ndis\nc-ndis-filter_cancel_direct_oid_request.md">
      FilterCancelDirectOidRequest</a> function. To bypass this function, set this member to <b>NULL</b>.


### -field SynchronousOidRequestHandler

<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div>
<div> </div>
This member is reserved.


### -field SynchronousOidRequestHandlerComplete

<div class="alert"><b>Warning</b>  In Windows 10, version 1709, Synchronous OID requests are supported only for miniport and protocol drivers. Filter drivers cannot make Synchronous OID request calls in Windows 10, version 1709.</div>
<div> </div>
This member is reserved.


## -remarks
A filter driver calls the 
    <a href="netvista.ndisfregisterfilterdriver">
    NdisFRegisterFilterDriver</a> function to register its characteristics, including the default entry
    points for its filter driver functions (<i>FilterXxx</i>). The filter driver initializes an NDIS_FILTER_DRIVER_CHARACTERISTICS structure and
    passes a pointer to this structure in the 
    <i>FilterCharacteristics</i> parameter of 
    <b>NdisFRegisterFilterDriver</b>.


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_cancel_direct_oid_request.md">
   FilterCancelDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">FilterCancelOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_cancel_send_net_buffer_lists.md">
   FilterCancelSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_detach.md">FilterDetach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_device_pnp_event_notify.md">FilterDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_direct_oid_request_complete.md">
   FilterDirectOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_net_pnp_event.md">FilterNetPnPEvent</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_oid_request_complete.md">FilterOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_pause.md">FilterPause</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_restart.md">FilterRestart</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">FilterReturnNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
   FilterSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_set_module_options.md">FilterSetModuleOptions</a>
</dt>
<dt>
<a href="netvista.filtersetoptions">FilterSetOptions</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_status.md">FilterStatus</a>
</dt>
<dt>
<a href="netvista.ndis_filter_partial_characteristics">
   NDIS_FILTER_PARTIAL_CHARACTERISTICS</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>
</dt>
<dt>
<a href="netvista.inf_file_settings_for_filter_drivers">INF File Settings for Filter Drivers</a>
</dt>
<dt>
<a href="netvista.initializing_a_filter_driver">Initializing a Filter Driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_FILTER_DRIVER_CHARACTERISTICS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
