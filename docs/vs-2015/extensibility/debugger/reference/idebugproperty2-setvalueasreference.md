---
title: IDebugProperty2::SetValueAsReference |Microsoft Docs
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
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f116d2ab53df42a080ab90b6dbecf2ec985fa08a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51773739"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

設定這個屬性的值，指定參考的值。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>參數  
 `rgpArgs`  
 [in]要傳遞至 managed 程式碼屬性 setter 的引數陣列。 如果屬性 setter 不採用引數，或如果這個[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)這類屬性 setter 中，未參考物件`rgpArgs`應為 null 的值。 此參數通常為 null 值。  
  
 `dwArgCount`  
 [in]中的引數數目`rgpArgs`陣列。  
  
 `pValue`  
 [in]參考，形式[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)物件，用來設定這個屬性的值。  
  
 `dwTimeout`  
 [in]取得值，設定以毫秒為單位的時間長度。 一般的值是`INFINITE`。 這會影響任何可評估需要花費的時間的長度。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤程式碼，通常是下列其中之一：  
  
|錯誤|描述|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|不支援從參考中設定的值。|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|無法設定值，因為這個屬性所參考的方法。|  
|`E_SETVALUE_VALUE_IS_READONLY`|值是唯讀的且無法設定。|  
|`E_NOTIMPL`|未實作方法。|  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

