---
title: CA1046： 請勿多載參考類型上的等號比較運算子 |Microsoft Docs
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
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ea32811cfd695e6d55ec635e2e4ea5b4feded05a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49919373"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046：請勿多載參考類型上的等號比較運算子
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|分類|Microsoft.Design|
|中斷變更|中斷|

## <a name="cause"></a>原因
 公用或巢狀公用參考型別多載等號比較運算子。

## <a name="rule-description"></a>規則描述
 對參考類型而言，等號比較運算子的預設實作 (Implementation) 永遠都是正確的。 根據預設，只有當兩項參考都指向相同物件時才會相等。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，移除位在相等運算子的實作。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 它是安全地隱藏此規則的警告，當參考類型的行為類似內建實值型別。 如果是類型的進行加法或減法運算執行個體上的有意義的則可能是類型的正確實作等號比較運算子，並隱藏此違規情形。

## <a name="example"></a>範例
 比較兩個參考時，下列範例會示範預設行為。

 [!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefTypesNoEqualityOp/cs/FxCop.Design.RefTypesNoEqualityOp.cs#1)]

## <a name="example"></a>範例
 下列應用程式會比較某些參考。

 [!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefTypesNoEqualityOp/cs/FxCop.Design.TestRefTypesNoEqualityOp.cs#1)]

 此範例會產生下列輸出。

 **新的 (2 2) 和 b = = 相等的新 (2，2)？否**
**c 和相等嗎？[是]**
**b 和 a = = 嗎？否**
**c 和 a = = 嗎？[是]**
## <a name="related-rules"></a>相關的規則
 [CA1013：多載加號和減號運算子時必須一併多載等號比較運算子](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>另請參閱
 <xref:System.Object.Equals%2A?displayProperty=fullName> [等號比較運算子](http://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)



