---
title: IDebugPortSupplier3::EnumPersistedPorts |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d1bb9348c0dfae477d0c306868991acd13e7a487
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49856050"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
這個方法會擷取物件，可讓持續性的連接埠清單的列舉型別。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>參數  
 `PortNames`  
 [in]A [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)結構，其中包含一份以尋找並傳回在持續性的連接埠之間的連接埠名稱。 只有這些持續性連接埠使用這些名稱將會傳回。  
  
 `ppEnum`  
 [out]物件，實作[IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)介面。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 連接埠提供者會具現化，並儲存連接埠提供者時終結時，會載入保存的連接埠。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)