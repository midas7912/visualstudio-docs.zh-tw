---
title: IDebugThread2::GetName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugThread2::GetName
helpviewer_keywords:
- IDebugThread2::GetName
ms.assetid: eec54b8f-4a0e-4919-b0f9-81d4bd1e0b6f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 670ee7b9fe8262e981f3c0abeb57710c2da9b0e2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49898469"
---
# <a name="idebugthread2getname"></a>IDebugThread2::GetName
取得執行緒的名稱。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetName (   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName (   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pbstrName`  
 [out]傳回執行緒的名稱。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 擷取的名稱一律可以顯示的名稱，而且此名稱描述執行緒。 執行緒名稱可能會衍生自執行階段架構支援將具名的執行緒，或可能被衍生自的偵錯引擎的名稱。 或者，設定執行緒名稱，藉由呼叫[SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)方法。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)