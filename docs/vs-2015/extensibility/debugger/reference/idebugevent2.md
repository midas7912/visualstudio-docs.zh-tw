---
title: IDebugEvent2 |Microsoft Docs
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
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3d4b1022d8eda4cfb992e9bfcc997193a84ee37
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51770022"
---
# <a name="idebugevent2"></a>IDebugEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此介面用來傳達重要的偵錯資訊，例如停止於中斷點，以及非關鍵的資訊，例如偵錯訊息。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 偵錯引擎 (DE) 和自訂連接埠提供者實作此介面上所有其他的事件介面的相同物件。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 使用介面識別碼 (IID) 引數提供給[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)或是[事件](../../../extensibility/debugger/reference/idebugportevents2-event.md)，工作階段的偵錯管理員 (SDM) 呼叫[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上`IDebugEvent2`介面，以取得適當的事件介面。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法`IDebugEvent2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|取得這個偵錯事件的屬性。|  
  
## <a name="remarks"></a>備註  
 更具體的事件介面，例如[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)，不是衍生自 IDebugEvent2 介面，但會改為實作為個別的介面上的相同物件`IDebugEvent2`。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [核心介面](../../../extensibility/debugger/reference/core-interfaces.md)   
 [事件](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

