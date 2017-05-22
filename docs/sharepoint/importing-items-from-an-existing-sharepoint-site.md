---
title: "從現有的 SharePoint 網站匯入項目"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.WSPImport.SelectionDependency"
  - "VS.SharepointTools.WSPImport.SpecifyProjectSource"
  - "VS.SharePointTools.WSPImport.SelectionItemsToImport"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "匯入項目 [Visual Studio 中的 SharePoint 開發]"
  - "Visual Studio 中的 SharePoint 開發, 匯入 .wsp 檔案"
  - "Visual Studio 中的 SharePoint 開發, 匯入項目"
ms.assetid: b1012eb8-5927-4522-9475-72f0ba55fcca
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 從現有的 SharePoint 網站匯入項目
  匯入 SharePoint 方案套件專案範本可讓您在新的 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 方案中，重複使用來自現有 SharePoint 網站的項目，例如內容類型和欄位。 雖然您可以執行大部分匯入的方案而不需修改，仍有特定限制和問題需要考量，特別是您在匯入後修改任何項目的話。  
  
> [!NOTE]  
>  若要匯入可重複使用的工作流程，請使用「匯入可重複使用的工作流程」專案範本。[!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [匯入可重複使用之工作流程的方針](../sharepoint/guidelines-for-importing-reusable-workflows.md).  
  
## 支援的 SharePoint 方案  
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] 完全支援匯入在 [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 和 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 中建立的方案。  
  
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] 不支援匯入在下列應用程式中建立的方案：  
  
-   [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)]  
  
-   [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)]  
  
-   [!INCLUDE[vs_orcas_long](../sharepoint/includes/vs-orcas-long-md.md)]  
  
-   Microsoft SharePoint Designer 2007  
  
-   [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)]  
  
 雖然您經常可以成功匯入這些應用程式所建立的解決方案，但這項功能並未經過測試且不受支援。  
  
## 項目匯入限制  
 雖然大部分的 SharePoint 項目可以從現有的 .wsp 檔案匯入，但不支援下列項目，而且可能需要修改才能正確運作：  
  
-   BDC 實體  
  
-   程式碼工作流程關聯項目  
  
-   程式碼工作流程  
  
-   視覺 Web 組件 \(.ascx\)  
  
-   Web 服務 \(.asmx\)  
  
-   內容類型繫結  
  
-   事件接收器  
  
-   清單定義 \(範本\)  
  
-   網站定義  
  
 當您從 [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 或 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 匯出方案時，會自動從 .wsp 檔案排除這些項目。 不過，從不受支援的工具產生的他 .wsp 檔案可能會包含這些項目。 \(請參閱本主題中稍早的＜支援的 SharePoint 方案＞。\)  
  
## 匯入方案時發生什麼事  
 當您使用「匯入 SharePoint 方案套件」範本匯入方案時，[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 複製 .wsp 檔案的所有內容，並嘗試調解並盡可能保留匯入項目與其檔案之間最多的關聯和參考。  
  
 所有匯入的項目會複製到  **方案總管**中的對應資料夾。 例如，內容類型會出現在 \[內容類型\] 資料夾下，而清單執行個體會出現在 \[清單執行個體\] 下。 與匯入項目相關的檔案也會複製到項目的資料夾。 例如，匯入的清單執行個體會包含其模組、表單和 ASPX 頁面。  
  
### 相依項目  
 如果您在 \[匯入 SharePoint 方案套件精靈\] 中選取項目，但未選取其相依項目，會有訊息方塊通知您必須同時選取相依項目才能匯入。  
  
### 何謂功能？  
 SharePoint Designer 使用者可能會看到非預期的檔案，稱為  *功能*，出現在  **方案總管**的匯入方案中。雖然功能存在於 SharePoint Designer 方案中，它們在檢視中是隱藏的。 現在，在 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 中會顯示功能。  
  
 功能是 SharePoint 項目的容器。 每一個功能會保留其所包含之每個項目的參考，例如內容類型和清單定義。 當您匯入方案時，[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 會設定所有匯入項目的功能，並嘗試維護檔案的功能與項目關聯。 無法解析其參考的任何檔案會放在  \[其他匯入檔案\] 資料夾中。  
  
 如需功能的詳細資訊，請參閱 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md) 和 [使用功能](http://go.microsoft.com/fwlink/?LinkID=147704)。  
  
### 處理特殊案例  
 在某些情況下，Visual Studio 無法調解項目與其相依的檔案。[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 無法解析的任何檔案會出現在  \[其他匯入檔案\] 資料夾底下。 此外，它們的  **DeploymentType** 屬性會設為  **NoDeployment**，使它們不會隨著方案部署。  
  
 例如，如果您匯入清單定義 ExpenseForms，則具有該名稱的清單定義會出現在  **方案總管**的  **\[清單定義\]** 資料夾中，同時還會有其 Elements.xml 和 Schema.xml 檔。 不過，其相關聯的 ASPX 和 HTML 表單，可能會放置於  \[其他匯入檔案\] 資料夾下，稱為  **ExpenseForms** 的資料夾。 若要完成匯入，請在  **方案總管**中，移動 ExpenseForms 清單定義底下的這些檔案，並將每個檔案的  **DeploymentType** 屬性從  **NoDeployment** 變更為 **ElementFile**。  
  
 匯入事件接收器時，Elements.xml 檔案會複製到正確的位置，但您必須手動將組件包含在方案套件中，讓它與方案一起部署。[!INCLUDE[crabout](../sharepoint/includes/crabout-md.md)]如何執行這項工作的詳細資訊，請參閱 [如何：新增與移除其他組件](../sharepoint/how-to-add-and-remove-additional-assemblies.md)。  
  
 匯入工作流程時，InfoPath 表單會複製到  \[其他匯入檔案\] 資料夾。 如果 .wsp 檔案包含 Web 範本，它會設定為  **方案總管**中的啟動頁面。  
  
## 匯入欄位和屬性包  
 當您匯入的方案含有多個欄位時，所有個別欄位定義會合併成單一的 Elements.xml 檔案，位於  **方案總管**中，稱為  **\[Fields\]** 的節點下。 同樣地，所有的屬性包項目會合併成 Elements.xml 檔案，位於稱為  **\[PropertyBags\]** 的節點下。  
  
 在 SharePoint 中的欄位是指定資料類型例如文字、布林或查閱的資料行。 如需詳細資訊，請參閱 [建置組塊：資料行和欄位類型](http://go.microsoft.com/fwlink/?LinkId=182304)。 屬性包可讓您將屬性加入至 SharePoint 中的物件，從伺服器陣列到 SharePoint 網站上清單的所有項目。 屬性包會實作為屬性名稱和值的雜湊資料表。 如需詳細資訊，請參閱 [管理 SharePoint 組態](http://go.microsoft.com/fwlink/?LinkId=182296) 或 [SharePoint 屬性包設定](http://go.microsoft.com/fwlink/?LinkId=182297)。  
  
## 刪除專案中的項目  
 SharePoint 方案中的大部分項目有一個或多個相依項目。 例如，清單執行個體取決於內容類型，而內容類型相依於欄位。 匯入 SharePoint 方案之後，如果您刪除方案中的項目但未刪除其相依項目，[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 不會通知您任何參考問題，直到您嘗試部署方案。 例如，如果匯入的方案中有取決於內容類型的清單執行個體，而您刪除了該內容類型，部署時可能會發生錯誤。 如果相依項目不存在於 SharePoint 伺服器上，即會發生錯誤。 同樣地，如果刪除的項目也有相關的屬性包，請從 \[**PropertyBags**\] Elements.xml 檔案中刪除這些屬性包項目。 因此，如果您從匯入的方案中刪除任何項目，但發生部署錯誤，請檢查是否有任何相依項目也需要刪除。  
  
## 還原遺失的功能屬性  
 匯入方案時，匯入的功能資訊清單中會省略一些選用功能的屬性。 如果您想要在新的功能檔案中還原這些屬性，請藉由比較原始功能檔案與新的功能資訊清單，識別遺漏的屬性，然後遵循[如何：自訂 SharePoint 功能](../sharepoint/how-to-customize-a-sharepoint-feature.md) 主題中的指示。  
  
## 內建清單執行個體上不會執行部署衝突偵測  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 不會在內建清單執行個體 \(也就是 SharePoint 隨附的預設清單執行個體\) 上執行部署衝突偵測。 不會執行衝突偵測，以避免覆寫 SharePoint 上的內建清單執行個體。 內建清單執行個體仍會部署或更新，但絕不會被刪除或覆寫。 [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint 封裝和部署疑難排解](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
## 匯入 SharePoint Server 2010 工作流程  
 如果您匯入在 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 中建立的工作流程，它將無法在您部署之後正確執行。 工作流程無法正確執行的原因，是因為遺失特定組件，而 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 工作流程包含目前在 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 工作流程方案中不支援的 InfoPath 表單。 不過，匯入的 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 工作流程，可以藉由修正某些項目之後正常運作，例如將參考加入 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 組件並重新連接 InfoPath 表單。[!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [匯入 SharePoint Server 2010 工作流程](http://go.microsoft.com/fwlink/?LinkId=182226)。  
  
## 項目名稱字元限制  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 對於專案和專案項目名稱，包括路徑，具有總計 260 個字元的限制。 在匯入方案時，如果項目名稱超出此限制，您會收到錯誤：  
  
 **指定的路徑、檔案名稱或兩者都太長。 完整的檔名必須少於 260 個字元，並且目錄名稱必須少於 248 個字元。**  
  
 當您收到這個錯誤時，不會建立項目。 匯入的模組最常發生此問題。 若要避免這個問題，請執行下列作業：  
  
-   當您在  **\[加入新的專案\]** 對話方塊輸入時，請使用專案的簡短名稱。  
  
-   建立專案時，位置盡可能接近根資料夾，以縮短路徑。  
  
## SharePointProductVersion 屬性  
 如果您匯入在舊版 SharePoint 例如 [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] 或 [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] 中建立的方案，請將封裝資訊清單中的 SharePointProductVersion 屬性值變更為 12.0，或是將指令碼管理員控制項插入所有匯入的網頁中，並保留 SharePointProductVersion 設為 14.0。 否則，匯入的 Web 表單不會顯示在 SharePoint 中。  
  
### 背景  
 [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 和 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 中的方案包含稱為 SharePointProductVersion 的屬性。 SharePoint 在其封裝資訊清單中使用這個屬性來判斷方案設計針對的 SharePoint 版本。 兩個有效值為 12.0 和 14.0。 12.0 的值表示項目是針對 [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] 或 [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] 設計；14.0 的值表示項目是針對 [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 或 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 設計。  
  
 為了加強轉譯 ASPX 頁面時的安全性，[!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 和 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 要求所有的 ASPX 或主版頁面都要包含指令碼管理員控制項。 如需指令碼管理員的詳細資訊，請參閱 [ScriptManager 控制項概觀](http://go.microsoft.com/fwlink/?LinkID=169399)。 因為 [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] 和 [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] 中未提供指令碼管理員控制項，因此必須加入一個指令碼管理員控制項到升級至 [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 或 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 的任何 [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] 或 [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] 頁面。 使用標準主版頁面的 ASPX 頁面不需要指令碼管理員控制項，因為已經將一個指令碼管理員控制項加入標準主版頁面。 不過，未使用主版頁面或使用自訂主版頁面的 ASPX 頁面，必須加入指令碼控制項才能在 [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] 或 [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] 中運作。  
  
 當您將 [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] 或 [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] 專案匯入至 [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)] 時，缺少指令碼管理員控制項可能會是一個問題，因為所有新專案的 SharePointProductVersion 屬性都設定為 14.0。 如果您部署的已升級專案中，具有沒有指令碼管理員的 Web 表單，表單將不會顯示在 SharePoint 中。  
  
## 請參閱  
 [逐步解說：從現有的 SharePoint 網站匯入項目](../sharepoint/walkthrough-import-items-from-an-existing-sharepoint-site.md)   
 [匯入可重複使用之工作流程的方針](../sharepoint/guidelines-for-importing-reusable-workflows.md)   
 [逐步解說：將 SharePoint Designer 可重複使用的工作流程匯入 Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)   
 [如何：將現有的 BDC 模型檔案加入至 SharePoint 專案](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)  
  
  