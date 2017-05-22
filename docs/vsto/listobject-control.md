---
title: "ListObject 控制項"
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
  - "VST.Toolbox.List"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "清單，事件"
  - "ListObject 控制項"
  - "ListObject 控制項，事件"
  - "ListObject 控制項，資料繫結"
  - "ListObject 控制項，在繫結至資料時提升效能"
ms.assetid: 2bdecbf0-2a0f-48de-a544-dca12bb4a9a3
caps.latest.revision: 70
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 69
---
# ListObject 控制項
  <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項是可公開事件及繫結至資料的清單。 當您將清單加入工作表時，Visual Studio 會建立 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項，以便您直接對這個控制項進行程式設計，而不必周遊 Microsoft Office Excel 物件模型。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 建立控制項  
 在文件層級專案中，您可以於設計階段或執行階段，將 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項加入工作表。 在 VSTO 增益集專案中，您只能於執行階段將 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項加入工作表。 如需詳細資訊，請參閱[如何：將 ListObject 控制項加入至工作表](../vsto/how-to-add-listobject-controls-to-worksheets.md)。  
  
> [!NOTE]  
>  根據預設，當工作表關閉時，動態建立的清單物件不會保存為工作表中的主控制項。 如需詳細資訊，請參閱[在執行階段將控制項加入至 Office 文件](../vsto/adding-controls-to-office-documents-at-run-time.md)。  
  
## 將資料繫結至控制項  
 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項支援簡單和複雜資料繫結。<xref:Microsoft.Office.Tools.Excel.ListObject> 控制項可在設計階段使用 <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A> 和 <xref:Microsoft.Office.Tools.Excel.ListObject.DataMember%2A> 屬性，或在執行階段使用 <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> 方法繫結至資料來源。  
  
> [!NOTE]  
>  如果將 <xref:Microsoft.Office.Tools.Excel.ListObject> 繫結至資料變更時會引發事件的資料來源 \(例如 <xref:System.Data.DataTable>\)，它會自動進行更新。 如果將 <xref:Microsoft.Office.Tools.Excel.ListObject> 繫結至資料變更時不會引發事件的資料來源，則必須呼叫 <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRow%2A> 或 <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRows%2A> 方法以更新 <xref:Microsoft.Office.Tools.Excel.ListObject>。  
  
 當您將重複的結構描述項目對應至工作表儲存格，藉此將 <xref:Microsoft.Office.Tools.Excel.ListObject> 加入該儲存格時，Visual Studio 會自動將 <xref:Microsoft.Office.Tools.Excel.ListObject> 對應至產生的資料集。 不過，<xref:Microsoft.Office.Tools.Excel.ListObject> 不會自動繫結至資料。 在文件層級專案中，您可以於設計階段或執行階段採取一些步驟，將 <xref:Microsoft.Office.Tools.Excel.ListObject> 繫結至資料集。 在 VSTO 增益集中，您可以於執行階段透過程式設計方式，將 <xref:Microsoft.Office.Tools.Excel.ListObject> 繫結至資料集。  
  
 由於資料與 <xref:Microsoft.Office.Tools.Excel.ListObject> 分離，因此您應該透過所繫結的資料集加入及移除資料，而不是直接透過 <xref:Microsoft.Office.Tools.Excel.ListObject> 進行。 如果透過任何機制更新所繫結之資料集中的資料，<xref:Microsoft.Office.Tools.Excel.ListObject> 控制項會自動反映這些變更。 如需詳細資訊，請參閱[將資料繫結至 Office 方案中的控制項](../vsto/binding-data-to-controls-in-office-solutions.md)。  
  
 您可以將 <xref:Microsoft.Office.Tools.Excel.ListObject> 繫結至資料來源，以快速填入 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項。 如果您在繫結至資料的 <xref:Microsoft.Office.Tools.Excel.ListObject> 中編輯資料，資料來源中也會自動進行這些變更。 如果您想要填入 <xref:Microsoft.Office.Tools.Excel.ListObject>，再讓使用者變更 <xref:Microsoft.Office.Tools.Excel.ListObject> 中的資料，卻又不想要修改資料來源，則可以使用 <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A> 方法將 <xref:Microsoft.Office.Tools.Excel.ListObject> 與資料來源中斷連結。 如需詳細資訊，請參閱[如何：將資料填入 ListObject 控制項](../vsto/how-to-fill-listobject-controls-with-data.md)。  
  
> [!NOTE]  
>  重疊的 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項不支援資料繫結。  
  
### 提升 ListObject 控制項的效能  
 如果先繫結控制項，再呼叫 <xref:System.Data.DataSet.ReadXml%2A> 填入資料集，通常會使 XML 檔案讀入繫結至資料之 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項的速度變慢。 若要提升效能，請先呼叫 <xref:System.Data.DataSet.ReadXml%2A> 再繫結控制項。  
  
### 中斷連接 ListObject 控制項與資料來源  
 將 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項繫結至資料來源並以此資料填入控制項之後，您可以中斷與資料來源的連接，如此一來對清單物件中資料所做的修改，就不會影響資料來源。 如需詳細資訊，請參閱[如何：將資料填入 ListObject 控制項](../vsto/how-to-fill-listobject-controls-with-data.md)。  
  
### 還原欄和列順序  
 當您將資料繫結至在設計階段加入文件的 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項時，Visual Studio 會在每次儲存活頁簿時，記錄欄和列順序。 如果使用者在執行階段移動 <xref:Microsoft.Office.Tools.Excel.ListObject> 欄或列，在下一次開啟活頁簿時會保留新的順序，並將 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項重新繫結至資料來源。  
  
 如果您想要將 <xref:Microsoft.Office.Tools.Excel.ListObject> 還原成其原始欄和列順序，可以呼叫 <xref:Microsoft.Office.Tools.Excel.ListObject.ResetPersistedBindingInformation%2A> 方法。 這個方法會移除與指定 <xref:Microsoft.Office.Tools.Excel.ListObject> 之欄和列順序相關的自訂文件屬性。 如果不想保留 <xref:Microsoft.Office.Tools.Excel.ListObject> 的欄和列順序，請從活頁簿的 <xref:Microsoft.Office.Tools.Excel.Workbook.Shutdown> 事件呼叫這個方法。  
  
## 格式化  
 可套用至 <xref:Microsoft.Office.Interop.Excel.ListObject> 的格式，也可套用至 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項。 這包括框線、字型、數字格式和樣式。 使用者可以在繫結至資料的 <xref:Microsoft.Office.Tools.Excel.ListObject> 中重新排列欄，只要 <xref:Microsoft.Office.Tools.Excel.ListObject> 是在設計階段加入文件，這些變更就會隨文件一起保存。 下次開啟文件時，清單物件會繫結至相同的資料來源，但欄順序則會反映使用者的變更。  
  
## 在執行階段加入及移除欄  
 您無法在執行階段，於繫結至資料的 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項中手動加入或移除欄。 如果使用者嘗試刪除某欄，該欄會立即還原，並移除任何加入的欄。 因此，請務必撰寫程式碼，向使用者說明為何無法在繫結至資料的 <xref:Microsoft.Office.Tools.Excel.ListObject> 上執行這些動作。 Visual Studio 在與資料繫結相關的 <xref:Microsoft.Office.Tools.Excel.ListObject> 上，提供數個事件。 例如，您可以使用 <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored> 事件，在使用者嘗試刪除資料時，警告使用者該資料無法刪除並已還原。  
  
## 在執行階段加入及移除列  
 只要資料來源允許新增列且不是唯讀，您便可以在繫結至資料的 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項中手動加入及移除列。 您可以對 <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> 等事件撰寫程式碼，以驗證資料。 如需詳細資訊，請參閱[如何：將新資料列加入 ListObject 控制項時驗證資料](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)。  
  
 有時清單物件與資料來源的關聯性會造成常式錯誤。 例如，您可以對應要在 <xref:Microsoft.Office.Tools.Excel.ListObject> 中出現的欄；在這種情況下，如果遺漏具有限制的欄 \(例如不可接受 null 值的欄位\)，則每次建立列都會引發錯誤。 您可以撰寫程式碼，在 <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow> 事件的事件處理常式中加入遺漏的值。  
  
## 在 Excel 中重新命名 ListObject 控制項  
 Excel 可讓使用者在執行階段使用 \[設計\] 索引標籤，來變更 Excel 表格的名稱。 不過，<xref:Microsoft.Office.Tools.Excel.ListObject> 控制項不支援這項功能。 如果使用者嘗試重新命名對應至 <xref:Microsoft.Office.Tools.Excel.ListObject> 的 Excel 表格，該 Excel 表格的名稱會自動還原成儲存活頁簿時所使用的原始名稱。  
  
## 事件  
 下列事件適用於 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項：  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataBindingFailure>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataMemberChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataSourceChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Deselected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectedIndexChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectionChange>  
  
## 請參閱  
 [使用擴充物件自動化 Excel](../vsto/automating-excel-by-using-extended-objects.md)   
 [如何：將 ListObject 控制項加入至工作表](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [如何：調整 ListObject 控制項的大小](../vsto/how-to-resize-listobject-controls.md)   
 [如何：將新資料列加入 ListObject 控制項時驗證資料](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [如何：將 ListObject 欄對應到資料](../vsto/how-to-map-listobject-columns-to-data.md)   
 [如何：將資料填入 ListObject 控制項](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Office 程式開發範例和逐步解說](../vsto/office-development-samples-and-walkthroughs.md)   
 [將資料繫結至 Office 方案中的控制項](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [在 VSTO 增益集的執行階段中擴充 Word 文件和 Excel 活頁簿](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 文件上的控制項](../vsto/controls-on-office-documents.md)   
 [在執行階段將控制項加入至 Office 文件](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [如何：將資料庫的資料填入工作表](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [主項目和主控制項的程式設計限制](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  