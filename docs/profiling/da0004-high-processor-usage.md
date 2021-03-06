---
title: DA0004：處理器使用率高 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 87f418c8f145d13dee575c9d45d192a59547e6a0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49920881"
---
# <a name="da0004-high-processor-usage"></a>DA0004：處理器使用率高

|||  
|-|-|  
|規則 ID|DA0004|  
|分類|分析工具使用方式|  
|分析方法|測試設備<br /><br /> 取樣|  
|訊息|處理器使用率持續在 75% 以上。 請考慮為 CPU 繫結應用程式使用取樣模式。|  
|規則型別|資訊|  

 當您使用取樣、.NET 記憶體或資源爭用方法進行分析時，必須至少收集 10 個樣本才能觸發此規則。  

## <a name="cause"></a>原因  
 處理器 (CPU) 使用率在使用檢測方法所收集的分析資料中很高。 分析 CPU 繫結應用程式時，請考慮使用取樣分析方法。  

## <a name="rule-description"></a>規則描述  
 在此分析執行期間，一或多個處理器持續很忙碌。 CPU 使用率過高可能表示是 CPU 繫結應用程式。 檢測的設定檔不是調查 CPU 使用率情節最有效的方式。 當您分析花費許多時間在處理器上執行指令的應用程式時，取樣會更有效率。  

## <a name="how-to-fix-violations"></a>如何修正違規  
 除非您需要函式計時，或者您比較有興趣了解輸入/輸出而不是處理器瓶頸，否則請考慮使用取樣方法而非檢測方法再次分析您的應用程式。