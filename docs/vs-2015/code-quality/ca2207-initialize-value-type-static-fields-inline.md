---
title: CA2207： 必須初始化實值類型的靜態欄位內嵌 |Microsoft Docs
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
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d2833e14c941ae4d2ac6c16f8f5abf625f430de9
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49890592"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207：必須初始化實值類型的靜態欄位內嵌
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|分類|Microsoft.Usage|
|中斷變更|非中斷|

## <a name="cause"></a>原因
 實值型別宣告明確靜態建構函式。

## <a name="rule-description"></a>規則描述
 實值型別宣告時，它會進行預設初始化，其中所有的實值型別欄位設定為零，而所有參考型別欄位都設定為`null`(`Nothing` Visual Basic 中)。 明確的靜態建構函式只保證對執行個體建構函式之前執行，或呼叫靜態成員的型別。 因此，如果型別建立而不需要呼叫的執行個體建構函式時，靜態建構函式執行不保證。

 如果是初始化的內嵌的所有靜態資料，而且宣告明確的靜態建構函式，C# 和 Visual Basic 編譯器會新增`beforefieldinit`MSIL 類別定義的旗標。 編譯器也會加入私用靜態建構函式，其中包含靜態初始設定程式碼。 保證此私用靜態建構函式執行之前存取類型的任何靜態欄位。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形時宣告，因此移除靜態建構函式初始化所有靜態資料。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

## <a name="related-rules"></a>相關的規則
 [CA1810：必須初始化參考類型內部的靜態欄位](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)



