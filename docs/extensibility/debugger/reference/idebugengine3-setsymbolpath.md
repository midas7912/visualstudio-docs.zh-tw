---
title: IDebugEngine3::SetSymbolPath |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine3::SetSymbolPath
helpviewer_keywords:
- IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 00f493c0c64dc8bc6bef6adff59fff4ce1bcb8c3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49854568"
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
設定要搜尋偵錯符號的路徑。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>參數  
  
|參數|描述|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[in]包含的符號搜尋路徑的字串。 如需詳細資訊，請參閱 < 備註 >。 不可以是 null。|  
|`szSymbolCachePath`|[in]字串，包含可快取符號的本機路徑。 不可以是 null。|  
|`Flags`|[in]不使用;一律設為 0。|  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回 S_OK;否則會傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 字串`szSymbolSearchPath`是一或多個路徑，以搜尋符號分號分隔的清單。 這些路徑可以是本機路徑、 UNC 樣式路徑或 URL。 這些路徑也可以混合不同的類型。 如果路徑是 UNC (例如\\\Symserver\Symbols)，則偵錯引擎應該判斷如果路徑是至符號伺服器，而且應該能夠從該伺服器，它們中所指定之路徑的快取中載入符號`szSymbolCachePath`。  
  
 符號路徑也可以包含一或多個快取位置。 快取中優先順序最高的優先順序快取與先列出，並以分隔 * 符號。 例如:   
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)方法會執行實際載入的符號。  
  
## <a name="see-also"></a>另請參閱  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)