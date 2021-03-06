---
title: Visual Studio 系統管理員指南 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
caps.latest.revision: 76
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 25d6655969245adf1b2a28df2b3327561d149983
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51722818"
---
# <a name="visual-studio-administrator-guide"></a>Visual Studio Administrator Guide
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如需 Visual Studio 2017 最新文件，請參閱 < [Visual Studio 2017 系統管理員指南](/visualstudio/install/visual-studio-administrator-guide)。

只要每部目標電腦符合，您可以在網路上部署 Visual Studio 2015[最小安裝需求](http://www.microsoft.com/visualstudio/eng/products/2013-editions)。 您可以使用 /layout 參數執行安裝檔案，來建立網路共用 (述[建立離線安裝 Visual Studio 的](../install/create-an-offline-installation-of-visual-studio.md)頁面)，然後將它從本機電腦，複製到網路共用。 如果您使用 ISO，您就可以掛接 ISO 並共用它或將 ISO 複製到網路共用。  
  
 請注意，從網路共用安裝會「記住」它們的來源位置。 這表示用戶端電腦的修復可能需要回到用戶端原先安裝開始處的網路共用。 請小心選擇網路位置，以便它能與您預期在組織中執行 Visual Studio 2015 用戶端的存留期一致。  
  
## <a name="detection-and-servicing-keys"></a>偵測與服務機碼  
 您可以使用登錄中的偵測子機碼，判斷是否已在電腦上安裝 Visual Studio 產品。 若要判斷是否需要繼續安裝，您會在自動化部署中使用這些偵測機碼。  請參閱[偵測系統需求](../extensibility/internals/detecting-system-requirements.md)[偵測系統需求]。  
  
## <a name="avoiding-reboots"></a>避免重新開機  
 您可以藉由確定您符合適當的 Visual Studio 必要條件，然後再部署 Visual Studio，來減少重新開機。 適用於.NET Framework 中，您可能需要重新啟動電腦均執行 Windows 8，如果您 Visual Studio 2015 上部署，但是未先安裝.NET Framework 4.6。  
  
 針對 Windows 和 Android 裝置模擬，如果您還沒有開啟 Hyper-V 這項 Windows 功能，您可能需要重新啟動電腦。 針對 Web 程式開發，如果您還沒有開啟 Web 伺服器這項 Windows 功能，您可能需要重新啟動電腦。 針對 Office 程式開發，如果您還沒有開啟 Windows Identify Foundation 這項 Windows 功能，您可能需要重新啟動電腦。 如果您還沒有開啟 Web 伺服器這項 Windows 功能，請重新啟動電腦。 針對 Office 程式開發，如果您還沒有開啟 Windows Identify Foundation 這項 Windows 功能，您可能需要重新啟動電腦。 若要進一步了解如何自動偵測和安裝 Windows 功能，請參閱 [在執行 Windows Server 2008 R2 的 Server Core 安裝的伺服器上安裝伺服器角色](https://technet.microsoft.com/library/ee441260(v=ws.10).aspx)。  
  
## <a name="error-return-codes"></a>錯誤傳回碼  
 下表列出重要的錯誤碼。 您可以在自動化中使用這些錯誤碼，判斷是否需要重新開機，以及安裝是否成功。 如果您收到錯誤代碼，考量的疑難排解步驟[安裝 Visual Studio](../install/install-visual-studio-2015.md)頁面。  
  
|設定狀態|不需要重新啟動|必須重新啟動|描述|  
|------------------|--------------------------|----------------------|-----------------|  
|成功|0x00000000 [0]|0x00000bc2 [3010]|安裝成功。|  
|區塊|0x80044000 [-2147205120]|0x8004C000 [-2147172352]|如果要報告的唯一區塊是「重新開機暫止」，則傳回值為「未完成 - 需要重新開機」值 (0x80048bc7)。|  
|取消|0x00000642 [1602]|0x80048642 [-2147187134]|傳回重新開機值時，傳回碼為 1602。|  
|未完成 - 需要重新開機|N/A|0x80048bc7 [-2147185721]|必須先重新啟動，才能繼續安裝。|  
|失敗|0x00000643 [1603]|0x80048643 [-2147187133]|傳回重新開機值時，傳回碼為 1603。|  
  
## <a name="interactive-administrator-installer"></a>互動式的系統管理員安裝程式  
 如果您正在 Visual Studio 安裝之上建立互動式安裝程式，您可以從 Visual Studio 安裝程式檢視進度。 Visual Studio 2015 安裝程式是根據開放原始碼 Windows Installer XML (WiX) chainer 技術建置，也稱為 "burn"。 burn 這項技術支援兩種通訊協定：burn 和 netfx4。 如需簡短的參考，請參閱在 [wixtoolset.org](http://wixtoolset.org/)的 ExePackage 項目文件中的 Protocol 屬性描述。可能需要檢閱此 Protocol 屬性的 WiX 開放原始碼實作以進行整合。  
  
## <a name="controlling-what-is-installed"></a>控制安裝哪些元件  
 如果您想要控制您的使用者可以安裝的元件，有兩個選項：系統管理員檔案安裝和命令列選項。 如果您的目標是限制使用者可以從 Visual Studio 安裝程式經驗選擇的內容，請選取系統管理員檔案安裝。 如果您想要建立初始設定，但允許使用者選擇他們自己的 Visual Studio 安裝程式經驗，請選取命令列參數。  
  
 如需系統管理員檔案經驗的詳細資訊，請參閱 [How to: Create and Run an Unattended Installation of Visual Studio](../install/how-to-create-and-run-an-unattended-installation-of-visual-studio.md) 和 [How to: Automatically apply product keys when deploying Visual Studio](../install/how-to-automatically-apply-product-keys-when-deploying-visual-studio.md)。  如需有關命令列控制項的詳細資訊，請參閱 <<c0> [ 使用命令列參數安裝 Visual Studio](../install/use-command-line-parameters-to-install-visual-studio.md)頁面。  
  
## <a name="specifying-customer-feedback-settings"></a>指定客戶回函設定  
 根據預設，Visual Studio 的安裝已啟用客戶回函。 您可以設定 Visual Studio 來將下列登錄機碼的值變更為字串 "0"，在個別電腦上停用客戶回函。  
  
 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM**  
**OptIn**  
  
 (例如，將其變更為 HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM OptIn="0")  
  
## <a name="related-topics"></a>相關主題  
  
|主題|描述|  
|-----------|-----------------|  
|[如何：安裝特定版本的 Visual Studio](../install/how-to-install-a-specific-release-of-visual-studio.md)|描述如何安裝最新版的特定組態[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。|  
|[如何：建立和執行 Visual Studio 的自動安裝](../install/how-to-create-and-run-an-unattended-installation-of-visual-studio.md)|描述如何安裝[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]以自動模式。|  
|[如何：部署 Visual Studio 時會自動套用產品金鑰](../install/how-to-automatically-apply-product-keys-when-deploying-visual-studio.md)|描述如何部署到多部電腦時套用產品金鑰。|  
|[說明檢視器系統管理員指南](../ide/help-viewer-administrator-guide.md)|提供有關如何管理本機說明安裝有或沒有網際網路存取的網路環境的資訊。|  
|[安裝 Visual Studio](../install/install-visual-studio-2015.md)|提供指示與連結主題會說明如何安裝[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。|