---
title: "維護性警告 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 88199541fe5d3c4be3f9f1cff6de308d45d0d85a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2017
---
# <a name="maintainability-warnings"></a>維護性警告
維護性警告支援程式庫和應用程式維護。  
  
## <a name="in-this-section"></a>本章節內容  
  
|規則|說明|  
|----------|-----------------|  
|[CA1500：變數名稱不應該與欄位名稱相符](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|執行個體方法宣告的參數或區域變數，其名稱符合宣告的型別，會導致發生錯誤的執行個體欄位。|  
|[CA1501：避免在物件間過度繼承](../code-quality/ca1501-avoid-excessive-inheritance.md)|類型在其繼承階層架構 (Inheritance Hierarchy) 中超過四個層級的深度。 太深的巢狀類型階層架構可能會難以依循、了解和維護。|  
|[CA1502：避免造成過度複雜的方法](../code-quality/ca1502-avoid-excessive-complexity.md)|這個規則會測量整個方法中線性獨立路徑的數目，此數目是由條件分支的數目與複雜度決定。|  
|[CA1504：必須檢閱可能造成誤導的欄位名稱](../code-quality/ca1504-review-misleading-field-names.md)|執行個體欄位名稱開頭為"s_"或靜態的名稱 (在中共用[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 欄位開頭為"m_"。|  
|[CA1505：應避免撰寫無法維護的程式碼](../code-quality/ca1505-avoid-unmaintainable-code.md)|類型或方法的維護性指標值很低。 維護性指標很低代表類型或方法很可能會難以維護，而應該列為需要重新設計的候選目標。|  
|[CA1506：應避免使用結合過度的類別](../code-quality/ca1506-avoid-excessive-class-coupling.md)|這個規則會測量類別的耦合，方法是計算類型或方法包含的唯一類型參考數目。|  
  
## <a name="see-also"></a>另請參閱  
 [測量 Managed 程式碼的複雜度和維護性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)