---
title: 安全性
ms.date: 06/01/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio], applications
- application design, securability
ms.assetid: 7d32c4cf-8bec-4307-a2a8-42f0ceddf3eb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 87e9cb7e9400253713caab17da04c44eb11f5ed1
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843906"
---
# <a name="secure-applications"></a>保護應用程式

開發應用程式時，從設計到部署的所有層面都應該考慮到安全性。 從一開始就應盡可能安全地執行 Visual Studio。 請參閱[使用者權限](../ide/user-permissions-and-visual-studio.md)。

為了協助您有效開發安全的應用程式，您應該對安全性概念和開發平台的安全性功能有基本了解， 而且也應該了解安全性編碼技術。

## <a name="code-for-security"></a>安全性編碼

大部分產生安全性弱點的編碼錯誤，其發生原因是開發人員在處理使用者輸入時做出不正確的假設，或是他們不完全了解其開發中的平台。

- [安全程式碼撰寫方針](/dotnet/standard/security/secure-coding-guidelines)描述設計 .NET 程式碼以搭配使用安全性系統時，可以採用的不同方式。
- [C++ 的安全性最佳做法](/cpp/top/security-best-practices-for-cpp)包含適用於 C++ 開發人員之安全性工具和做法的相關資訊。

## <a name="build-for-security"></a>安全性建置

在建置程序中，安全性也是很重要的考量。 您可以採取一些額外的步驟來提升部署的應用程式安全性，並協助防止未經授權的反向工程、詐騙或其他攻擊：

- [Dotfuscator](dotfuscator/index.md)　為免費，而且有助於保護 .NET 組件不會遭受反向工程和未經授權的使用，例如未經授權的偵錯。
- [強式名稱簽署](managing-assembly-and-manifest-signing.md)可以用來唯一識別軟體元件，並防止名稱詐騙。

## <a name="see-also"></a>另請參閱

- [.NET Framework 中的安全性](/dotnet/standard/security/index)
- [Azure 安全性](/azure/security/)
- [Windows 10 行動裝置版安全性指南](/windows/security/threat-protection/windows-10-mobile-security-guide)
- [Apache Cordova 平台安全性功能](/visualstudio/cross-platform/tools-for-cordova/security/best-practices?view=toolsforcordova-2017)
- [ASP.NET Core 安全性](/aspnet/core/security/?view=aspnetcore-2.1)
- [Windows Forms 安全性](/dotnet/framework/winforms/windows-forms-security)