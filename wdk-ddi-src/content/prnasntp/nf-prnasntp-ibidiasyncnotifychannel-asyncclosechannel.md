---
UID: NF:prnasntp.IBidiAsyncNotifyChannel.AsyncCloseChannel
title: IBidiAsyncNotifyChannel::AsyncCloseChannel method
author: windows-driver-content
description: "."
old-location: print\ibidiasyncnotifychannel_asyncclosechannel.htm
old-project: print
ms.assetid: D2A8A131-E839-40E2-8897-DA74F7BA0FA8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AsyncCloseChannel method [Print Devices], AsyncCloseChannel method [Print Devices], IBidiAsyncNotifyChannel interface, AsyncCloseChannel,IBidiAsyncNotifyChannel.AsyncCloseChannel, IBidiAsyncNotifyChannel, IBidiAsyncNotifyChannel interface [Print Devices], AsyncCloseChannel method, IBidiAsyncNotifyChannel::AsyncCloseChannel, print.ibidiasyncnotifychannel_asyncclosechannel, prnasntp/IBidiAsyncNotifyChannel::AsyncCloseChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prnasntp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	COM
api_location:
-	Prnasntp.h
api_name:
-	IBidiAsyncNotifyChannel.AsyncCloseChannel
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IBidiAsyncNotifyChannel::AsyncCloseChannel method


## -description





## -syntax


````
HRESULT AsyncCloseChannel(
  [in] IPrintAsyncNotifyDataObject *pObject,
  [in] IPrintAsyncCookie           *pCookie
);
````


## -parameters




### -param param




### -param EQUALNULL






#### - pCookie [in]


#### - pObject [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-ibidiasyncnotifychannel.md">IBidiAsyncNotifyChannel</a>



 

 

