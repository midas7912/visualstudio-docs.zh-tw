---
title: CA1005：避免在泛型類型上包含過多參數
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e65427aecb2d4ecc135480d23834fdc07a413b05
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49850122"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005：避免在泛型類型上包含過多參數

|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|分類|Microsoft.Design|
|中斷變更|中斷|

## <a name="cause"></a>原因
 外部可見的泛型型別有兩個以上的型別參數。

## <a name="rule-description"></a>規則描述
 泛型類型所包含的型別參數越多，就越難了解並記住每個型別參數所代表的含意。 通常具有一個型別參數，如下所示顯然`List<T>`，並在某些情況下，具有兩個類型參數，如下所示`Dictionary<TKey, TValue>`。 如果兩個以上的型別參數存在，都會變得難以太適合大部分的使用者 (例如`TooManyTypeParameters<T, K, V>`C# 中或`TooManyTypeParameters(Of T, K, V)`在[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，變更設計，以使用不超過兩個類型參數。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告，除非絕對需要設計的兩個以上的型別參數。 提供了容易了解和使用的語法中的泛型減少時間，才能了解，並增加新的程式庫的採用率。

## <a name="related-rules"></a>相關的規則
 [CA1010：集合應該實作泛型介面](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000：不要在泛型型別上宣告靜態成員](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002：不要公開泛型清單](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006：不要在成員簽章中巢狀化泛型類型](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004：泛型方法應該提供類型參數](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003：必須使用一般事件處理常式執行個體](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007：建議在適當時使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>另請參閱
 [泛型](/dotnet/csharp/programming-guide/generics/index)