---
title: 讀取 XML 資料至資料集 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- reading XML
- data access [Visual Studio], XML data
- reading files, XML
- data [Visual Studio], reading from XML files
- reading data, XML files
- XML [Visual Studio], reading
- XML documents, reading
- datasets [Visual Basic], reading XML data
ms.assetid: fae72958-0893-47d6-b3dd-9d42418418e4
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6eb85fcef78b4b856c47ccb4436d1314ae440136
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2018
ms.locfileid: "50219727"
---
# <a name="read-xml-data-into-a-dataset"></a>將 XML 資料讀入資料集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
ADO.NET 提供簡單的方法來處理 XML 資料。 在此逐步解說中，您可以建立 XML 資料載入資料集的 Windows 應用程式。 資料集即會顯示在<xref:System.Windows.Forms.DataGridView>控制項。 最後，XML 檔案的內容為基礎的 XML 結構描述會顯示在文字方塊中。  
  
 此逐步解說包含五個主要步驟：  
  
1.  建立新的專案  
  
2.  建立 XML 檔案讀入資料集  
  
3.  建立使用者介面  
  
4.  建立資料集、 讀取 XML 檔案，並顯示在<xref:System.Windows.Forms.DataGridView>控制項  
  
5.  加入程式碼來顯示 XML 結構描述中的 XML 檔案中根據<xref:System.Windows.Forms.TextBox>控制項  
  
> [!NOTE]
>  對話方塊和功能表命令，您會看到 [說明] 中所述，根據您目前使用的設定或版本可能會有所不同，您正在使用。 若要變更您的設定，在**工具**功能表上，選取**匯入和匯出設定**。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
## <a name="create-a-new-project"></a>建立新專案  
 在此步驟中，您可以建立 Visual Basic 或 Visual C# 的專案包含本逐步解說。  
  
#### <a name="to-create-the-new-windows-project"></a>建立新的 Windows 專案  
  
1.  在 [**檔案**] 功能表中，建立新的專案。  
  
2.  將專案命名為 `ReadingXML`。  
  
3.  選取  **Windows 應用程式**，然後選取**確定**。 如需詳細資訊，請參閱 <<c0> [ 用戶端應用程式](http://msdn.microsoft.com/library/2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68)。  
  
     **ReadingXML**建立專案並將其加入至**方案總管 中**。  
  
## <a name="generate-the-xml-file-to-be-read-into-the-dataset"></a>產生 XML 檔案讀入資料集  
 本逐步解說著重於 XML 資料讀入資料集，因為提供的 XML 檔案的內容。  
  
#### <a name="to-create-the-xml-file-that-will-be-read-into-the-dataset"></a>若要建立的 XML 檔案，將讀取至資料集  
  
1.  在 **專案**功能表上，選取**加入新項目**。  
  
2.  選取  **XML 檔案**，將檔案命名`authors.xml`，然後選取**新增**。  
  
     XML 檔案載入設計工具，並且可供編輯。  
  
3.  下列程式碼貼到編輯器以下 XML 宣告中：  
  
    ```xml  
    <Authors_Table>  
      <authors>  
        <au_id>172-32-1176</au_id>  
        <au_lname>White</au_lname>  
        <au_fname>Johnson</au_fname>  
        <phone>408 496-7223</phone>  
        <address>10932 Bigge Rd.</address>  
        <city>Menlo Park</city>  
        <state>CA</state>  
        <zip>94025</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>213-46-8915</au_id>  
        <au_lname>Green</au_lname>  
        <au_fname>Margie</au_fname>  
        <phone>415 986-7020</phone>  
        <address>309 63rd St. #411</address>  
        <city>Oakland</city>  
        <state>CA</state>  
        <zip>94618</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>238-95-7766</au_id>  
        <au_lname>Carson</au_lname>  
        <au_fname>Cheryl</au_fname>  
        <phone>415 548-7723</phone>  
        <address>589 Darwin Ln.</address>  
        <city>Berkeley</city>  
        <state>CA</state>  
        <zip>94705</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>267-41-2394</au_id>  
        <au_lname>Hunter</au_lname>  
        <au_fname>Anne</au_fname>  
        <phone>408 286-2428</phone>  
        <address>22 Cleveland Av. #14</address>  
        <city>San Jose</city>  
        <state>CA</state>  
        <zip>95128</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>274-80-9391</au_id>  
        <au_lname>Straight</au_lname>  
        <au_fname>Dean</au_fname>  
        <phone>415 834-2919</phone>  
        <address>5420 College Av.</address>  
        <city>Oakland</city>  
        <state>CA</state>  
        <zip>94609</zip>  
        <contract>true</contract>  
      </authors>  
    </Authors_Table>  
    ```  
  
4.  在 **檔案**功能表上，選取**儲存 authors.xml**。  
  
## <a name="create-the-user-interface"></a>建立使用者介面  
 此應用程式的使用者介面是由下列項目所組成：  
  
-   A<xref:System.Windows.Forms.DataGridView>顯示做為資料的 XML 檔案的內容控制項。  
  
-   A<xref:System.Windows.Forms.TextBox>顯示 XML 結構描述的 XML 檔案的控制項。  
  
-   兩個<xref:System.Windows.Forms.Button>控制項。  
  
    -   一個按鈕的 XML 檔案讀入資料集，並顯示在<xref:System.Windows.Forms.DataGridView>控制項。  
  
    -   第二個按鈕會在從資料集，以及透過將結構描述擷取<xref:System.IO.StringWriter>會顯示在<xref:System.Windows.Forms.TextBox>控制項。  
  
#### <a name="to-add-controls-to-the-form"></a>若要將控制項加入至表單  
  
1.  開啟`Form1`設計 檢視中。  
  
2.  從**工具箱**，拖曳到表單上的下列控制項：  
  
    -   一個<xref:System.Windows.Forms.DataGridView>控制項  
  
    -   一個<xref:System.Windows.Forms.TextBox>控制項  
  
    -   兩個<xref:System.Windows.Forms.Button>控制項  
  
3.  設定下列屬性：  
  
    |控制項|屬性|設定|  
    |-------------|--------------|-------------|  
    |`TextBox1`|**多行**|`true`|  
    ||**捲軸**|**垂直**|  
    |`Button1`|**名稱**|`ReadXmlButton`|  
    ||**Text**|`Read XML`|  
    |`Button2`|**名稱**|`ShowSchemaButton`|  
    ||**Text**|`Show Schema`|  
  
## <a name="create-the-dataset-thatreceives-the-xml-data"></a>建立資料集 thatreceives XML 資料  
 在此步驟中，您會建立新的資料集，名為`authors`。 如需有關資料集的詳細資訊，請參閱 < [Visual Studio 中的資料集工具](../data-tools/dataset-tools-in-visual-studio.md)。  
  
#### <a name="to-create-a-new-dataset-that--receives-the-xml-data"></a>若要建立新的資料集，接收 XML 資料  
  
1.  中**方案總管**，選取的原始程式檔**Form1**，然後選取**檢視表設計工具**按鈕**方案總管 中**工具列。  
  
2.  從[工具箱、 資料 索引標籤](../ide/reference/toolbox-data-tab.md)，拖曳**資料集**拖曳至**Form1**。  
  
3.  在 **加入資料集**對話方塊中，選取**不具類型資料集**，然後選取**確定**。  
  
     **DataSet1**已加入至元件匣。  
  
4.  在 **屬性**視窗中，將**名稱**並<xref:System.Data.DataSet.DataSetName%2A>屬性`AuthorsDataSet`。  
  
## <a name="create-the-event-handler-to-read-the-xml-file-into-the-dataset"></a>建立 XML 檔案讀入資料集的事件處理常式  
 **讀取 XML**按鈕會將 XML 檔案讀入資料集。 它接著會根據設定的屬性<xref:System.Windows.Forms.DataGridView>繫結至資料集的控制項。  
  
#### <a name="to-add-code-to-the-readxmlbuttonclick-event-handler"></a>若要將程式碼新增至 ReadXmlButton_Click 事件處理常式  
  
1.  中**方案總管**，選取**Form1**，然後選取**檢視表設計工具**按鈕**方案總管 中**工具列。  
  
2.  選取 [**讀取 XML** ] 按鈕。  
  
     **程式碼編輯器**會在開啟`ReadXmlButton_Click`事件處理常式。  
  
3.  輸入下列程式碼插入`ReadXmlButton_Click`事件處理常式：  
  
     [!code-csharp[VbRaddataFillingAndExecuting#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form1.cs#2)]
     [!code-vb[VbRaddataFillingAndExecuting#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form1.vb#2)]  
  
4.  在 `ReadXMLButton_Click`事件處理常式程式碼，變更`filepath =`正確路徑的項目。  
  
## <a name="create-the-event-handler-to-display-the-schema-in-the-textbox"></a>建立事件處理常式，若要在文字方塊中顯示的結構描述  
 **顯示的結構描述** 按鈕會建立<xref:System.IO.StringWriter>物件，會填入結構描述，並會顯示在<xref:System.Windows.Forms.TextBox>控制項。  
  
#### <a name="to-add-code-to-the-showschemabuttonclick-event-handler"></a>若要將程式碼新增至 ShowSchemaButton_Click 事件處理常式  
  
1.  在 **方案總管 中**，選取**Form1**，然後選取**檢視表設計工具** 按鈕。  
  
2.  選取 [**顯示的結構描述**] 按鈕。  
  
     **程式碼編輯器**會在開啟`ShowSchemaButton_Click`事件處理常式。  
  
3.  輸入下列程式碼插入`ShowSchemaButton_Click`事件處理常式。  
  
     [!code-csharp[VbRaddataFillingAndExecuting#3](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/CS/Form1.cs#3)]
     [!code-vb[VbRaddataFillingAndExecuting#3](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataFillingAndExecuting/VB/Form1.vb#3)]  
  
## <a name="test-the-form"></a>測試表單  
 您現在可以測試表單，以確定它如預期般運作。  
  
#### <a name="to-test-the-form"></a>若要測試表單  
  
1.  選取  **F5**執行應用程式。  
  
2.  選取 [**讀取 XML** ] 按鈕。  
  
     DataGridView 中顯示 XML 檔案的內容。  
  
3.  選取 [**顯示的結構描述**] 按鈕。  
  
     文字方塊會顯示 XML 檔案的 XML 結構描述。  
  
## <a name="next-steps"></a>後續步驟  
 本逐步解說會說明 XML 檔案讀入資料集，以及建立結構描述的 XML 檔案的內容為基礎的基本概念。 以下是接下來，您可能會執行一些工作：  
  
-   編輯資料集並將它寫回為 XML 中的資料。 如需詳細資訊，請參閱<xref:System.Data.DataSet.WriteXml%2A>。  
  
-   編輯資料集中的資料，並寫出至資料庫。 如需詳細資訊，請參閱 <<c0> [ 儲存資料](../data-tools/saving-data.md)。  
  
## <a name="see-also"></a>另請參閱  
 [資料逐步解說](http://msdn.microsoft.com/library/15a88fb8-3bee-4962-914d-7a1f8bd40ec4)   
 [存取 Visual Studio 中的資料](../data-tools/accessing-data-in-visual-studio.md)   
 [準備您的應用程式接收資料](http://msdn.microsoft.com/library/c17bdb7e-c234-4f2f-9582-5e55c27356ad)   
 [Visual Studio 中的 XML 工具](../xml-tools/xml-tools-in-visual-studio.md)

