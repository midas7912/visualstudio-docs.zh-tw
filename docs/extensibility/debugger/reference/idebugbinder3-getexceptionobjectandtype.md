---
title: IDebugBinder3::GetExceptionObjectAndType |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBinder3::GetExceptionObjectAndType
helpviewer_keywords:
- IDebugBinder3::GetExceptionObjectAndType method
ms.assetid: 2a313fe1-4ee1-4f01-af86-382d6c661a8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61f82cdeda76cd8660fff47e30edf37c81d154f5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49867789"
---
# <a name="idebugbinder3getexceptionobjectandtype"></a>IDebugBinder3::GetExceptionObjectAndType
如果有的話，這個方法會擷取與物件相關聯的例外狀況。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetExceptionObjectAndType(  
   IDebugObject** ppException,  
   IDebugField**  ppField  
);  
```  
  
```csharp  
int GetExceptionObjectAndType(  
   out IDebugObject ppException,  
   out IDebugField  ppField  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppException`  
 [out]傳回表示例外狀況的物件。  
  
 `ppField`  
 [out]傳回物件，代表特定的欄位可能會造成例外狀況 （這可能是 null 值）。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
> [!NOTE]
>  若要確認是否有例外狀況，請檢查所傳回的值`ppException`： 如果它是 null 值，則任何例外狀況物件相關聯。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)