---
title: IDebugBreakpointUnboundEvent2::GetReason |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBreakpointUnboundEvent2::GetReason
helpviewer_keywords:
- IDebugBreakpointUnboundEvent2::GetReason
ms.assetid: 0f8a4fec-d3eb-417d-8516-4f7b51904033
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c6b2dfa661b6dc21b50dec33afc736e0cc3be90a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49926315"
---
# <a name="idebugbreakpointunboundevent2getreason"></a>IDebugBreakpointUnboundEvent2::GetReason
取得中斷點已繫結的原因。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetReason(   
   BP_UNBOUND_REASON* pdwUnboundReason  
);  
```  
  
```csharp  
int GetReason(   
   out enum_ BP_UNBOUND_REASON pdwUnboundReason  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pdwUnboundReason`  
 [out]傳回值，以從[BP_UNBOUND_REASON](../../../extensibility/debugger/reference/bp-unbound-reason.md)指定中斷點已繫結的原因的列舉類型。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 原因包括正在重新繫結至不同的位置之後的編輯後繼續的作業或判斷中斷點已繫結錯誤的中斷點。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CBreakpointUnboundDebugEventBase**公開 （expose） 的物件[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)介面。  
  
```cpp  
STDMETHODIMP CBreakpointUnboundDebugEventBase::GetReason(  
    BP_UNBOUND_REASON* pdwUnboundReason)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( EVAL(pdwUnboundReason) )  
    {  
        *pdwUnboundReason = m_dwReason;  
  
        hRes = S_OK;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)