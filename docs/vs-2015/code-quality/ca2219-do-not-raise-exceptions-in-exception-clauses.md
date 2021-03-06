---
title: CA2219： 不要引發例外狀況子句中的例外狀況 |Microsoft Docs
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
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2b5f08043985b6a2eb2b5fe0267fefb58ad00587
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891176"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219：不要在 exception 子句中引發例外狀況
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|分類|Microsoft.Usage|
|中斷變更|非中斷、 中斷|

## <a name="cause"></a>原因
 發生例外狀況從`finally`，篩選或 fault 子句。

## <a name="rule-description"></a>規則描述
 當例外狀況子句中引發例外狀況時，它會大幅增加偵錯困難的度。

 在引發例外狀況時`finally`或 fault 子句中，新的例外狀況會隱藏作用中的例外狀況，如果有的話。 這可讓原錯誤更難以偵測及偵錯。

 Filter 子句中引發例外狀況時，執行階段以無訊息模式攔截到例外狀況，並會導致篩選條件評估為 false。 沒有任何方法來告知的篩選條件評估為 false，並從篩選條件擲回之例外狀況的差異。 這可讓您難以偵測及偵錯中篩選條件的邏輯錯誤。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此違規的此規則，不要明確地引發的例外狀況`finally`，篩選或 fault 子句。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏這項規則的警告。 沒有在其下的例外狀況子句中引發例外狀況提供執行的程式碼的好處的案例。

## <a name="related-rules"></a>相關的規則
 [CA1065：不要在非預期的位置中引發例外狀況](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>另請參閱
 [設計警告](../code-quality/design-warnings.md)



