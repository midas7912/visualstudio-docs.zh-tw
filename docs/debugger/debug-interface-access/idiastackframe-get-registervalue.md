---
title: 'Idiastackframe:: Get_registervalue |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_registerValue method
ms.assetid: cbe3d8ac-319a-40ac-bc3e-4eb81b2d7807
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7799316a933e5f021df78699e41e6e9483746575
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49845949"
---
# <a name="idiastackframegetregistervalue"></a>IDiaStackFrame::get_registerValue
擷取的值指定的暫存器儲存在堆疊框架中。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT get_registerValue(  
   ULONG      registerIndex,  
   ULONGLONG *pRetVal  
);  
```  
  
#### <a name="parameters"></a>參數  
 `registerIndex`  
 [in]其中一個[CV_HREG_e 列舉](../../debugger/debug-interface-access/cv-hreg-e.md)列舉值。  
  
 `pRetVal`  
 [out]在登錄中儲存的值。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`，否則會傳回錯誤碼。  
  
## <a name="see-also"></a>另請參閱  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [CV_HREG_e 列舉](../../debugger/debug-interface-access/cv-hreg-e.md)