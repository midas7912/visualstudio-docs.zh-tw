---
title: IDebugFunctionObject::CreateArrayObject |Microsoft Docs
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
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8330fa51b4ab0adcb11fdc5c20729a6f2b41ca52
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51752978"
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

建立的陣列物件。 此陣列可以包含任一個基本型別或物件執行個體的值。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ot`  
 [in]指定的值從[OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md)列舉，指出新的陣列物件的類型。  
  
 `pClassField`  
 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)物件，表示類別的物件，如果正在建立物件的陣列執行個體的值。 如果建立基本物件的陣列，這個參數為 null 值。  
  
 `dwRank`  
 [in]陣序規範或陣列的維度數目。  
  
 `dwDims`  
 [in]陣列的每個維度大小。  
  
 `dwLowBounds`  
 [in]每個維度的來源 （通常是 0 或 1）。  
  
 `ppObject`  
 [out]傳回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)物件，代表新建立的陣列。 這是實際[IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)物件。  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回 S_OK;否則，傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 呼叫這個方法來建立物件，表示函式表示的陣列參數[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)介面。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

