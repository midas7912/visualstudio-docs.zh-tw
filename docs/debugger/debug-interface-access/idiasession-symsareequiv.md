---
title: 'Idiasession:: Symsareequiv |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bdaa1ab070b6d95af0f28f5bdaa005b9ac808766
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49850980"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
檢查兩個符號是否相等。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### <a name="parameters"></a>參數  
 `symbolA`  
 [in]第一個[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)用於比較的物件。  
  
 `symbolB`  
 [in]第二個`IDiaSymbol`用於比較的物件。  
  
## <a name="return-value"></a>傳回值  
 如果符號相等，則會傳回`S_OK`; 否則傳回`S_FALSE`，符號不相等。 否則，傳回錯誤碼。  
  
## <a name="see-also"></a>另請參閱  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)