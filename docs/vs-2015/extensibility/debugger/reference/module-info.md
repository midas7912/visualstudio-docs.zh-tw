---
title: MODULE_INFO |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 95972779db412ad87883fbb3ba5d4fbbc1ee1cc1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47497124"
---
# <a name="moduleinfo"></a>MODULE_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[MODULE_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-info)。  
  
描述特定模組 （DLL、 EXE 或組件）。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
typedef struct tagMODULE_INFO {   
   MODULE_INFO_FIELDS dwValidFields;  
   BSTR               m_bstrName;  
   BSTR               m_bstrUrl;  
   BSTR               m_bstrVersion;  
   BSTR               m_bstrDebugMessage;  
   UINT64             m_addrLoadAddress;  
   UINT64             m_addrPreferredLoadAddress;  
   DWORD              m_dwSize;  
   DWORD              m_dwLoadOrder;  
   FILETIME           m_TimeStamp;  
   BSTR               m_bstrUrlSymbolLocation;  
   MODULE_FLAGS       m_dwModuleFlags;  
} MODULE_INFO;  
```  
  
```csharp  
public struct MODULE_INFO {   
   public uint     dwValidFields;  
   public string   m_bstrName;  
   public string   m_bstrUrl;  
   public string   m_bstrVersion;  
   public string   m_bstrDebugMessage;  
   public ulong    m_addrLoadAddress;  
   public ulong    m_addrPreferredLoadAddress;  
   public uint     m_dwSize;  
   public uint     m_dwLoadOrder;  
   public FILETIME m_TimeStamp;  
   public string   m_bstrUrlSymbolLocation;  
   public uint     m_dwModuleFlags;  
};  
```  
  
## <a name="members"></a>成員  
 dwValidFields  
 從旗標的組合[MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)列舉，指定哪些欄位都已填寫。  
  
 m_bstrName  
 模組名稱。  
  
 m_bstrUrl  
 模組的 URL。  
  
 m_bstrVersion  
 模組版本。  
  
 m_bstrDebugMessage  
 是選擇性的訊息相關模組，比方說，「 無法載入符號。 」  
  
 m_addrLoadAddress  
 模組載入地址。  
  
 m_addrPreferredLoadAddress  
 模組的慣用的載入位址。  
  
 m_dwSize  
 模組大小。  
  
 m_dwLoadOrder  
 模組的載入順序。  
  
 m_TimeStamp  
 符號檔案上次修改時間。  
  
 m_bstrUrlSymbolLocation  
 符號檔的位置 (例如，"。\\") 指定模組中。 用做為起始的位置來尋找符號的模組。  
  
 m_dwModuleFlags  
 從旗標的組合[MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)說明模組的列舉型別。  
  
## <a name="remarks"></a>備註  
 此結構會傳遞至[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)填滿其中的方法。  
  
 此結構會對應至每個模組中所列**模組**視窗。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [結構和等位](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)   
 [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)
