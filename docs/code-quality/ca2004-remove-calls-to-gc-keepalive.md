---
title: CA2004：必須移除對 GC.KeepAlive 的呼叫
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bea4af6c0ae0e21e15a79d52f4c7205a51a3ea46
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49819117"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004：必須移除對 GC.KeepAlive 的呼叫

|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|分類|Microsoft.Reliability|
|中斷變更|非重大|

## <a name="cause"></a>原因
 類別會使用`SafeHandle`但仍會包含呼叫`GC.KeepAlive`。

## <a name="rule-description"></a>規則描述
 如果您要將它轉換成`SafeHandle`使用方式，移除所有呼叫`GC.KeepAlive`（物件）。 在此情況下，類別應該不需要呼叫`GC.KeepAlive`，假設它們沒有完成項但依賴`SafeHandle`完成作業系統控制代碼。  雖然呼叫中保留的成本`GC.KeepAlive`可能不明顯所認知的效能測量，呼叫`GC.KeepAlive`是必要的或足以解決可能不再存在的問題，會讓程式碼更難的存留期維護。

## <a name="how-to-fix-violations"></a>如何修正違規
 移除對呼叫`GC.KeepAlive`。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 只有不是要轉換成正確的技術上來說，您可以隱藏這個警告`SafeHandle`類別中的使用方式。