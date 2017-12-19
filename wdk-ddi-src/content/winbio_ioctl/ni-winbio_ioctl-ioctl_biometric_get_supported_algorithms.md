---
UID: NI.winbio_ioctl.IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS
title: IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS
author: windows-driver-content
description: The IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS IOCTL retrieves a list of cryptographic hash algorithms that are supported by the device. This IOCTL is optional.
old-location: biometric\ioctl_biometric_get_supported_algorithms.htm
old-project: biometric
ms.assetid: 0bc373a8-af60-419a-88e1-58888b88f24d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWiaTransferCallback, IWiaTransferCallback::TransferCallback, TransferCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS
req.alt-loc: Winbio_ioctl.h
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

# IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS IOCTL



## -description
The IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS IOCTL retrieves a list of cryptographic hash algorithms that are supported by the device. This IOCTL is optional.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="biometric.winbio_supported_algorithms">WINBIO_SUPPORTED_ALGORITHMS</a> structure.


### -output-buffer-length
The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.

S_OK, STATUS_SUCCESS

The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.

E_INVALIDARG

The parameters were not specified correctly.

E_UNKNOWN

Any other failure that prevents the payload from being filled in.

E_UNEXPECTED

Any other failure that prevents the payload from being filled in.

E_FAIL

Any other failure that prevents the payload from being filled in.

 


## -remarks
The algorithms are specified by using NULL-terminated UTF-8 encoded strings.  The algorithm identifier "OID" strings are defined in <a href="http://go.microsoft.com/fwlink/p/?linkid=133011">RFC 3279 </a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=133012">RFC 3278 </a><u>.</u>

Here are examples of OID strings for hash algorithms.

SHA-1

"1.3.14.3.2.26"

SHA-256

"2.16.840.1.101.3.4.2.1"

SHA-384

"2.16.840.1.101.3.4.2.2"

SHA-512

"2.16.840.1.101.3.4.2.3"

IOCTL_BIOMETRIC_GET_SUPPORTED_ALGORITHMS must be implemented if the device supports WINBIO_CAPABILITY_SECURE_STORAGE.  The device must support at least SHA-1 ("1.3.14.3.2.26") to be used for storing WinBio templates.

If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of <a href="biometric.winbio_supported_algorithms">WINBIO_SUPPORTED_ALGORITHMS</a> with the status of the Biometric operation.

Possible values include:



The operation completed successfully.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winbio_ioctl.h</dt>
</dl>
</td>
</tr>
</table>