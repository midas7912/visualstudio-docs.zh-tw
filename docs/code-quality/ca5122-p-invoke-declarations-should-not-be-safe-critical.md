---
title: CA5122 P-Invoke 宣告不可為安全關鍵
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30aea58afe014a4b6e19b32c03c780c129ec479d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896045"
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122 P/Invoke 宣告不可為安全關鍵

|||
|-|-|
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|
|CheckId|CA5122|
|分類|Microsoft.Security|
|中斷變更|中斷|

## <a name="cause"></a>原因
 P/Invoke 宣告已用 <xref:System.Security.SecuritySafeCriticalAttribute>標記：

```csharp
[assembly: AllowPartiallyTrustedCallers]

// ...
public class C
{
    [SecuritySafeCritical]
    [DllImport("kernel32.dll")]
    public static extern bool Beep(int frequency, int duration); // CA5122 - safe critical p/invoke
   }
```

 在此範例中，`C.Beep(...)` 已標記為安全性安全關鍵方法。

## <a name="rule-description"></a>規則描述
 在執行安全性敏感作業時，會將方法標記為 SecuritySafeCritical，但透明程式碼也能安全地使用。 安全性透明度模型的基本規則之一是透明程式碼不可直接透過 P/Invoke 呼叫機器碼。 因此，即使將 P/Invoke 標示為安全性安全關鍵，透明程式碼仍然不能呼叫它，而且會導致安全性分析錯誤。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要讓透明程式碼可以使用 P/Invoke，須公開安全性安全關鍵包裝函式方法：

```csharp
[assembly: AllowPartiallyTrustedCallers

class C
{
   [SecurityCritical]
   [DllImport("kernel32.dll", EntryPoint="Beep")]
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke

   [SecuritySafeCritical]
   public static bool Beep(int frequency, int duration)
   {
      return BeepPInvoke(frequency, duration);
   }
}
```

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。