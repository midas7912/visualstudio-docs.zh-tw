---
title: IDebugCustomAttributeQuery2 |Microsoft Docs
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
- IDebugCustomAttributeQuery2
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
- IDebugCustomAttributeQuery2 interface
ms.assetid: 7cfa23e4-a05a-47a3-af6c-bd40c655014b
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b175a15520b9956ecd2a1418f35f1aa9bdbc1330
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51739065"
---
# <a name="idebugcustomattributequery2"></a>IDebugCustomAttributeQuery2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

判斷此欄位的自訂屬性存在，如果存在的話，會傳回屬性資訊。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugCustomAttributeQuery2 : IDebugCustomAttributeQuery  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 符號提供者所實作的相同物件上實作這個介面[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)以支援自訂屬性。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 使用[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)若要取得從這個介面[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)介面。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法**IDebugCustomAttributeQuery**介面。  
  
|方法|描述|  
|------------|-----------------|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)|判斷名稱是否存在的自訂屬性。|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md)|取得指定的自訂屬性的屬性資訊。|  
  
 除了**IDebugCustomAttributeQuery**方法，`IDebugCustomAttributeQuery2`實作下列方法：  
  
|方法|描述|  
|------------|-----------------|  
|[EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)|取得附加至這個欄位的所有自訂屬性的列舉值。|  
  
## <a name="remarks"></a>備註  
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)方法可以傳回為這個欄位定義的所有自訂屬性的列舉值。  
  
## <a name="requirements"></a>需求  
 標頭： sh.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [符號提供者介面](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)

