---
title: "逐步解說：為您的 Word 建立第一個 VSTO 增益集"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "增益集 [Visual Studio 中的 Office 程式開發], 建立第一個專案"
  - "應用程式層級增益集 [Visual Studio 中的 Office 程式開發], 建立第一個專案"
  - "Visual Studio 中的 Office 程式開發, 建立第一個專案"
  - "Word [Visual Studio 中的 Office 程式開發], 建立第一個專案"
ms.assetid: 9d857be7-5c74-4303-baf4-672afc1ea397
caps.latest.revision: 55
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 51
---
# 逐步解說：為您的 Word 建立第一個 VSTO 增益集
  本入門逐步解說將示範如何建立 Microsoft Office Word 的 VSTO 增益集。  不論開啟哪一份文件，您在這類方案中建立的功能都可供應用程式本身使用。  
  
 [!INCLUDE[appliesto_wdallapp](../vsto/includes/appliesto-wdallapp-md.md)]  
  
 這個逐步解說將說明下列工作：  
  
-   建立 Word VSTO 增益集專案。  
  
-   撰寫可使用 Word 物件模型的程式碼，儲存文件時便可加入文字。  
  
-   建置和執行專案來進行測試。  
  
-   清除已完成的專案，使得 VSTO 增益集不再於開發電腦上自動執行。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 必要條件  
 您需要下列元件才能完成此逐步解說：  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 建立專案  
  
#### 在 Visual Studio 中建立新的 Word VSTO 增益集專案  
  
1.  啟動 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]。  
  
2.  在 \[檔案\] 功能表中，指向 \[新增\]，然後按一下 \[專案\]。  
  
3.  在範本窗格中，展開 \[Visual C\#\] 或 \[Visual Basic\]，然後展開 \[Office\/SharePoint\]。  
  
4.  在展開的 \[Office\/SharePoint\] 節點下，選取 \[Office 增益集\] 節點。  
  
5.  在專案範本清單中，選取 \[Word VSTO 增益集\] 專案。  
  
6.  在 \[名稱\] 方塊中，輸入 **FirstWordAddIn**。  
  
7.  按一下 \[**確定**\]。  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 會建立 **FirstWordAddIn** 專案，並在編輯器中開啟 ThisAddIn 程式碼檔案。  
  
## 撰寫程式碼以將文字加入儲存的文件  
 接著，將程式碼加入 ThisAddIn 程式碼檔。  新程式碼會使用 Word 物件模型，將未定案文字加入每份儲存的文件中。  根據預設，ThisAddIn 程式碼檔包含下列產生的程式碼：  
  
-   `ThisAddIn` 類別的部分定義。  這個類別提供您撰寫程式碼的進入點，並提供對 Word 物件模型的存取。  如需詳細資訊，請參閱 [VSTO 增益集程式設計](../vsto/programming-vsto-add-ins.md)。  `ThisAddIn` 類別的其餘部分則定義於您不應修改的隱藏程式碼檔中。  
  
-   `ThisAddIn_Startup` 和 `ThisAddIn_Shutdown` 事件處理常式。  當 Word 載入和卸載 VSTO 增益集時，會呼叫這些事件處理常式。  請使用這些事件處理常式，在 VSTO 增益集載入時將它初始化，以及在 VSTO 增益集卸載時清除它所用的資源。  如需詳細資訊，請參閱 [Office 專案中的事件](../vsto/events-in-office-projects.md)。  
  
#### 將文字段落加入儲存的文件  
  
1.  在 ThisAddIn 程式碼檔中，將下列程式碼加入 `ThisAddIn` 類別。  新的程式碼會定義 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 事件的事件處理常式，該事件是在儲存文件時所引發的。  
  
     當使用者儲存文件時，事件處理常式會將新文字加入此文件開頭。  
  
     [!code-csharp[Trin_WordAddInTutorial#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInTutorial/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_WordAddInTutorial#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInTutorial/VB/ThisAddIn.vb#1)]  
  
    > [!NOTE]  
    >  此程式碼會使用索引值 1 來存取 <xref:Microsoft.Office.Interop.Word._Document.Paragraphs%2A> 集合中的第一個段落。  雖然 Visual Basic 和 Visual C\# 都是使用以 0 為起始的陣列，但是在 Word 物件模型中，大多數集合的陣列界限下限都是 1。  如需詳細資訊，請參閱[撰寫 Office 方案中的程式碼](../vsto/writing-code-in-office-solutions.md)。  
  
2.  如果使用的是 C\#，請將下列必要的程式碼加入 `ThisAddIn_Startup` 事件處理常式中。  這段程式碼是用來連接 `Application_DocumentBeforeSave` 事件處理常式和 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 事件。  
  
     [!code-csharp[Trin_WordAddInTutorial#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInTutorial/CS/ThisAddIn.cs#2)]  
  
 若要在儲存文件時修改文件，前面的程式碼範例可以使用下列物件：  
  
-   `ThisAddIn` 類別的 `Application` 欄位。  `Application` 欄位會傳回 <xref:Microsoft.Office.Interop.Word.Application> 物件，此物件代表 Word 目前的執行個體。  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 事件的事件處理常式的 `Doc` 參數。  `Doc` 參數是 <xref:Microsoft.Office.Interop.Word.Document> 物件，此物件代表儲存的文件。  如需詳細資訊，請參閱 [Word 物件模型概觀](../vsto/word-object-model-overview.md)。  
  
## 測試專案  
  
#### 測試專案  
  
1.  按 **F5** 建置及執行專案。  
  
     當您建置專案時，程式碼會編譯到包含在專案建置輸出資料夾中的組件。  Visual Studio 也會建立一組登錄項目，以便 Word 探索和載入 VSTO 增益集，而且會設定開發電腦中的安全性設定，讓 VSTO 增益集可以執行。  如需詳細資訊，請參閱 [建置 Office 方案](../vsto/building-office-solutions.md)。  
  
2.  在 Word 中，儲存使用中的文件。  
  
3.  確認下列文字已加入文件中。  
  
     **This text was added by using code.**  
  
4.  關閉 Word。  
  
## 清除專案  
 當您完成專案開發時，請從開發電腦移除 VSTO 增益集組件、登錄項目和安全性設定。  否則，每次在開發電腦上開啟 Word 時，VSTO 增益集將會繼續執行。  
  
#### 清除開發電腦上已完成的專案  
  
1.  在 Visual Studio 中，按一下 \[建置\] 功能表上的 \[清除方案\]。  
  
## 後續步驟  
 現在您已經建立 Word 的基本 VSTO 增益集，可以從下列主題進一步了解如何開發 VSTO 增益集：  
  
-   您可以在 VSTO 增益集中執行的一般程式設計工作：[VSTO 增益集程式設計](../vsto/programming-vsto-add-ins.md)。  
  
-   Word VSTO 增益集特有的程式設計工作：[Word 方案](../vsto/word-solutions.md)。  
  
-   使用 Word 物件模型：[Word 物件模型概觀](../vsto/word-object-model-overview.md)。  
  
-   自訂 Word 的 UI，例如，將自訂索引標籤加入功能區，或建立您專屬的自訂工作窗格：[Office UI 自訂](../vsto/office-ui-customization.md)。  
  
-   建置和偵錯 Word 的 VSTO 增益集：[建置 Office 方案](../vsto/building-office-solutions.md)。  
  
-   部署 Word 的 VSTO 增益集：[部署 Office 方案](../vsto/deploying-an-office-solution.md)。  
  
## 請參閱  
 [Office 方案開發概觀 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Word 方案](../vsto/word-solutions.md)   
 [VSTO 增益集程式設計](../vsto/programming-vsto-add-ins.md)   
 [Word 物件模型概觀](../vsto/word-object-model-overview.md)   
 [Office UI 自訂](../vsto/office-ui-customization.md)   
 [建置 Office 方案](../vsto/building-office-solutions.md)   
 [部署 Office 方案](../vsto/deploying-an-office-solution.md)   
 [Office 專案範本概觀](../vsto/office-project-templates-overview.md)  
  
  