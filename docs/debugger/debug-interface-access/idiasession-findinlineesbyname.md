---
title: IDiaSession::findInlineesByName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 9860336d-f703-4ecb-bfc4-3f5beb175a76
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47d01237d7e2235f2d50e82a8fd599384e930d2c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896259"
---
# <a name="idiasessionfindinlineesbyname"></a>IDiaSession::findInlineesByName
擷取列舉型別，可讓用戶端來逐一查看所有符合指定之名稱的內嵌函式行號資訊。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT findInlineesByName (   
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>參數  
 `name`  
 [in]指定要用於比較的名稱。  
  
 `option`  
 [in]指定套用至搜尋名稱的比較選項。 從數值[NameSearchOptions 列舉](../../debugger/debug-interface-access/namesearchoptions.md)單獨或合併，就可以使用列舉型別。  
  
 `ppResult`  
 [out]傳回[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)物件，其中包含一份已擷取的行號。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="see-also"></a>另請參閱  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 列舉](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)