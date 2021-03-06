---
title: 逐步解說： 下載組件隨選與 ClickOnce 部署 API |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- assemblies, downloading [ClickOnce]
- ClickOnce deployment, on-demand download
- on-demand assemblies, ClickOnce
ms.assetid: d20e2789-8621-4806-b5b7-841122da1456
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d6338044dff5aa5b0555b15b689c04ddd406c50f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49887653"
---
# <a name="walkthrough-download-assemblies-on-demand-with-the-clickonce-deployment-api"></a>逐步解說： 下載組件隨選與 ClickOnce 部署 API
根據預設，所有組件包含在[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]第一次執行應用程式時，會下載應用程式。 不過，您可能有應用程式的較少的使用者所使用的部分。 在此情況下，只有在建立組件的其中一種類型時，才會想要下載組件。 下列逐步解說示範如何將標示為 「 選用 」，應用程式中的某些組件，以及如何下載它們使用中的類別<xref:System.Deployment.Application>common language runtime (CLR) 要求它們時的命名空間。  
  
> [!NOTE]
>  您的應用程式必須以完全信任執行，才能使用此程序。  
  
## <a name="prerequisites"></a>必要條件  
 您需要下列元件，才能完成此逐步解說的其中一個：  
  
-   Windows SDK 中。 可以從 Microsoft 下載中心下載 Windows SDK。  
  
-   Visual Studio。  
  
## <a name="create-the-projects"></a>建立專案  
  
#### <a name="to-create-a-project-that-uses-an-on-demand-assembly"></a>若要建立使用隨組件的專案  
  
1. 建立名為 ClickOnceOnDemand 的目錄。  
  
2. 開啟 Windows SDK 命令提示字元或[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]命令提示字元。  
  
3. 切換至 ClickOnceOnDemand 目錄。  
  
4. 產生公開/私密金鑰的金鑰組，使用下列命令：  
  
   ```cmd  
   sn -k TestKey.snk  
   ```  
  
5. 使用 [記事本] 或其他文字編輯器，定義名為類別`DynamicClass`具有單一屬性，名為`Message`。  
  
    [!code-vb[ClickOnceLibrary#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]
    [!code-csharp[ClickOnceLibrary#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]  
  
6. 將文字儲存的檔案名稱*ClickOnceLibrary.cs*或是*ClickOnceLibrary.vb*，取決於所使用的語言，為*ClickOnceOnDemand*目錄。  
  
7. 將檔案編譯成組件。  
  
   ```csharp  
   csc /target:library /keyfile:TestKey.snk ClickOnceLibrary.cs  
   ```  
  
   ```vb  
   vbc /target:library /keyfile:TestKey.snk ClickOnceLibrary.vb  
   ```  
  
8. 若要取得組件的公開金鑰語彙基元，請使用下列命令：  
  
   ```cmd  
   sn -T ClickOnceLibrary.dll  
   ```  
  
9. 建立新的檔案，使用文字編輯器，並輸入下列程式碼。 此程式碼會建立在必要時下載 ClickOnceLibrary 組件的 Windows Forms 應用程式。  
  
     [!code-csharp[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.cs)]
     [!code-vb[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.vb)]  
  
10. 在程式碼中，找出呼叫<xref:System.Reflection.Assembly.LoadFile%2A>。  
  
11. 設定`PublicKeyToken`您稍早擷取的值。  
  
12. 將檔案儲存為其中一個*Form1.cs*或是*Form1.vb*。  
  
13. 編譯成可執行檔使用下列命令。  
  
    ```csharp  
    csc /target:exe /reference:ClickOnceLibrary.dll Form1.cs  
    ```  
  
    ```vb  
    vbc /target:exe /reference:ClickOnceLibrary.dll Form1.vb  
    ```  
  
## <a name="mark-assemblies-as-optional"></a>組件必須標記為選擇性  
  
#### <a name="to-mark-assemblies-as-optional-in-your-clickonce-application-by-using-mageuiexe"></a>使用 MageUI.exe 中標示為 ClickOnce 應用程式中的選用組件  
  
1.  使用*MageUI.exe*，建立應用程式資訊清單中所述[逐步解說： 手動部署 ClickOnce 應用程式](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)。 應用程式資訊清單，請使用下列設定：  
  
    -   命名應用程式資訊清單`ClickOnceOnDemand`。  
  
    -   在 **檔案**頁面上，於*ClickOnceLibrary.dll*資料列中，設定**檔案類型**資料行**無**。  
  
    -   在 **檔案**頁面上，於*ClickOnceLibrary.dll*資料列中，輸入`ClickOnceLibrary.dll`中**群組**資料行。  
  
2.  使用*MageUI.exe*，建立部署資訊清單中所述[逐步解說： 手動部署 ClickOnce 應用程式](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)。 部署資訊清單，請使用下列設定：  
  
    -   命名的部署資訊清單`ClickOnceOnDemand`。  
  
## <a name="testing-the-new-assembly"></a>測試新的組件  
  
#### <a name="to-test-your-on-demand-assembly"></a>測試隨選組件  
  
1. 上傳您[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]部署至 Web 伺服器。  
  
2. 啟動您的應用程式與部署[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]從網頁瀏覽器輸入 URL 的部署資訊清單。 如果您呼叫您[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]應用程式`ClickOnceOnDemand`，而且您將它上傳至 adatum.com 的根目錄，您的 URL 看起來像這樣：  
  
   ```  
   http://www.adatum.com/ClickOnceOnDemand/ClickOnceOnDemand.application  
   ```  
  
3. 您的主要表單出現時，請按 <xref:System.Windows.Forms.Button>。 您應該會看到"Hello World ！"訊息方塊視窗中的字串。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Deployment.Application.ApplicationDeployment>