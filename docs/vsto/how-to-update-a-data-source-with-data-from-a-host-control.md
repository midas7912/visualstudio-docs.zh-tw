---
title: 如何： 從主控制項的資料更新資料來源
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], data source updates
- data [Office development in Visual Studio], updating a data source from a document
- host controls [Office development in Visual Studio], data source updates
- Office documents [Office development in Visual Studio, data sources
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3a31bac6b3cbd13fcff8c841c9947e8c14f8984a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49839761"
---
# <a name="how-to-update-a-data-source-with-data-from-a-host-control"></a>如何： 從主控制項的資料更新資料來源
  您可以將主控制項繫結至資料來源，並以在控制項中對資料所做的變更來更新資料來源。 這個程序包含兩個主要步驟：  
  
1. 以控制項中修改的資料更新記憶體內部資料來源。 一般而言，記憶體內部資料來源是 <xref:System.Data.DataSet>、 <xref:System.Data.DataTable>或其他一些資料物件。  
  
2. 以記憶體內部資料來源中變更的資料更新資料庫。 只有在資料來源已連接到 SQL Server 或 Microsoft Office Access 資料庫等後端資料庫時才適用。  
  
   如需有關主控制項和資料繫結的詳細資訊，請參閱[主項目和裝載控制項概觀](../vsto/host-items-and-host-controls-overview.md)並[將資料繫結至 Office 方案中的控制項](../vsto/binding-data-to-controls-in-office-solutions.md)。  
  
   [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="update-the-in-memory-data-source"></a>更新記憶體中的資料來源  
 根據預設，啟用簡單資料繫結的主控制項 (Word 文件上的內容控制項或 Excel 工作表上的具名範圍控制項)，不會將資料變更儲存至記憶體內部資料來源。 也就是說，當使用者變更主控制項中的值，並接著移動離開該控制項時，這個控制項中的新值並不會自動儲存至資料來源。  
  
 若要將資料儲存至資料來源，您可以撰寫程式碼，以更新資料來源，以回應特定的事件，在執行階段，或您可以設定要在控制項中的值變更時，會自動更新資料來源的控制項。  
  
 您不需要將 <xref:Microsoft.Office.Tools.Excel.ListObject> 變更儲存至記憶體內部資料來源。 當您將 <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項繫結至資料時， <xref:Microsoft.Office.Tools.Excel.ListObject> 控制項會自動將變更儲存至記憶體內部資料來源，而不需要其他程式碼。  
  
### <a name="to-update-the-in-memory-data-source-at-runtime"></a>若要更新在執行階段的記憶體中的資料來源  
  
-   呼叫 <xref:System.Windows.Forms.Binding.WriteValue%2A> 物件的 <xref:System.Windows.Forms.Binding> 方法，將控制項繫結至資料來源。  
  
     下列範例會將對 Excel 工作表上 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控制項所做的變更儲存至資料來源。 這個範例假設您有名為 <xref:Microsoft.Office.Tools.Excel.NamedRange> 的 `namedRange1` 控制項，而且控制項的 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 屬性已繫結至資料來源中的欄位。  
  
     [!code-csharp[Trin_VstcoreDataExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreDataExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#1)]  
  
### <a name="automatically-update-the-in-memory-data-source"></a>自動更新記憶體中的資料來源  
 您也可以設定控制項，讓它自動更新記憶體內部資料來源。 在文件層級專案中，您可以使用程式碼或設計工具來執行這項作業。 在 VSTO 增益集專案中，您必須使用程式碼。  
  
#### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-code"></a>使用程式碼將控制項設定為自動更新記憶體內部資料來源  
  
1. 使用的 System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged 模式<xref:System.Windows.Forms.Binding>控制項繫結至資料來源的物件。 您可以使用兩種選項來更新資料來源：  
  
   - 若要驗證控制項時更新資料來源，請將這個屬性設 System.Windows.Forms.DataSourceUpdateMode.OnValidation。  
  
   - 若要更新資料來源，控制項的資料繫結屬性值變更時，請將這個屬性設 System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged。  
  
     > [!NOTE]  
     >  System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged 選項不適用於 Word 主控制項，，因為 Word 不提供文件變更或控制項變更通知。 不過，這個選項可用於 Word 文件上的 Windows Form 控制項。  
  
     下列範例會將 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控制項設定為只要控制項中的值一變更就自動更新資料來源。 這個範例假設您有名為 `namedRange1` 的 <xref:Microsoft.Office.Tools.Excel.NamedRange> 控制項，而且控制項的 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 屬性已繫結至資料來源中的欄位。  
  
     [!code-csharp[Trin_VstcoreDataExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreDataExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#19)]  
  
#### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-the-designer"></a>使用設計工具將控制項設定為自動更新記憶體內部資料來源  
  
1.  在 Visual Studio 中，以設計工具開啟 Word 文件或 Excel 活頁簿。  
  
2.  按一下您要自動更新資料來源的控制項。  
  
3.  在 [屬性]  視窗中，展開 [(DataBindings)]  屬性。  
  
4.  旁 **（進階）**  屬性中，按一下省略符號按鈕 (![VisualStudioEllipsesButton 螢幕擷取畫面](../vsto/media/vbellipsesbutton.png "VisualStudioEllipsesButton 螢幕擷取畫面"))。  
  
5.  在 [格式化與進階繫結]  對話方塊中，按一下 [資料來源更新模式]  下拉式清單，然後選取下列其中一個值：  
  
    -   若要在驗證控制項時更新資料來源，請選取 [OnValidation] 。  
  
    -   若要在控制項的資料繫結屬性值變更時更新資料來源，請選取 [OnPropertyChanged] 。  
  
        > [!NOTE]  
        >  [OnPropertyChanged]  選項不適用於 Word 主控制項，因為 Word 不提供文件變更或控制項變更通知。 不過，這個選項可用於 Word 文件上的 Windows Form 控制項。  
  
6.  關閉 [格式化與進階繫結]  對話方塊。  
  
## <a name="update-the-database"></a>更新資料庫  
 如果資料庫與記憶體內部資料來源相關聯，您必須以對資料來源所做的變更來更新資料庫。 如需有關如何更新資料庫的詳細資訊，請參閱 <<c0> [ 將資料儲存回資料庫](../data-tools/save-data-back-to-the-database.md)並[使用 TableAdapter 更新資料](../data-tools/update-data-by-using-a-tableadapter.md)。  
  
### <a name="to-update-the-database"></a>若要更新資料庫  
  
1.  呼叫控制項之 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> 的 <xref:System.Windows.Forms.BindingSource> 方法。  
  
     當您在設計階段將資料繫結控制項加入文件或活頁簿時，會自動產生 <xref:System.Windows.Forms.BindingSource> 。 <xref:System.Windows.Forms.BindingSource> 會將控制項連接到專案中的具類型資料集。 如需詳細資訊，請參閱 < [BindingSource 元件概觀](/dotnet/framework/winforms/controls/bindingsource-component-overview)。  
  
     下列程式碼範例假設您的專案包含名為 <xref:System.Windows.Forms.BindingSource> 的 `customersBindingSource`。  
  
     [!code-csharp[Trin_VstcoreDataExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreDataExcel#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#20)]  
  
2.  呼叫`Update`專案中產生的 TableAdapter 方法。  
  
     當您將資料繫結控制項加入文件或活頁簿在設計階段時，會自動產生的 TableAdapter。 TableAdapter 會連接至資料庫專案中具類型的資料集。 如需詳細資訊，請參閱 < [TableAdapter 概觀](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview)。  
  
     下列程式碼範例假設您在 Northwind 資料庫中，有 [客戶] 資料表的連接，而且您的專案包含名為 TableAdapter`customersTableAdapter`和名為具類型資料集`northwindDataSet`。  
  
     [!code-csharp[Trin_VstcoreDataExcel#21](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreDataExcel#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#21)]  
  
## <a name="see-also"></a>另請參閱  
 [資料繫結至 Office 方案中的控制項](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [將資料儲存回資料庫](../data-tools/save-data-back-to-the-database.md)    
 [使用 TableAdapter 更新資料](../data-tools/update-data-by-using-a-tableadapter.md)    
 [如何： 捲動工作表中的資料庫記錄](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [如何： 從資料庫的資料填入工作表](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [如何： 的物件的資料填入文件](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [如何： 的資料庫中的資料填入文件](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [如何： 擴展的資料服務文件](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  