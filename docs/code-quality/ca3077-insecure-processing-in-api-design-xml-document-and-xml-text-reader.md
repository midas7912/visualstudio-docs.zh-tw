---
title: CA3077：API 設計、XML 文件和 XML 文字讀取器中的不安全處理
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c8d90883f2aac5389ec0787fee08749da363e747
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49821951"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077：API 設計、XML 文件和 XML 文字讀取器中的不安全處理

|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|分類|Microsoft.Security|
|中斷變更|非中斷|

## <a name="cause"></a>原因
 針對衍生自 XMLDocument 和 XMLTextReader 的 API 進行設計時，請留意 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>。  若在參考或解析外部實體來源時使用不安全的 DTDProcessing 執行個體，或在 XML 中設定不安全的值，都可能會導致資訊洩漏。

## <a name="rule-description"></a>規則描述
 *文件類型定義 (DTD)* 是  [World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)中針對 XML 剖析器用來判斷文件有效性所定義之兩種方式的其中一種。 此規則會搜尋已接受不受信任之資料的屬性和執行個體，藉此警告開發人員潛在的 [Information Disclosure](/dotnet/framework/wcf/feature-details/information-disclosure) 威脅，這些威脅可能會導致 [Denial of Service (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) 攻擊。 下列情況會觸發此規則：

- <xref:System.Xml.XmlDocument> 或<xref:System.Xml.XmlTextReader>類別針對 DTD 處理會使用預設解析程式的值。

- 未針對 XmlDocument 或 XmlTextReader 衍生的類別定義任何建構函式，或在 <xref:System.Xml.XmlResolver>中使用不安全的值。

## <a name="how-to-fix-violations"></a>如何修正違規

- 可以攔截並處理所有 XmlTextReader 例外狀況，正確地以避免路徑資訊外洩。

- 使用<xref:System.Xml.XmlSecureResolver>而不是 XmlResolver，以限制 XmlTextReader 可以存取的資源。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 如果您無法確定輸入是否來自受信任的來源，請不要隱藏這個警告的規則。

## <a name="pseudo-code-examples"></a>虛擬程式碼範例

### <a name="violation"></a>違規

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass () {} // warn
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2() // warn
        {
        }
    }
}
```

### <a name="solution"></a>方案

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass ()
        {
            XmlResolver = null;
        }
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2()
        {
               XmlResolver = null;
        }
    }
}
```