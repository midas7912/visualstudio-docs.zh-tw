---
title: CA1303： 不要將傳遞常值為當地語系化的參數 |Microsoft Docs
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
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d900abe23dab4d950b5790798916fe728a44af4a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49886556"
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303：不要將常值當做已當地語系化的參數傳遞
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|分類|Microsoft.Globalization|
|中斷變更|非中斷|

## <a name="cause"></a>原因
 方法將字串常值做為參數的建構函式或方法中的[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]類別庫及字串應該可以當地語系化。

 字串常值當做值傳遞至參數或屬性，且在一或多個下列情況下，則為 true 時，會引發此警告：

-   <xref:System.ComponentModel.LocalizableAttribute>參數或屬性的屬性設定為 true。

-   參數或屬性名稱中包含 「 文字 」、 「 訊息 」，或 「 標題 」。

-   「 值 」 或"format"字串參數傳遞至 Console.Write 或 Console.WriteLine 方法的名稱。

## <a name="rule-description"></a>規則描述
 內嵌在原始程式碼中的字串常值很難進行當地語系化。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，取代字串常值字串的執行個體透過擷取<xref:System.Resources.ResourceManager>類別。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 它是安全的程式碼程式庫不會當地語系化，則字串不會公開給使用者或使用程式碼程式庫的開發人員隱藏此規則的警告。

 使用者可以消除雜訊對方法應該不會被傳送當地語系化的字串重新命名的參數或屬性名稱，或標示為條件的這些項目。

## <a name="example"></a>範例
 下列範例會示範當任一其兩個引數超出範圍時，會擲回例外狀況的方法。 第一個引數，例外狀況的建構函式會違反此規則的常值字串。 第二個引數，建構函式會正確傳遞字串，透過擷取<xref:System.Resources.ResourceManager>。

 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DoNotPassLiterals/cpp/FxCop.Globalization.DoNotPassLiterals.cpp#1)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DoNotPassLiterals/cs/FxCop.Globalization.DoNotPassLiterals.cs#1)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Globalization.DoNotPassLiterals/vb/FxCop.Globalization.DoNotPassLiterals.vb#1)]

## <a name="see-also"></a>另請參閱
 [桌面應用程式中的資源](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)



