---
UID: NF:udecxurb.UdecxUrbRetrieveControlSetupPacket
title: UdecxUrbRetrieveControlSetupPacket function
author: windows-driver-content
description: Retrieves a USB control setup packet from a specified framework request object.
old-location: buses\udecxurbretrievecontrolsetuppacket.htm
old-project: usbref
ms.assetid: 09D9AB68-12DB-442F-897B-6C6BD8B5F030
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UdecxUrbRetrieveControlSetupPacket, UdecxUrbRetrieveControlSetupPacket function [Buses], buses.udecxurbretrievecontrolsetuppacket, udecxurb/UdecxUrbRetrieveControlSetupPacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxurb.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUrbRetrieveControlSetupPacket
product:
- Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# UdecxUrbRetrieveControlSetupPacket function


## -description


Retrieves a USB control setup packet from  a specified framework request object.  


## -parameters




### -param Request [in]

A handle to a framework request object that represents the request containing the setup packet.


### -param SetupPacket [out]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure that receives a setup packet describing the USB control transfer.


## -returns



The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 




## -remarks



The client driver can inspect contents of the setup packet to determine the standard control request that is sent to the device.

To complete the request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/mt595955">UdecxUrbCompleteWithNtStatus</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

