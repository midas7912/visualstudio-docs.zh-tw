---
title: IDebugObject2::IsUserData |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7fee6b88b33080221d619d40f797d0a976d5f495
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49849173"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
判斷物件是否代表使用者資料。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT IsUserData(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserData(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pfUser`  
 [out]傳回非零值 (`TRUE`) 該物件所代表的使用者資料; 如果零 (`FALSE`) 如果沒有。  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回 S_OK;否則，傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 使用者資料是任何物件，是指定為 JustMyCode （使用者可設定選項，將模組標記為使用者程式碼，並因此出現在堆疊追蹤） 模組的一部分。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)