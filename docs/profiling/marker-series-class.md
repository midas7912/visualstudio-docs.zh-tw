---
title: marker_series 類別 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e638d9316b46a8600fe2e88ca5e4a6611fa1ec4d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843831"
---
# <a name="markerseries-class"></a>marker_series 類別
表示由單一提供者產生之事件的序列通道。  
  
## <a name="syntax"></a>語法  
  
```cpp  
class marker_series;  
```  
  
## <a name="members"></a>成員  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[marker_series::marker_series 建構函式](../profiling/marker-series-marker-series-constructor.md)|初始化 `marker_series` 類別的新執行個體。|  
|[marker_series::~marker_series 解構函式](../profiling/marker-series-tilde-marker-series-destructor.md)|終結 marker_series 物件並釋放所有配置的資源。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[marker_series::is_enabled 方法](../profiling/marker-series-is-enabled-method.md)|判斷是否有任何工作階段啟用該提供者。|  
|[marker_series::write_alert 方法](../profiling/marker-series-write-alert-method.md)|將警示寫入並行視覺化檢視追蹤檔。|  
|[marker_series::write_flag 方法](../profiling/marker-series-write-flag-method.md)|將旗標寫入並行視覺化檢視追蹤檔。|  
|[marker_series::write_message 方法](../profiling/marker-series-write-message-method.md)|將訊息寫入並行視覺化檢視追蹤檔。|  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `marker_series`  
  
## <a name="requirements"></a>需求  
 **標頭：***cvmarkersobj.h*  
  
 **命名空間：** Concurrency::diagnostic  
  
## <a name="see-also"></a>另請參閱  
 [diagnostic 命名空間](../profiling/diagnostic-namespace.md)