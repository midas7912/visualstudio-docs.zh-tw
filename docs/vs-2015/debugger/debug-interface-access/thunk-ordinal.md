---
title: THUNK_ORDINAL |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Thunk_Ordinal enumeration
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f670656eb1ffe610b81ae8e549e04b6fb8919a62
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733945"
---
# <a name="thunkordinal"></a>THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

將指定的 thunk 類型。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## <a name="elements"></a>項目  
 THUNK_ORDINAL_NOTYPE  
 標準的 thunk。  
  
 THUNK_ORDINAL_ADJUSTOR  
 A `this` adjustor thunk。  
  
 THUNK_ORDINAL_VCALL  
 虛擬呼叫 thunk。  
  
 THUNK_ORDINAL_PCODE  
 P-程式碼 thunk。  
  
 THUNK_ORDINAL_LOAD  
 延遲載入 thunk。  
  
 THUNK_ORDINAL_TRAMP_INCREMENTAL  
 累加 trampoline thunk （trampoline thunk 用來從一個記憶體空間的呼叫退回到另一個）。  
  
 THUNK_ORDINAL_TRAMP_BRANCHISLAND  
 分支點 trampoline thunk。  
  
## <a name="remarks"></a>備註  
 這個列舉型別中的值會傳回呼叫[idiasymbol:: Get_thunkordinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)方法。  
  
## <a name="requirements"></a>需求  
 標頭： cvconst.h  
  
## <a name="see-also"></a>另請參閱  
 [列舉和結構](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)



