---
title: 註釋結構和類別 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 965a823c658516edf247f6a99d23d189097b31f0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51801466"
---
# <a name="annotating-structs-and-classes"></a>註釋結構和類別
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以使用作用類似非變異項目的註釋來標註結構和類別，在包含封入結構做為參數或結果值的任何函式呼叫或函式進入/結束點，會假定這些註釋為真。  
  
## <a name="struct-and-class-annotations"></a>結構和類別的註解  
  
-   `_Field_range_(low, high)`  
  
     欄位是在範圍中 （含） 從`low`至`high`。  相當於使用適當的前置或後置條件套用至已標註物件的 `_Satisfies_(_Curr_ >= low && _Curr_ <= high)`。  
  
-   `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`  
  
     欄位，其可寫入的大小是由 `size` 以項目 (或位元組) 為單位指定。  
  
-   `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`  
  
     欄位，其可寫入的大小是由 `size` 以項目 (或位元組) 為單位指定，而且可以讀取這些項目 (位元組) 的 `count`。  
  
-   `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`  
  
     具有可讀取及可寫入大小的欄位，其大小是以 `size` 所指定的項目 (或位元組) 為單位表示。  
  
-   `_Struct_size_bytes_(size)`  
  
     具有可讀取及可寫入大小的欄位，其大小是以 `size` 所指定的項目 (或位元組) 為單位表示。  
  
     適用於結構或類別的宣告。  指出該類型的有效物件可能大於所宣告的類型，其位元組數目是由 `size` 所指定。  例如:   
  
    ```cpp  
  
    typedef _Struct_size_bytes_(nSize)  
    struct MyStruct {  
        size_t nSize;  
        …  
    };  
  
    ```  
  
     緩衝區大小，以位元組為單位的參數`pM`型別的`MyStruct *`便會進入是：  
  
    ```cpp  
    min(pM->nSize, sizeof(MyStruct))  
    ```  
  
## <a name="see-also"></a>另請參閱  
 [使用 SAL 註釋減少 C/c + + 程式碼的缺失](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [了解 SAL](../code-quality/understanding-sal.md)   
 [註釋函式參數和傳回值](../code-quality/annotating-function-parameters-and-return-values.md)   
 [註釋函式行為](../code-quality/annotating-function-behavior.md)   
 [註釋鎖定行為](../code-quality/annotating-locking-behavior.md)   
 [指定套用註釋的時機和位置](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [內建函式](../code-quality/intrinsic-functions.md)   
 [最佳做法和範例](../code-quality/best-practices-and-examples-sal.md)



