---
title: 匯入發行設定以發行至 IIS
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6df935578955d3c72b6f4fa61efdf614229bca0
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2018
ms.locfileid: "38808461"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>在 Visual Studio 中匯入發行設定，即可將應用程式發行至 IIS

您可以使用 [發行] 工具匯入發行設定，然後部署您的應用程式。 在本文中，我們會使用 IIS 的發行設定，但您可以使用類似步驟匯入 [Azure App Service](../deployment/tutorial-import-publish-settings-azure.md) 的發行設定。 在某些情況下，使用發行設定的設定檔速度，比起針對每個 Visual Studio 安裝手動設定 IIS 部署還要快。

這些步驟適用於 Visual Studio 中的 ASP.NET、ASP.NET Core 和 .NET Core 應用程式。 這些步驟對應於 Visual Studio 2017 15.6 版。

在本教學課程中，您將進行下列作業：

> [!div class="checklist"]
> * 設定 IIS，讓您能夠產生發行設定檔案
> * 建立發行設定檔案
> * 將發行設定檔案匯入至 Visual Studio
> * 將應用程式部署至 IIS

發行設定檔案 (*\*.publishsettings*) 不同於 Visual Studio 中建立的發行設定檔 (*\*.pubxml*)。 發行設定檔案是由 IIS 或 Azure App Service 所建立，或者可以手動方式建立，並可匯入至 Visual Studio 中。

> [!NOTE]
> 如果您只需要從某個 Visual Studio 安裝將 Visual Studio 發行設定檔 (\*.pubxml 檔案) 複製到另一個 Visual Studio 安裝，您可以在受控專案類型的 \\<專案名稱\>\Properties\PublishProfiles 資料夾中找到發行設定檔 \<設定檔名稱\>.pubxml。 針對網站，請查看 *\App_Data* 資料夾底下的內容。 發行設定檔是 MSBuild XML 檔案。

## <a name="prerequisites"></a>必要條件

* 您必須安裝 Visual Studio 2017，以及 **ASP.NET** 和 **NET Framework** 開發工作負載。 針對 .NET Core 應用程式，您還需要 .**NET Core** 工作負載。

    如果您尚未安裝 Visual Studio，請前往 [Visual Studio 下載](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)頁面免費進行安裝。

* 若要從 IIS 產生發行設定檔案，您必須具備執行 Windows Server 2012 或 Windows Server 2016 的電腦，並且必須正確設定 IIS 網頁伺服器角色。 另外還必須安裝 ASP.NET 4.5 或 ASP.NET Core。 針對 ASP.NET Core，請參閱[發行至 IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)。 針對 ASP.NET 4.5，請參閱[使用 ASP.NET 3.5 和 ASP.NET 4.5 的 IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>在 Visual Studio 中建立新的 ASP.NET 專案

1. 在執行 Visual Studio 的電腦上，選擇 [檔案] > [新增專案]。

1. 在 [Visual C#] 或 [Visual Basic] 底下，選擇 [Web]，然後在中間窗格中選擇 [ASP.NET Web 應用程式 (.NET Framework)] 或 (僅限於 C#) [ASP.NET Core Web 應用程式]，然後按一下 [確定]。

    如果您沒有看到特定的專案範本，請在 [新增專案] 對話方塊的左窗格中，按一下 [開啟 Visual Studio 安裝程式] 連結。 Visual Studio 安裝程式即會啟動。 請參閱本文中的必要條件，以識別您必須安裝的必要 Visual Studio 工作負載。

1. 選擇 [MVC] (.NET Framework) 或 [Web 應用程式 (Model-View-Controller)] (適用於 .NET Core)，並確定已選取 [不需要驗證]，然後按一下 [確定]。

1. 鍵入 **MyWebApp** 這類名稱，然後按一下 [確定]。

    Visual Studio 會建立專案。

1. 選擇 [建置] > [建置方案] 來建置專案。

## <a name="install-and-configure-web-deploy-on-windows-server"></a>在 Windows Server 上安裝並設定 Web Deploy

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>在 Windows Server 上的 IIS 中建立發行設定檔案

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>在 Visual Studio 中匯入發行設定並進行部署

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

應用程式部署成功之後，它應該會自動啟動。 如果沒有從 Visual Studio 啟動，請在 IIS 中啟動該應用程式。 針對 ASP.NET Core，您必須先確定**DefaultAppPool** 的 [應用程式集區] 欄位設定為 [沒有受控程式碼]。

## <a name="next-steps"></a>後續步驟

在本教學課程中，您已建立發行設定檔案、將其匯入至 Visual Studio 中，並已將 ASP.NET 應用程式部署至 IIS。 您可能需要 Visual Studio 中的其他發行選項概觀。

> [!div class="nextstepaction"]
> [第一眼部署](../deployment/deploying-applications-services-and-components.md)
