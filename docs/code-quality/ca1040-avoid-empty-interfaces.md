---
title: CA1040：避免空的介面
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d5c23a52e65d04b5cc8d147cc0ec3bd7c12bde3c
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548289"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040：避免空的介面

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|類別|Microsoft.Design|
|中斷變更|中斷|

## <a name="cause"></a>原因
 介面不會宣告任何成員或實作兩個或多個其他介面。

## <a name="rule-description"></a>規則描述
 介面是用來定義一組可提供行為或程式使用合約的成員。 不論類型出現在繼承階層架構 (Inheritance Hierarchy) 中的何處，任何類型都可以採用介面所描述的功能。 類型會實作介面，方法是提供介面成員的實作。 空的介面並未定義任何成員。 因此，它不會定義可以實作的合約。

 如果您的設計包含空白預期類型的介面實作，您可能使用介面作為標記或用來識別類型的群組。 如果這個識別會在執行階段，若要完成這項作業的正確方式是使用自訂屬性。 使用存在該屬性中，不存在或屬性的屬性，來識別目標類型。 如果識別必須發生在編譯時期，它可接受使用空的介面。

## <a name="how-to-fix-violations"></a>如何修正違規
 移除介面，或將成員加入至它。 如果空的介面來標示一組型別，取代介面的自訂屬性。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 它可安全地隱藏此規則的警告，介面用來識別在編譯時期的一組型別時。

## <a name="example"></a>範例
 下列範例會顯示空的介面。

 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]