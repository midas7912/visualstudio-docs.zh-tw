---
title: IDebugPort2::GetPortRequest |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e6e041bd4772b5487d0023e01b0c89c483d2f65d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51760115"
---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

取得先前用來建立連接埠 （如果有的話） 的連接埠的描述。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT GetPortRequest(   
   IDebugPortRequest2** ppRequest  
);  
```  
  
```csharp  
int GetPortRequest(   
   out IDebugPortRequest2 ppRequest  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppRequest`  
 [out]傳回[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)物件，表示用來建立連接埠的要求。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  傳回`E_PORT_NO_REQUEST`如果使用未建立連接埠[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)連接埠要求。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)

