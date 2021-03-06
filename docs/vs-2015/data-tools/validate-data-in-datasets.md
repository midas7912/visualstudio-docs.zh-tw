---
title: 驗證資料集中 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DataTable.ColumnChanging
- System.Data.DataTable.ColumnChanging
- System.Data.DataTable.RowChanging
- DataTable.RowChanging
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data validation, datasets
- data validation
- validating data, datasets
- updating datasets, validating data
ms.assetid: 79500596-1e4d-478e-a991-a636fd73a622
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fa90ddb397d1c18e88ab8f25e2a0c3aee3e4d9a5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891124"
---
# <a name="validate-data-in-datasets"></a>驗證資料集中的資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
驗證資料是資料物件中所輸入的值符合的條件約束的資料集結構描述中的確認程序。 驗證程序也會確認這些值會遵循您的應用程式所建立的規則。 它是個不錯的做法，驗證資料，再將更新傳送至基礎資料庫。 這會減少錯誤，以及可能的應用程式與資料庫之間的往返次數。  
  
 您可以確認正在寫入至資料集的資料有效，藉由建置至本身的資料集的驗證檢查。 資料集可以檢查資料，不論如何執行更新時，直接由控制項在表單中，在一個元件，或以其他方式。 資料集是您的應用程式 （不同於後端資料庫） 的一部分，因為它是建置應用程式特定驗證的合理位置。  
  
 將驗證新增至您的應用程式的最佳位置是資料集的部分類別檔案中。 在 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]或[!INCLUDE[csprcs](../includes/csprcs-md.md)]，開啟**Dataset 設計工具**，連按兩下您要建立驗證的資料行或資料表。 此動作會自動建立<xref:System.Data.DataTable.ColumnChanging>或<xref:System.Data.DataTable.RowChanging>事件處理常式。 如需詳細資訊，請參閱 <<c0> [ 如何： 驗證期間資料行變更的資料](http://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5)或是[如何： 驗證期間資料列變更的資料](http://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc)。 如需完整範例，請參閱 <<c0> [ 逐步解說： 將驗證新增至資料集](http://msdn.microsoft.com/library/09351fab-d670-45e3-b53a-a944eff717e7)。  
  
## <a name="validate-data"></a>驗證資料  
 在資料集內的驗證可以透過下列方式來完成：  
  
- 藉由建立您自己的應用程式特定驗證中個別資料行的值變更期間檢查。  如需詳細資訊，請參閱 <<c0> [ 如何： 驗證期間資料行變更的資料](http://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5)。  
  
- 藉由建立您自己應用程式特定的驗證，可以檢查在整個資料值的資料會變更資料列。 如需詳細資訊，請參閱 <<c0> [ 如何： 驗證期間資料列變更的資料](http://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc)。  
  
- 建立金鑰，unique 條件約束等做為實際的結構描述定義的資料集的一部分。 如需有關驗證併入結構描述定義的詳細資訊，請參閱[限制為包含唯一值的 DataColumn](http://msdn.microsoft.com/library/8ca21f77-b99a-47a7-a656-7cfd7a1bd9df)。  
  
- 藉由設定的屬性<xref:System.Data.DataColumn>物件，例如<xref:System.Data.DataColumn.MaxLength%2A>， <xref:System.Data.DataColumn.AllowDBNull%2A>，和<xref:System.Data.DataColumn.Unique%2A>。  
  
  多個事件所引發<xref:System.Data.DataTable>物件記錄中進行變更時：  
  
- <xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.ColumnChanged>期間和每個個別的資料行的變更之後，會引發事件。 <xref:System.Data.DataTable.ColumnChanging>事件很有用，當您想要驗證特定的資料行中的變更。 提議的變更的相關資訊會傳遞做為引數與事件。 如需詳細資訊，請參閱 <<c0> [ 如何： 驗證期間資料行變更的資料](http://msdn.microsoft.com/library/a2680600-67b6-4a40-a77e-b5bc638281c5)。  
  
- <xref:System.Data.DataTable.RowChanging>和<xref:System.Data.DataTable.RowChanged>期間和之後，會引發事件的資料列變更。 <xref:System.Data.DataTable.RowChanging>事件是較一般。 表示資料列，在某處發生變更，但您不知道哪個資料行已變更。 如需詳細資訊，請參閱 <<c0> [ 如何： 驗證期間資料列變更的資料](http://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc)。  
  
  根據預設，每個資料行的變更，因此引發四個事件。 第一個是<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.ColumnChanged>正在變更之特定資料行的事件。 接下來是<xref:System.Data.DataTable.RowChanging>和<xref:System.Data.DataTable.RowChanged>事件。 如果要對資料列進行多項變更，則會引發事件，每個變更。  
  
> [!NOTE]
>  資料列<xref:System.Data.DataRow.BeginEdit%2A>方法會關閉<xref:System.Data.DataTable.RowChanging>和<xref:System.Data.DataTable.RowChanged>每個個別資料行變更之後的事件。 在此情況下，不會引發事件之前<xref:System.Data.DataRow.EndEdit%2A>已呼叫方法，當<xref:System.Data.DataTable.RowChanging>和<xref:System.Data.DataTable.RowChanged>會一次引發事件。 如需詳細資訊，請參閱 <<c0> [ 填入 dataset 時關閉條件約束](../data-tools/turn-off-constraints-while-filling-a-dataset.md)。  
  
 您選擇的事件取決於您想要驗證細微程度。 如果這是很重要，您在資料行的變更時立即攔截錯誤，請使用組建驗證<xref:System.Data.DataTable.ColumnChanging>事件。 否則，請使用<xref:System.Data.DataTable.RowChanging>事件，可能會導致一次擷取數個錯誤。 此外，如果您的資料結構，讓一個資料行的值會根據另一個資料行的內容進行驗證，然後執行驗證期間<xref:System.Data.DataTable.RowChanging>事件。  
  
 在更新記錄時<xref:System.Data.DataTable>物件會引發如發生變更，並進行變更之後，您可以回應到的事件。  
  
 如果您的應用程式會使用具類型資料集，您可以建立強型別的事件處理常式。 這會新增四個額外的具型別的的事件，您可以建立處理常式： `dataTableNameRowChanging`， `dataTableNameRowChanged`， `dataTableNameRowDeleting`，和`dataTableNameRowDeleted`。 這些具類型的事件處理常式傳遞的引數，包括您的資料表的資料行名稱，讓您更輕鬆地寫入和讀取程式碼。  
  
## <a name="data-update-events"></a>資料更新事件  
  
|Event - 事件|描述|  
|-----------|-----------------|  
|<xref:System.Data.DataTable.ColumnChanging>|正在變更的資料行中的值。 事件傳遞的資料列和資料行，以及建議的新值。|  
|<xref:System.Data.DataTable.ColumnChanged>|已變更資料行中的值。 事件傳遞的資料列和資料行，以及建議的值。|  
|<xref:System.Data.DataTable.RowChanging>|對所做的變更<xref:System.Data.DataRow>物件即將認可回資料集。 如果您未呼叫<xref:System.Data.DataRow.BeginEdit%2A>方法中，<xref:System.Data.DataTable.RowChanging>每個資料行的變更都會引發事件之後立即<xref:System.Data.DataTable.ColumnChanging>在引發事件。 如果您呼叫<xref:System.Data.DataRow.BeginEdit%2A>進行變更前，<xref:System.Data.DataTable.RowChanging>只有在您呼叫時，才會引發事件<xref:System.Data.DataRow.EndEdit%2A>方法。<br /><br /> 事件會傳遞給您，資料列，以及值，指出正在執行何種動作 （變更、 插入、 等等）。|  
|<xref:System.Data.DataTable.RowChanged>|已變更的資料列。 事件會傳遞給您，資料列，以及值，指出正在執行何種動作 （變更、 插入、 等等）。|  
|<xref:System.Data.DataTable.RowDeleting>|正在刪除資料列。 事件會傳遞給您，資料列，以及值，指出正在執行何種動作 (delete)。|  
|<xref:System.Data.DataTable.RowDeleted>|已刪除資料列。 事件會傳遞給您，資料列，以及值，指出正在執行何種動作 (delete)。|  
  
 <xref:System.Data.DataTable.ColumnChanging>， <xref:System.Data.DataTable.RowChanging>，和<xref:System.Data.DataTable.RowDeleting>更新程序期間引發事件。 您可以使用這些事件，以驗證資料，或執行其他類型的處理。 因為在這些事件時正在執行更新，可以取消藉由擲回例外狀況，這可防止從更新完成。  
  
 <xref:System.Data.DataTable.ColumnChanged>，<xref:System.Data.DataTable.RowChanged>和<xref:System.Data.DataTable.RowDeleted>事件是通知更新已成功完成時所引發的事件。 當您想要採取進一步的動作成功更新為基礎，這些事件會很有用。  
  
## <a name="validate-data-during-column-changes"></a>在資料行變更期間驗證資料  
  
> [!NOTE]
>  **Dataset 設計工具**建立部分類別中的驗證邏輯加入至資料集。 設計工具所產生的資料集不會刪除，或變更的部分類別中的任何程式碼。  
  
 您可以在回應中的資料行的值變更時驗證資料<xref:System.Data.DataTable.ColumnChanging>事件。 這個事件引發時，會傳遞的事件引數 (<xref:System.Data.DataColumnChangeEventArgs.ProposedValue%2A>)，包含目前的資料行建議的值。 根據內容`e.ProposedValue`，您可以：  
  
- 接受建議的值，不執行任何動作。  
  
- 藉由設定資料行錯誤拒絕建議的值 (<xref:System.Data.DataRow.SetColumnError%2A>) 從在資料行變更的事件處理常式。  
  
- 選擇性地使用<xref:System.Windows.Forms.ErrorProvider>控制項來顯示錯誤訊息給使用者。 如需詳細資訊，請參閱 < [ErrorProvider 元件](http://msdn.microsoft.com/library/c0f2e231-c5c9-413d-a507-75af2db499b6)。  
  
  您也可以驗證執行期間<xref:System.Data.DataTable.RowChanging>事件。 如需詳細資訊，請參閱 <<c0> [ 如何： 驗證期間資料列變更的資料](http://msdn.microsoft.com/library/afc03c77-dfed-4302-9376-929400468ecc)。  
  
## <a name="validate-data-during-row-changes"></a>在資料列變更期間驗證資料  
 您可以撰寫程式碼，以確認您想要驗證每個資料的行包含符合您的應用程式的資料。 藉由設定資料行，指出它包含錯誤，是否無法接受建議的值執行這項操作。 下列範例會設定資料行發生錯誤時`Quantity`資料行是 0 或更小。 資料列變更的事件處理常式應該類似下列的範例。  
  
#### <a name="to-validate-data-when-a-row-changes-visual-basic"></a>若要驗證資料的資料列時變更 (Visual Basic)  
  
1.  開啟您的資料集，在**Dataset 設計工具**。 如需詳細資訊，請參閱 <<c0> [ 如何： 以 Dataset 設計工具中開啟資料集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  按兩下您想要驗證之資料表標題列。 此動作會自動建立<xref:System.Data.DataTable.RowChanging>事件處理常式<xref:System.Data.DataTable>資料集的部分類別檔案中。  
  
    > [!TIP]
    >  若要建立的資料列變更的事件處理常式的資料表名稱的左邊按兩下。 如果您按兩下資料表名稱時，您可以編輯它。  
  
     [!code-vb[VbRaddataValidating#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataValidating/VB/NorthwindDataSet.vb#3)]  
  
#### <a name="to-validate-data-when-a-row-changes-c"></a>若要驗證資料的資料列時變更 (C#)  
  
1.  開啟您的資料集，在**Dataset 設計工具**。 如需詳細資訊，請參閱 <<c0> [ 如何： 以 Dataset 設計工具中開啟資料集](http://msdn.microsoft.com/library/36fc266f-365b-42cb-aebb-c993dc2c47c3)。  
  
2.  按兩下您想要驗證之資料表標題列。 此動作會建立部分類別檔案<xref:System.Data.DataTable>。  
  
    > [!NOTE]
    >  **Dataset 設計工具**不會自動建立的事件處理常式<xref:System.Data.DataTable.RowChanging>事件。 您必須建立方法以處理<xref:System.Data.DataTable.RowChanging>事件，並執行程式碼，來連結資料表的初始設定方法中的事件。  
  
3.  將下列程式碼複製到的部分類別中：  
  
    ```  
    public override void EndInit()  
    {  
        base.EndInit();  
        Order_DetailsRowChanging += TestRowChangeEvent;  
    }  
  
    public void TestRowChangeEvent(object sender, Order_DetailsRowChangeEvent e)  
    {  
        if ((short)e.Row.Quantity <= 0)  
        {  
            e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");  
        }  
        else  
        {  
            e.Row.SetColumnError("Quantity", "");  
        }  
    }  
    ```  
  
## <a name="to-retrieve-changed-rows"></a>若要擷取變更的資料列  
 資料表中的每個資料列具有<xref:System.Data.DataRow.RowState%2A>屬性會追蹤該資料列的目前狀態的使用中的值，<xref:System.Data.DataRowState>列舉型別。 您可以從資料集或資料的資料表傳回變更的資料列，藉由呼叫`GetChanges`方法<xref:System.Data.DataSet>或<xref:System.Data.DataTable>。 您可以在呼叫之前有變更來確認`GetChanges`藉由呼叫<xref:System.Data.DataSet.HasChanges%2A>資料集的方法。 如需詳細資訊<xref:System.Data.DataSet.HasChanges%2A>，請參閱 <<c2> [ 如何： 檢查是否有變更的資料列](http://msdn.microsoft.com/library/af160d20-472b-4c13-8f15-75480c39a653)。  
  
> [!NOTE]
>  您將變更認可到資料集或資料的資料表之後 (藉由呼叫<xref:System.Data.DataSet.AcceptChanges%2A>方法)，則`GetChanges`方法會傳回任何資料。 如果您的應用程式需要處理變更的資料列，您必須處理的變更，然後再呼叫`AcceptChanges`方法。  
  
 呼叫<xref:System.Data.DataSet.GetChanges%2A>的資料集或資料表的方法會傳回新的資料集或資料表，其中包含已變更的唯一記錄。 如果您想要取得特定的記錄 — 例如，新的記錄或修改的記錄，您可以將傳遞的值<xref:System.Data.DataRowState>列舉型別做為參數`GetChanges`方法。  
  
 使用<xref:System.Data.DataRowVersion>存取的資料列 （例如，原始值已在處理它之前的資料列中） 的不同版本的列舉。  
  
#### <a name="to-get-all-changed-records-from-a-dataset"></a>若要取得所有已變更的記錄從資料集  
  
-   呼叫<xref:System.Data.DataSet.GetChanges%2A>資料集的方法。  
  
     下列範例會建立新的資料集，稱為`changedRecords`並填入所有已變更的記錄，從另一個資料集，稱為`dataSet1`。  
  
     [!code-csharp[VbRaddataEditing#14](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#14)]
     [!code-vb[VbRaddataEditing#14](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#14)]  
  
#### <a name="to-get-all-changed-records-from-a-data-table"></a>若要取得所有已變更的記錄資料表的資料  
  
-   呼叫<xref:System.Data.DataTable.GetChanges%2A>DataTable 的方法。  
  
     下列範例會建立新的資料表呼叫`changedRecordsTable`並填入所有已變更的記錄，從另一個資料表，稱為`dataTable1`。  
  
     [!code-csharp[VbRaddataEditing#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#15)]
     [!code-vb[VbRaddataEditing#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#15)]  
  
#### <a name="to-get-all-records-that-have-a-specific-row-state"></a>若要取得的特定狀態的所有記錄  
  
-   呼叫`GetChanges`方法的資料集或資料表和傳遞<xref:System.Data.DataRowState>做為引數的列舉值。  
  
     下列範例示範如何建立新的資料集，稱為`addedRecords`，並填入只記錄已新增至`dataSet1`資料集。  
  
     [!code-csharp[VbRaddataEditing#16](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#16)]
     [!code-vb[VbRaddataEditing#16](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#16)]  
  
-   下列範例示範如何傳回最近加入的所有記錄`Customers`資料表：  
  
     [!code-csharp[VbRaddataEditing#17](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#17)]
     [!code-vb[VbRaddataEditing#17](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#17)]  
  
## <a name="access-the-original-version-of-a-datarow"></a>存取 DataRow 的原始版本  
 資料集將資料列變更時，會保留原始 (<xref:System.Data.DataRowVersion>) 和新 (<xref:System.Data.DataRowVersion>) 的資料列版本。 比方說，之前呼叫`AcceptChanges`方法中，您的應用程式可以存取記錄的不同版本 (如中所定義<xref:System.Data.DataRowVersion>列舉型別) 並據以處理變更。  
  
> [!NOTE]
>  不同版本的資料列存在，只有經編輯之後，它之前`AcceptChanges`已呼叫方法。 之後`AcceptChanges`已呼叫方法、 目前和原始的版本都相同。  
  
 傳遞<xref:System.Data.DataRowVersion>值資料行索引 （或資料行名稱做為字串） 以及傳回該資料行的特定資料列版本的值。 已變更的資料行識別期間<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.ColumnChanged>事件。 這是要檢查不同的資料列版本進行驗證的好時機。 不過，如果您已暫時停用條件約束，將不會引發這些事件，而且您必須以程式設計方式識別哪些資料行已變更。 您可以逐一查看<xref:System.Data.DataTable.Columns%2A>集合，並比較不同<xref:System.Data.DataRowVersion>值。  
  
#### <a name="to-get-the-original-version-of-a-record"></a>若要取得一筆資料錄的原始版本  
  
-   存取資料行的值，藉由傳入<xref:System.Data.DataRowVersion>您想要傳回的資料列。  
  
     下列範例示範如何使用<xref:System.Data.DataRowVersion>若要取得的原始值的值`CompanyName`欄位中<xref:System.Data.DataRow>:  
  
     [!code-csharp[VbRaddataEditing#21](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#21)]
     [!code-vb[VbRaddataEditing#21](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#21)]  
  
## <a name="access-the-current-version-of-a-datarow"></a>存取目前版本的 DataRow  
  
#### <a name="to-get-the-current-version-of-a-record"></a>若要取得目前的版本記錄的  
  
-   存取的資料行的值，然後將參數加入索引，表示您想要傳回的資料列版本。  
  
     下列範例示範如何使用<xref:System.Data.DataRowVersion>若要取得的目前值的值`CompanyName`欄位中<xref:System.Data.DataRow>:  
  
     [!code-csharp[VbRaddataEditing#22](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataEditing/CS/Form1.cs#22)]
     [!code-vb[VbRaddataEditing#22](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataEditing/VB/Form1.vb#22)]  
  
## <a name="see-also"></a>另請參閱  
 [建立和編輯具類型資料集](../data-tools/creating-and-editing-typed-datasets.md)   
 [如何：連接至資料庫中的資料](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [如何： 驗證 Windows Form DataGridView 控制項中的資料](http://msdn.microsoft.com/library/d10aef35-701e-4a3c-a684-2a2ed1aeaca6)   
 [操作說明：使用 Windows Forms ErrorProvider 元件顯示表單驗證的錯誤圖示](http://msdn.microsoft.com/library/3b681a32-9db4-497b-a34b-34980eabee46)

