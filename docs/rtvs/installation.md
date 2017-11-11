---
title: "安裝 Visual Studio R 工具 | Microsoft Docs"
ms.custom: 
ms.date: 6/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.devlang: r
ms.topic: article
ms.assetid: 3ff60292-1b88-4ee9-b2b2-edd957f1a519
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 712cc780388acc5e373f71d51fc8f1f42adb5bed
ms.openlocfilehash: 8e35c82a5f8583a609e9fccbacb0b27d9c3eac8f
ms.contentlocale: zh-tw
ms.lasthandoff: 07/12/2017

---

# <a name="how-to-install-r-tools-for-visual-studio"></a>如何安裝 Visual Studio R 工具

本主題內容：

- [支援的 Visual Studio 版本](#supported-versions-of-visual-studio)
- [在 Visual Studio 2017 中安裝 RTVS](#installing-rtvs-in-visual-studio-2017)
- [在 Visual Studio 2015 中安裝 RTVS](#installing-rtvs-in-visual-studio-2015)
- [離線安裝](#offline-installation-of-visual-studio-and-rtvs)

> [!Note]
> 安裝 R 工具之後，您可能要設定 Visual Studio 以取得最佳化資料科學家版面配置，如[選項](options.md#data-scientist-layout)主題所述。

## <a name="supported-versions-of-visual-studio"></a>支援的 Visual Studio 版本

Community (免費)、Professional 和 Enterprise 版本的 [Visual Studio 2017](https://www.visualstudio.com/downloads/) 和 [Visual Studio 2015 Update 3 (或更高版本)](http://go.microsoft.com/fwlink/?LinkId=691129) (直接下載) 支援 Visual Studio R 工具 (RTVS)。 

如果您只有產品隨附的 Visual Studio Shell (例如 Visual Studio Test Professional 和 SQL Server Management Studio)，將不會安裝 RTVS。 Visual Studio Shell 缺少 RTVS 的必要元件。


## <a name="installing-rtvs-in-visual-studio-2017"></a>在 Visual Studio 2017 中安裝 RTVS

1. 執行 Visual Studio 安裝程式。 (請參閱[下載](https://www.visualstudio.com/downloads/)，如果您還沒有安裝 Visual Studio。)在 Windows 7 上，請確定您的安裝程式已更新，顯示 Visual Studio 版本 *15.2 組建 26430.12* 或更新版本。

2. 選取 [資料科學與分析應用程式] 工作負載：

    ![VS2017 中的資料科學與分析應用程式工作負載](media/installation-data-science-workload.png)

3. 在相同的工作負載名稱下方，於右側設定任何其他選項。 這個工作負載預設會包括 F# 和 Python 支援。 針對 R，最低需求是 [R 語言支援]、[R 開發工具的執行階段支援] 和 [Microsoft R Client]。

RTVS 會安裝到：`%ProgramFiles(x86)%\Microsoft Visual Studio\<version>\<edition>Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`，其中 `<version>` 一般是 `2017`，而 `<edition>` 是 `Community`、`Professional` 或 `Enterprise`。

## <a name="installing-rtvs-in-visual-studio-2015"></a>在 Visual Studio 2015 中安裝 RTVS

使用 Visual Studio 2015，您需要個別安裝 R 解譯器和 R 工具。

### <a name="install-an-r-interpreter"></a>安裝 R 解譯器

RTVS 需要下列一或多個來源中 R 版本 3.2.1 或更高版本的 64 位元安裝︰

* [Microsoft R Open](https://mran.microsoft.com/download/)
* [Microsoft R Client](https://msdn.microsoft.com/microsoft-r/r-client-get-started)
* [CRAN R](https://cran.r-project.org/bin/windows/base/)

Microsoft R Open 和 CRAN R 都允許多個並行版本。 不過，Microsoft R Client 僅支援一個版本，並且一律會使用您已安裝的最新版本。

### <a name="install-the-r-tools"></a>安裝 R 工具

從 [https://aka.ms/rtvs-current](https://aka.ms/rtvs-current) 下載目前 RTVS。 RTVS 會檢查適合的 Visual Studio 版本，並協助您安裝 R 解譯器 (若尚未安裝)。

RTVS 會安裝在︰`%ProgramFiles(x86)%\Microsoft Visual Studio 14\Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`

## <a name="offline-installation-of-visual-studio-and-rtvs"></a>Visual Studio and RTVS 的離線安裝

離線安裝適用於未連線到網際網路的電腦︰

1. 遵循指示來建立 Visual Studio 版本的離線安裝程式： 

    - [Visual Studio 2017](../install/create-an-offline-installation-of-visual-studio.md)
    - [Visual Studio 2015](https://msdn.microsoft.com/library/mt706497.aspx)

1. 從 [https://aka.ms/rtvs-current-zip](https://aka.ms/rtvs-current-zip) 和 [https://aka.ms/rtvs-remote-zip](https://aka.ms/rtvs-remote-zip) 下載離線 RTVS 安裝程式。 

1. 從離線安裝程式安裝 Visual Studio 和 RTVS。

## <a name="see-also"></a>請參閱

- [開始使用 R](getting-started-with-r.md)
- [R 工具範例專案](getting-started-samples.md)
- [取得協助](getting-started-help.md)
- [選項設定](options.md)
