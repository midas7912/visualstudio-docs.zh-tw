---
title: MACHINE_INFO |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MACHINE_INFO
helpviewer_keywords:
- MACHINE_INFO structure
ms.assetid: e7564ff2-00b5-4750-8fd5-dc1029a16912
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e548552b5acda6a3334b6d7df90b2aeab80c2e77
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49847223"
---
# <a name="machineinfo"></a>MACHINE_INFO
描述特定的電腦。  
  
## <a name="syntax"></a>語法  
  
```cpp  
typedef struct tagMACHINE_INFO {   
   MACHINE_INFO_FIELDS Fields;  
   BSTR                bstrName;  
   MACHINE_INFO_FLAGS  Flags;  
} MACHINE_INFO;  
```  
  
```csharp  
public struct MACHINE_INFO {   
   public uint   Fields;  
   public string bstrName;  
   public uint   Flags;  
};  
```  
  
## <a name="members"></a>成員  
 `Fields`  
 從旗標的組合[MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)指定結構的哪些欄位會初始化的列舉型別。  
  
 `bstrName`  
 電腦名稱。 相當於呼叫[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)。  
  
 `Flags`  
 從旗標的組合[MACHINE_INFO_FLAGS](../../../extensibility/debugger/reference/machine-info-flags.md)說明機器屬性的列舉型別。  
  
## <a name="remarks"></a>備註  
 此結構由呼叫[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)方法。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [結構和等位](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)   
 [GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)