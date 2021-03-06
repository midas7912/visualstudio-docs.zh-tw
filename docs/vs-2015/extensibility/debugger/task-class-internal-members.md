---
title: Task 類別-內部成員 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines, Task class [.NET Framework]
- Task class [.NET Framework debug engines]
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92ddc4b00f9d8eb37893e1db7ae44802e04e9c46
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51764822"
---
# <a name="task-class---internal-members"></a>工作類別 - 內部成員
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題描述的內部成員<xref:System.Threading.Tasks.Task?displayProperty=fullName>類別可協助您實作自訂的偵錯工具。 如需此類別的一般資訊，請參閱<xref:System.Threading.Tasks.Task>參考主題。  
  
 **命名空間︰** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **組件：** mscorlib （在 mscorlib.dll 中)  
  
 因為您無法從.NET Framework 來存取這些內部成員，下列語法提供通用中繼語言 (CIL)。  
  
## <a name="syntax"></a>語法  
  
```  
.class public auto ansi System.Threading.Tasks.Task  
       extends System.Object  
       implements System.Threading.IThreadPoolWorkItem,  
                  System.IAsyncResult,  
                  System.IDisposable,  
                  System.Threading.ICancelableOperation  
```  
  
## <a name="members"></a>成員  
  
### <a name="methods"></a>方法  
  
|名稱|描述|  
|----------|-----------------|  
|[SetNotificationForWaitCompletion 方法](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|設定或清除 TASK_STATE_WAIT_COMPLETION_NOTIFICATION 狀態位元。|  
|[NotifyDebuggerOfWaitCompletion 方法](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|使用做為中斷點目標偵錯工具的預留位置方法。|  
  
### <a name="fields"></a>欄位  
  
|名稱|描述|  
|----------|-----------------|  
|[m_action 的呼叫](../../extensibility/debugger/m-action-field.md)|委派，表示程式碼中執行<xref:System.Threading.Tasks.Task>物件。|  
|[m_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|儲存的其他屬性<xref:System.Threading.Tasks.Task>物件。|  
|[m_parent](../../extensibility/debugger/m-parent-field.md)|支援欄位<xref:System.Threading.Tasks.Task?displayProperty=fullName>父屬性。|  
|[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|儲存的目前狀態的相關資訊<xref:System.Threading.Tasks.Task>物件。|  
|[m_stateObject](../../extensibility/debugger/m-stateobject-field.md)|物件，表示將動作所使用的資料。|  
|[m_taskId](../../extensibility/debugger/m-taskid-field.md)|支援欄位<xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName>屬性。|  
|[s_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|下一個可用的識別項，如<xref:System.Threading.Tasks.Task>物件。|  
|[TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|表示工作已取消之前它達到執行中狀態，或認可其取消工作，並完成而沒有例外狀況。|  
|[TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|指出工作執行。|  
|[TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|表示工作已完成，因為發生未處理的例外狀況。|  
|[TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|表示工作已順利完成執行。|  
|[TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|表示工作已完成執行其委派，而且在暗中等候附加的子工作完成。|  
  
## <a name="remarks"></a>備註  
 下列的內部方法適合用來偵錯工具引擎因為這些檔案會標示 크 가<xref:System.Threading.Tasks.Task>執行的程式碼：  
  
-   `Execute`  
  
-   `ExecuteEntry`  
  
-   `ExecuteWithThreadLocal`  
  
-   `Finish`  
  
-   `InnerInvoke`  
  
-   `InternalWait`  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 [.NET Framework 適用的平行擴充內部資訊](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)

