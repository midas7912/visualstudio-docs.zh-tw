---
title: CA1802： 在適當時使用常值 |Microsoft Docs
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
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 25b9c521d55b16cef885c50138bff84c3000e1b3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49940082"
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802：建議在適當時使用常值
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseLiteralsWhereAppropriate|
|CheckId|CA1802|
|分類|Microsoft.Performance|
|中斷變更|非重大|

## <a name="cause"></a>原因
 欄位宣告`static`和`readonly`(`Shared`並`ReadOnly`在[!INCLUDE[vbprvb](../includes/vbprvb-md.md)])，並在編譯時期會計算值進行初始化。

## <a name="rule-description"></a>規則描述
 值`static``readonly`的宣告類型的靜態建構函式呼叫時，將會計算在執行階段的欄位。 如果`static``readonly`欄位會初始化其宣告和靜態建構函式未明確宣告，編譯器會發出的靜態建構函式，將欄位初始化時。

 值`const`欄位會在編譯時期計算並儲存在中繼資料，這樣會增加執行階段效能，它是相較於`static``readonly`欄位。

 因為在編譯時期計算指派給目標欄位的值，將宣告變更為`const`欄位，使在編譯時期而不是在執行階段計算的值。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，取代`static`並`readonly`修飾詞搭配`const`修飾詞。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 很安全隱藏這項規則的警告，或停用規則，如果效能不是問題。

## <a name="example"></a>範例
 下列範例顯示的型別`UseReadOnly`，會違反此規則，並為型別， `UseConstant`，符合規則。

 [!code-csharp[FxCop.Performance.UseLiterals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UseLiterals/cs/FxCop.Performance.UseLiterals.cs#1)]
 [!code-vb[FxCop.Performance.UseLiterals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UseLiterals/vb/FxCop.Performance.UseLiterals.vb#1)]



