---
title: 私用組件庫 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSIX galleries, private
- private galleries, VSIX
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e91b3ecec969ab6a717598d8dfb77e674890216a
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2018
ms.locfileid: "39638579"
---
# <a name="private-galleries"></a>私用組件庫
您可以共用控制項、 範本和工具，您藉由公佈到開發*私用組件庫*內部為您的組織，如下所示：  
  
-   建立 Atom (RSS) 摘要您的內部網路上的適當設定中央位置 （儲存機制）。 如需詳細資訊，請參閱 <<c0> [ 如何： 建立私用組件庫摘要的 Atom](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md)。  
  
-   散發 *.pkgdef*描述私用組件庫的檔案。 我們建議此組態的系統管理員想要連線到多部電腦的私用組件庫，在相同的時間。  
  
## <a name="add-a-private-gallery-to-extensions-and-updates-in-visual-studio"></a>加入擴充功能和更新 Visual Studio 中的私用組件庫  
 使用私用組件庫時，您可以將它加入**擴充功能和更新**Visual Studio 中。  
  
 ![擴充管理員新增對話方塊](../extensibility/media/em_adddialog.png "EM_AddDialog")  
  
### <a name="to-add-a-private-gallery-to-extensions-and-updates"></a>將私用資源庫新增至擴充功能和更新  
  
1.  在功能表列上選擇 [工具] > [選項]。  
  
2.  在 **環境**節點中，選取**擴充功能和更新**。  
  
3.  選擇 [ **加入** ] 按鈕。  
  
4.  在 **名稱**欄位中，輸入私人資源庫的名稱，例如`My Gallery`。  
  
5.  在  **URL**欄位中，輸入 Atom 摘要或裝載私人資源庫的 SharePoint 網站的 URL。  
  
    1.  如果主機是 Atom 摘要連接至私用組件庫中，URL 會類似這個的其中一個： http://www.mywebsite/mygallery/atom.xml。  此 URL 可以參考到檔案或網路路徑。  
  
    2.  如果主機是在 SharePoint 網站，URL 會類似這個的其中一個： http://mysharepoint/sites/mygallery/forms/AllItems.aspx。  
  
### <a name="manage-private-galleries"></a>管理私人組件庫  
 系統管理員可以將私用組件庫提供給多部電腦同時修改每一部電腦的系統登錄。 若要達成此目的，建立 *.pkgdef*描述新的登錄機碼和其值的檔案。  此檔案的格式如下所示。  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 如需詳細資訊，請參閱 <<c0> [ 如何： 使用登錄設定管理私用組件庫](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md)。  
  
## <a name="install-extensions-from-a-private-gallery"></a>從私用組件庫中安裝擴充功能  
 您可以搜尋並安裝 Visual Studio 擴充功能私用資源庫中從**擴充功能和更新**。 下列步驟會使用名為私用組件庫`My Gallery`。  
  
 ![安裝私人組件庫的延伸模組管理員](../extensibility/media/em_.png "EM_")  
  
### <a name="to-search-for-and-install-extensions-from-a-private-gallery"></a>若要搜尋並安裝延伸模組從私用組件庫  
  
1.  在功能表列上選擇 **工具** > **擴充功能和更新**。  
  
2.  在左窗格中，選取**線上擴充功能**，然後選取**我的資源庫**。  
  
3.  在右窗格中，選取 [擴充功能，，然後選擇**下載**] 按鈕。  
  
## <a name="update-extensions-from-a-private-gallery"></a>從私用組件庫的更新延伸模組  
 張貼新版本的 Visual Studio 擴充功能私用組件庫中，您可以更新您已安裝的擴充功能。 下列步驟會使用名為私用組件庫`My Repository`。  
  
 ![延伸模組管理員私用組件庫更新](../extensibility/media/em_update.png "EM_Update")  
  
### <a name="to-update-an-installed-extension-from-a-private-gallery"></a>若要更新已安裝的延伸模組從私用組件庫  
  
1.  在功能表列上選擇 **工具** > **擴充功能和更新**。  
  
2.  在左窗格中，選取**更新**，然後選取**我的存放庫**。  
  
3.  在右窗格中，選取 [擴充功能，，然後選擇**更新**] 按鈕。  
  
## <a name="see-also"></a>另請參閱  
 [尋找及使用 Visual Studio 擴充功能](../ide/finding-and-using-visual-studio-extensions.md)   
 [提供 Visual Studio 擴充功能](../extensibility/shipping-visual-studio-extensions.md)