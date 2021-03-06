---
title: IDebugEventCallback2 |Microsoft Docs
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
- IDebugEventCallback2
helpviewer_keywords:
- IDebugEventCallback2
ms.assetid: 2c935ee0-2e22-4be0-a852-73736f33c8c9
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2c1e0f6425b6c466d54b6ed24bace0e406e7035d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51792095"
---
# <a name="idebugeventcallback2"></a>IDebugEventCallback2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

這個介面用於偵錯引擎 (DE) 傳送偵錯事件工作階段的偵錯管理員 (SDM)。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugEventCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 會實作這個介面來接收來自偵錯引擎的事件。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 偵錯引擎通常會接收這個介面，當呼叫 SDM [Attach](../../../extensibility/debugger/reference/idebugprogram2-attach.md)，[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)，或[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)。 偵錯引擎藉由呼叫將事件傳送至 SDM[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 下表顯示的方法`IDebugEventCallback2`。  
  
|方法|描述|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)|傳送通知的偵錯事件，以在 SDM。|  
  
## <a name="remarks"></a>備註  
 雖然[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)並[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)指定它們需要`IDebugEventCallback2`介面，這不是，和介面指標一律為 null 的值。 偵錯引擎必須改用`IDebugEventCallback2`介面的呼叫中收到[附加](../../../extensibility/debugger/reference/idebugprogram2-attach.md)，[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)，或[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)。  
  
 如果封裝會實作[IDebugEventCallback](../../../extensibility/debugger/reference/idebugeventcallback2.md) managed 程式碼，它強烈建議您，<xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>要傳遞至不同的介面上叫用[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [核心介面](../../../extensibility/debugger/reference/core-interfaces.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [附加](../../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)

