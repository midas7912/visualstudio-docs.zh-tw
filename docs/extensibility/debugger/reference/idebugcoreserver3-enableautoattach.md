---
title: IDebugCoreServer3::EnableAutoAttach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e5fc3ab0767a7077860c82acefc9554ba1228cee
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49831116"
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
可讓自動附加指定的偵錯引擎。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```csharp  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
);  
```  
  
#### <a name="parameters"></a>參數  
 `rgguidSpecificEngines`  
 [in]每個偵錯引擎將標示為自動附加 Guid 的陣列。  
  
 `celtSpecificEngines`  
 [in]中指定的引擎數`rgguidSpecificEngines`。  
  
 `pszStartPageUrl`  
 [in]若要使用自動附加時起始的 URL。  
  
 `pbstrSessionID`  
 [out]已自動附加的工作階段識別碼。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則會傳回錯誤碼。 一個錯誤碼是`E_AUTO_ATTACH_NOT_REGISTERED`，這表示尚未註冊 auto-attach class factory。  
  
## <a name="remarks"></a>備註  
 使用指定的 URL 相關聯的程式啟動時，將指定的偵錯引擎會自動啟動和附加。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)