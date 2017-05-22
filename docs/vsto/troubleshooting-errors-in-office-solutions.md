---
title: "Office 方案的錯誤疑難排解"
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
  - "VST.Project.DesignerDisabled"
  - "VST.Designer.CannotActivate"
  - "VST.Project.ExcelBusy"
  - "VST.SelectDocWizard.AlreadyCustomized"
  - "VST.SelectDocWizard.DocPath"
  - "VST.Project.CannotOpen"
  - "VST.Designer.ErrorsOccurred"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "疑難排解 [Visual Studio 中的 Office 程式開發]"
ms.assetid: 8bbf5433-1992-4ecf-ae1b-19117b8ebe43
caps.latest.revision: 69
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 68
---
# Office 方案的錯誤疑難排解
  當您在 Visual Studio 開發 Office 方案的過程中執行下列工作時，可能會遇到一些問題：  
  
-   [建立、 升級和開啟專案](#creating)  
  
-   [使用設計工具](#designers)  
  
-   [撰寫程式碼](#code)  
  
-   [建置專案](#building)  
  
-   [偵錯專案](#debugging)  
  
##  <a name="creating"></a> 建立、升級和開啟專案  
 當您建立或開啟 Office 專案時，可能會遇到下列錯誤。  
  
### 無法建立專案  
 在您嘗試建立或開啟 Office 專案時發生錯誤，但是 Visual Studio 沒有足夠的資訊來判斷原因。  請嘗試關閉專案、結束 Visual Studio 並重新啟動。  
  
 如果您嘗試建立文件層級專案，有時候可能已有與新專案中的文件同名的其他文件以 Excel 或 Word 開啟。  請確定所有其他 Excel 或 Word 執行個體都已關閉。  
  
### 以現有專案的文件為基礎建立新專案時，遺失了控制項屬性  
 如果您以現有專案的文件為基礎來建立新的 Office 專案，文件中任何控制項的屬性都不會複製到新專案中。  您必須以手動方式重設任何預先存在之控制項的屬性。  或者，您也可以建立現有專案的複本而不建立新專案，或將現有專案載入新方案中 \(在設計工具中\)，然後從現有文件複製控制項並貼到新文件中，藉此保留控制項屬性。  
  
### 以現有活頁簿為基礎建立 Excel 活頁簿專案時發生錯誤  
 如果您以現有活頁簿為基礎建立新的 Excel 活頁簿專案，可能會見到下列錯誤的組合。  
  
 來自 Excel：「隱私權警告：此文件包含巨集、ActiveX 控制項、XML 擴充套件資訊或 Web 元件。  這些可能包含無法經由 \[文件檢查\] 移除的私人資訊。」  
  
 來自 Visual Studio：「無法正確載入設計工具。」  
  
 當您嘗試建立的專案是以已使用 \[文件檢查\] 移除其個人資訊的活頁簿為基礎時，可能會發生這些錯誤。  若要避免這個錯誤，請在建立專案前先執行下列步驟。  
  
1.  在 Excel 中開啟該活頁簿。  
  
2.  在 Excel 中開啟 \[信任中心\]。  
  
3.  清除 \[隱私選項\] 索引標籤上的 \[存檔時自檔案摘要資訊中移除私人資訊\] 核取方塊。  
  
4.  儲存活頁簿並關閉 Excel。  
  
### 移轉之後無法開啟專案  
 Office 方案移轉至 Microsoft Office 2010 之後，無法在只安裝 2007 Microsoft Office system 的開發電腦上開啟專案。  您可能會看到下列錯誤。  
  
 「方案中的一個或多個專案未正確載入。  如需詳細資訊，請參閱 \[輸出\] 視窗。」  
  
 「無法建立專案，因為這部電腦上未安裝與這種專案類型關聯的應用程式。  您必須安裝與這種專案類型關聯的 Microsoft Office 應用程式。」  
  
 若要解決這個問題，請編輯 .vbproj 或 .csproj 檔。  若為 Word 專案，請將 HostPackage\="{763FDC83\-64E5\-4651\-AC9B\-28C4FEB985A1}" 取代為 HostPackage\="{6CE98B71\-D55A\-4305\-87A8\-0D6E368D9600}"。  若為 Excel 專案，請將 HostPackage\="{B284B16A\-C42C\-4438\-BDCD\-B72F4AC43CFB}" 取代為 HostPackage\="{825100CF\-0BA7\-47EA\-A084\-DCF3308DAF74}"。  若為 Outlook 專案，請將 HostPackage\="{D2B20FF5\-A6E5\-47E1\-90E8\-463C6860CB05}" 取代為 HostPackage\="{20A848B8\-E01F\-4801\-962E\-25DB0FF57389}"。  
  
 或者，請務必確定只在已安裝 Microsoft Office 2010 的開發電腦上開啟移轉的專案。  
  
### 含有 Windows Form 控制項的 Office 2003 文件層級專案在升級後發生錯誤  
 如果您將 Microsoft Office 2003 文件層級專案升級，而且此文件包含 Windows Forms 控制項，則升級的專案可能會發生編譯或執行階段錯誤。  若要避免這個問題，請先在開發電腦上安裝 Visual Studio 2005 Tools for Office Second Edition Runtime，再將專案升級。  此版本的執行階段可以從 Microsoft 下載中心取得得可轉散發套件 [Microsoft Visual Studio 2005 Tools for Office Second Edition Runtime \(VSTO 2005 SE\) \(x86\)](http://go.microsoft.com/fwlink/?linkid=49612)。  
  
 完成專案升級後，可以解除安裝開發電腦中的 Visual Studio 2005 Tools for Office Second Edition Runtime \(如果沒有其他 Office 方案正在使用它\)。  
  
##  <a name="designers"></a> 使用設計工具  
 當您在文件層級專案中使用文件、活頁簿或工作表設計工具時，可能會遇到下列錯誤。  
  
### 無法正確載入設計工具  
 在下列情況下，Visual Studio 無法開啟設計工具：  
  
-   Excel 或 Word 已開啟並且正在顯示強制回應對話方塊。  若要開啟設計工具，請查看 Excel 或 Word 是否開啟強制回應對話方塊，並且關閉任何開啟的強制回應對話方塊。  如果沒有開啟任何強制回應對話方塊，則可能需要執行其他動作，Excel 或 Word 才會回應。  
  
-   專案目前正在偵錯。  若要開啟設計工具，請停止或完成偵錯。  
  
-   Excel 啟動時，開發電腦上安裝的 Excel VSTO 增益集正在顯示對話方塊。  若要建立 Excel 文件層級專案，您必須先停用 VSTO 增益集。  
  
### 控制項在文件或工作表上顯示為黑色矩形  
 如果您將文件或工作表上的控制項設為群組，Visual Studio 就不再能夠辨認此控制項。  您無法從 \[屬性\] 視窗中存取群組控制項，而且這些控制項在文件或工作表上會顯示為黑色矩形。  您必須對這些控制項取消群組，以便還原其功能。  
  
### 在 Visual Studio 中看不到 Word 範本上的控制項  
 如果您在 \[Visual Studio 設計工具\] 中開啟 Word 範本，就有可能看不到該範本上未與文字排列的控制項。  這是因為 Visual Studio 會以 \[標準\] 檢視開啟 Word 範本。  若要檢視這些控制項，請按一下 \[檢視\] 功能表，指向 \[Microsoft Office Word 檢視\]，然後按一下 \[整頁模式\]。  
  
### 插入美工圖案命令在 \[Visual Studio 設計工具\] 中沒有任何作用  
 Excel 或 Word 在 \[Visual Studio 設計工具\] 中開啟時，按一下功能區中 \[插圖\] 索引標籤上的 \[美工圖案\] 按鈕並不會開啟 \[美工圖案\] 工作窗格。  若要加入美工圖案，您必須開啟位於 Visual Studio 外部的主要專案資料夾中活頁簿或文件的複本 \(不是位於 \\bin 資料夾中的複本\)，加入美工圖案，然後儲存活頁簿或文件。  
  
##  <a name="code"></a> 撰寫程式碼  
 當您在 Office 專案中撰寫程式碼時，可能會遇到下列錯誤。  
  
### 使用 C\# 時無法存取 Office 物件的某些事件  
 在某些情況下，當您嘗試在 Visual C\# 專案中存取某個 Office 主要 Interop 組件 \(PIA\) 類型執行個體的特定事件時，可能會看到編譯器錯誤。  
  
 "Ambiguity between 'Microsoft.Office.Interop.Excel.\_Application.NewWorkbook' 和 'Microsoft.Office.Interop.Excel.AppEvents\_Event.NewWorkbook'"  
  
 這個錯誤表示您嘗試存取的事件具有與該物件之其他屬性或方法相同的名稱。  若要存取此事件，您必須將該物件轉換成其*「事件介面」*\(event interface\)。  
  
 具有事件的 Office PIA 類型會實作兩個介面：一個是包含所有屬性和方法的核心介面，一個是包含物件所公開之事件的事件介面。  這些事件介面會使用命名慣例 *objectname*Events*n*\_Event，例如 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event> 和 <xref:Microsoft.Office.Interop.Word.ApplicationEvents2_Event>。  如果您無法存取預期會在物件上找到的事件，請將該物件轉換成其事件介面。  
  
 例如，<xref:Microsoft.Office.Interop.Excel.Application> 物件具有 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook> 事件和 <xref:Microsoft.Office.Interop.Excel._Application.NewWorkbook%2A> 屬性。  若要處理 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook> 事件，請將 <xref:Microsoft.Office.Interop.Excel.Application> 轉換成 <xref:Microsoft.Office.Interop.Excel.AppEvents_Event> 介面。  下列程式碼範例示範如何在 Excel 的文件層級專案中執行這項作業。  
  
 [!code-csharp[Trin_VstcoreTroubleshootingExcel#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingExcel/CS/ThisWorkbook.cs#1)]  
  
 如需 Office PIA 中事件介面的詳細資訊，請參閱 [Office 主要 Interop 組件中的類別和介面概觀](http://msdn.microsoft.com/zh-tw/da92dc3c-8209-44de-8095-a843659368d5)。  
  
### 無法參考以 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 為目標之專案的 Office PIA 類別  
 根據預設，在以 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 為目標的專案中，不會編譯參考 Office PIA 中所定義類別的程式碼。  PIA 中的類別會使用命名慣例 *objectname*Class，如 <xref:Microsoft.Office.Interop.Word.DocumentClass> 和 <xref:Microsoft.Office.Interop.Excel.WorkbookClass>。  例如，將不會編譯 Word VSTO 增益集專案中的下列程式碼。  
  
```vb  
Dim document As Word.DocumentClass = Globals.ThisAddIn.Application.ActiveDocument  
```  
  
```csharp  
Word.DocumentClass document = (Word.DocumentClass) Globals.ThisAddIn.Application.ActiveDocument;  
```  
  
 這段程式碼會導致下列編譯錯誤：  
  
-   Visual Basic：「在使用非 PIA 模式連結類別 ‘DocumentClass’ 的組件時，不允許參考至該類別。」  
  
-   Visual C\#：「無法內嵌 Interop 類型 ‘Microsoft.Office.Interop.Word.DocumentClass’。  請改用適當的介面。」  
  
 若要解決這個錯誤，請修改程式碼以參考對應的介面。  例如，不要參考 <xref:Microsoft.Office.Interop.Word.DocumentClass> 物件，改為參考 <xref:Microsoft.Office.Interop.Word.Document> 介面的執行個體。  
  
```vb  
Dim document As Word.Document = Globals.ThisAddIn.Application.ActiveDocument  
```  
  
```csharp  
Word.Document document = Globals.ThisAddIn.Application.ActiveDocument;  
```  
  
 根據預設，以 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 為目標的專案會自動內嵌 Office PIA 的所有 Interop 類型。  之所以會發生這個編譯錯誤，是因為內嵌的 Interop 類型功能僅適用於介面，而不適用於類別。  如需 Office PIA 中介面和類別的詳細資訊，請參閱 [Office 主要 Interop 組件中的類別和介面概觀](http://go.microsoft.com/fwlink/?LinkId=189592)。  如需 Office 專案中內嵌 Interop 類型功能的詳細資訊，請參閱[設計和建立 Office 方案](../vsto/designing-and-creating-office-solutions.md)。  
  
### 無法辨識 Office 類別的參考  
 某些類別名稱 \(例如 Application\) 會出現在多個命名空間中，例如 <xref:Microsoft.Office.Interop.Word> 和 <xref:System.Windows.Forms>。  因此，專案範本最上方的 **Imports**\/**using** 陳述式會包括縮寫的限定常數，例如：  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingWord/CS/ThisDocument.cs#2)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingWord/VB/ThisDocument.vb#2)]  
  
 如果使用這種 **Imports**\/**using** 陳述式，您必須能分辨 Office 類別的參考與 Word 或 Excel 限定詞的不同，例如：  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingWord/CS/ThisDocument.cs#3)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingWord/VB/ThisDocument.vb#3)]  
  
 如果您使用未限定的宣告，將會發生錯誤，例如：  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingWord/CS/ThisDocument.cs#4)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreTroubleshootingWord/VB/ThisDocument.vb#4)]  
  
 即使您已匯入了 Word 或 Excel 命名空間，而且也能存取其中的所有類別，但仍然必須使用 Word 或 Excel 完整限定所有類型，以免命名空間語意模糊。  
  
##  <a name="building"></a> 建置專案  
 當您建置 Office 專案時，可能會遇到下列錯誤。  
  
### 無法建立以含有限制權限之文件為基礎的文件層級專案  
 如果文件具有限制權限，Visual Studio 就無法建置文件層級專案。  如果專案包含具有限制權限的文件，則不會編譯該專案，而且您會在 \[錯誤清單\] 視窗中收到下列訊息。  
  
 「無法加入自訂。」  
  
 如果您想加入具有限制權限的文件，則在開發和建置方案時請使用無限制的文件。  然後，在您發佈方案之後，將限制權限套用至位於發佈位置的文件。  
  
### 在刪除 NamedRange 控制項之後發生編譯器錯誤  
 如果您從工作表刪除 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控制項，而該工作表並非設計工具的現用工作表，則自動產生的程式碼可能不會從專案中移除，而且可能會發生編譯器錯誤。  為了確定將移式碼移除，請務必選取包含 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控制項的工作表，在刪除控制項之前讓它成為現用工作表。  如果刪除控制項時沒有刪除自動產生的程式碼，您可以啟動工作表並進行變更，讓系統將該工作表標示為已修改，從而讓設計工具刪除該程式碼。  當您重建此專案時，便會移除程式碼。  
  
##  <a name="debugging"></a> 偵錯專案  
 當您偵錯 Office 專案時，可能會遇到下列錯誤。  
  
### 當您在開發電腦上發佈和安裝方案時，會出現解除安裝的提示  
 當您偵錯 Office 方案時，可能會見到下列錯誤。  
  
 「無法安裝自訂，因為目前安裝了其他版本，而且無法從這個位置進行升級。」  
  
 這個錯誤表示您先前已在開發電腦上發佈和安裝 Office 方案。  為避免這個訊息出現，請先從電腦上已安裝的程式清單中解除安裝此方案，然後再偵錯該方案。  或者，您也可以在開發電腦上建立其他使用者帳戶，以測試所發佈方案的安裝。  
  
### Visual Studio 中不會執行在 UNC 網路位置建立的文件層級專案  
 如果您在 UNC 網路位置建立 Excel 或 Word 文件層級專案，則必須將文件位置加入 Excel 或 Word 的信任位置清單。  否則，當您嘗試在 Visual Studio 中執行或偵錯專案時，將不會載入自訂。  如需信任位置的詳細資訊，請參閱[授與信任給文件](../vsto/granting-trust-to-documents.md)。  
  
### 偵錯之後執行緒未正確停止  
 Visual Studio 中的 Office 專案會遵循執行緒命名慣例，該慣例可讓偵錯工具正確關閉程式。  如果您在方案中建立執行緒，則應在每個執行緒名稱加上前置詞 VSTA\_，確保停止偵錯時能正確處理這些執行緒。  例如，您可以將等待網路事件的執行緒之 `Name` 屬性設定為 VSTA\_NetworkListener。  
  
### 無法在開發電腦上執行或偵錯任何 Office 方案  
 如果無法在開發電腦上執行或開發 Office 專案，您可能會看到下列錯誤訊息。  
  
 「無法載入自訂，因為無法建立應用程式定義域。」  
  
 Visual Studio 會使用融合 \(.NET Framework 組件載入器\)，在載入 Office 方案之前快取組件。  請確認 Visual Studio 可以寫入融合快取，然後再試一次。  如需詳細資訊，請參閱[陰影複製組件](http://msdn.microsoft.com/library/de8b8759-fca7-4260-896b-5a4973157672)。  
  
### 使用 \[編輯後繼續\] 之後在文件層級專案中停止偵錯工具時發生錯誤  
 如果您在專案處於中斷模式時使用 \[編輯後繼續\] 來變更 Excel 或 Word 文件層級專案中的程式碼，並隨後停止偵錯工具，則可能會看到包含以下錯誤訊息的對話方塊。  
  
 「在這個處理序的目前狀態終止它可能會造成不良後果，包括資料遺失和系統不穩定。」  
  
 不論您按一下對話方塊中的 \[是\] 或 \[否\]，Visual Studio 都會終止 Excel 或 Word 處理序並停止偵錯工具。  若要停止專案偵錯而不顯示此對話方塊，請直接結束 Excel 或 Word，而不是在 Visual Studio 中停止偵錯工具。  
  
## 請參閱  
 [Office 方案疑難排解](../vsto/troubleshooting-office-solutions.md)   
 [Office 方案安全性疑難排解](../vsto/troubleshooting-office-solution-security.md)   
 [Office 方案部署疑難排解](../vsto/troubleshooting-office-solution-deployment.md)  
  
  