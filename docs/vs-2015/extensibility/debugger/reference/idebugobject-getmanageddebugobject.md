---
title: IDebugObject::GetManagedDebugObject |Microsoft Docs
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
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5530865b9d6c7cfb74c91f00b6a65e41702135cb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807266"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

偵錯引擎的位址空間中建立受管理物件的複本。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppObject`  
 [out]傳回[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)物件，代表新建立的 managed 的物件。  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回 S_OK;否則，傳回錯誤碼。 如果這個傳回 E_FAIL [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)不代表 managed 實值類別的執行個體。  
  
## <a name="remarks"></a>備註  
 這[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)物件必須代表 managed 實值類別的執行個體，例如`System.Decimal`執行個體。 所需的本機複本，而呼叫的額外負荷[Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)就會被淘汰。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)

