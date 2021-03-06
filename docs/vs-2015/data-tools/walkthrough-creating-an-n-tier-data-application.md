---
title: 逐步解說： 建立 N-tier 資料應用程式 |Microsoft Docs
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
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
caps.latest.revision: 51
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 37876502a464e263ebd6803216b29bd62b65af5c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49890175"
---
# <a name="walkthrough-creating-an-n-tier-data-application"></a>逐步解說：建立 N-Tier 資料應用程式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
N-層 * 資料應用程式是應用程式存取資料而且分成多個邏輯層，或*層*。 將應用程式元件分成離散層級，可增加應用程式的可維護性和延展性。 原因是可以更輕鬆地採用套用至單一層級的新技術，而且您不需要重新設計整個方案。 多層式架構包括呈現層、中介層和資料層。 中介層通常包括資料存取層、商務邏輯層和共用元件 (如驗證 (authentication) 和驗證 (validation))。 資料層包括關聯式資料庫。 多層式架構應用程式通常會將敏感性資訊儲存至中介層的資料存取層，以與存取呈現層的終端使用者隔離。 如需詳細資訊，請參閱 <<c0> [ 多層式架構資料應用程式概觀](../data-tools/n-tier-data-applications-overview.md)。  
  
 其中一種在多層式架構應用程式中分為各種層級的方式，是針對您要併入應用程式中的每個層級建立離散專案。 具類型資料集所含的 `DataSet Project` 屬性可以決定所產生的資料集和 `TableAdapter` 程式碼應該進入的專案。  
  
 本逐步解說示範如何以不同的資料集和`TableAdapter`程式碼分成離散類別庫專案，使用**Dataset 設計工具**。 您可將資料集和 TableAdapter 程式碼之後，您會建立[Windows Communication Foundation 服務和 Visual Studio 中的 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)来呼叫到資料存取層的服務。 最後，您將建立 Windows Forms 應用程式做為呈現層。 此層級會存取資料服務中的資料。  
  
 在這個逐步解說期間，您將執行下列步驟：  
  
- 建立含有多個專案的新多層式架構方案。  
  
- 將兩個類別庫專案加入至多層式架構方案。  
  
- 使用建立具類型資料集**資料來源組態精靈**。  
  
- 將產生[TableAdapters](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)和資料集的程式碼分成離散專案。  
  
- 建立要呼叫到資料存取層的 Windows Communication Foundation (WCF) 服務。  
  
- 在服務中建立函式，以擷取資料存取層中的資料。  
  
- 建立 Windows Form 應用程式，以做為呈現層。  
  
- 建立繫結至資料來源的 Windows Form 控制項。  
  
- 撰寫程式碼以填入資料表。  
  
  ![影片連結](../data-tools/media/playvideo.gif "PlayVideo")如本主題的影片版本，請參閱[影片-如何： 建立多層式架構資料應用程式](http://go.microsoft.com/fwlink/?LinkId=115188)。  
  
## <a name="prerequisites"></a>必要條件  
 若要完成這個逐步解說，您需要：  
  
-   Northwind 範例資料庫的存取權。 如需詳細資訊，請參閱 <<c0> [ 如何： 安裝範例資料庫](../data-tools/how-to-install-sample-databases.md)。  
  
## <a name="creating-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>建立多層式架構方案和類別庫以保留資料集 (DataEntityTier)  
 這個逐步解說的第一個步驟是建立一個方案和兩個類別庫專案。 第一個類別庫將會保留資料集 (產生的具類型 DataSet 類別以及將保留應用程式資料的 DataTables)。 此專案是用做應用程式的資料實體層，而且通常位於中介層。 [建立和編輯具類型資料集](../data-tools/creating-and-editing-typed-datasets.md)用來建立初始資料集，並自動將程式碼分成兩個類別程式庫。  
  
> [!NOTE]
>  請務必正確地命名專案和方案為再按一下 **確定**。 這麼做可以讓您輕鬆地完成這個逐步解說。  
  
#### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>建立多層式架構方案和 DataEntityTier 類別庫  
  
1.  從**檔案** 功能表中，建立新的專案。  
  
    > [!NOTE]
    >  **Dataset 設計工具**支援[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]和 C# 專案。 請使用下列其中一種語言，來建立新的專案。  
  
2.  在 **新的專案**對話方塊的 **專案類型**窗格中，按一下**Windows**。  
  
3.  按一下 **類別庫**範本。  
  
4.  將專案命名為**DataEntityTier**。  
  
5.  將方案命名為**NTierWalkthrough**。  
  
6.  按一下 [確定 **Deploying Office Solutions**]。  
  
     會建立含有 DataEntityTier 專案的 NTierWalkthrough 方案，並將其加入**方案總管 中**。  
  
## <a name="creating-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>建立類別庫以保留 TableAdapter (DataAccessTier)  
 建立 DataEntityTier 專案之後的下一個步驟是建立另一個類別庫專案。 此專案將保留產生`TableAdapter`s，稱為*資料存取層*應用程式。 資料存取層包含連接至資料庫所需的資訊，而且通常位於中介層。  
  
#### <a name="to-create-the-new-class-library-for-the-tableadapters"></a>建立 TableAdapter 的新類別庫  
  
1.  從**檔案** 功能表中，將新專案加入至 NTierWalkthrough 方案。  
  
2.  在**新的專案**對話方塊中，於**範本**窗格中，按一下 **類別庫**。  
  
3.  將專案命名為**DataAccessTier**然後按一下**確定**。  
  
     隨即建立 DataAccessTier 專案，並將它加入至 NTierWalkthrough 方案。  
  
## <a name="creating-the-dataset"></a>建立資料集  
 下一個步驟是建立具類型資料集。 在單一專案中，建立具有資料集類別 (包括 DataTables 類別) 和 `TableAdapter` 類別的具類型資料集  (所有類別都會產生到單一檔案)。當您將資料集和 `TableAdapter` 分隔到不同的專案時，是將資料集類別移至另一個專案，而 `TableAdapter` 類別會保留在原始專案中。 因此，在最後會包含 `TableAdapter` 的專案 (DataAccessTier 專案) 中建立資料集。 您將使用來建立資料集**資料來源組態精靈**。  
  
> [!NOTE]
>  您必須具有 Northwind 範例資料庫的存取權，才能建立連接。 如需有關如何設定 Northwind 範例資料庫的資訊，請參閱 <<c0> [ 如何： 安裝範例資料庫](../data-tools/how-to-install-sample-databases.md)。  
  
#### <a name="to-create-the-dataset"></a>建立資料集  
  
1.  按一下 [在 DataAccessTier**方案總管] 中**。  
  
2.  按一下 [ **資料** ] 功能表上的 [ **顯示資料來源**]。  
  
3.  在 [**資料來源**] 視窗中，按一下**加入新的資料來源**啟動**資料來源組態精靈**。  
  
4.  在 **選擇資料來源類型**頁面上，按一下**資料庫**，然後按一下 **下一步**。  
  
5.  在 **選擇資料連接**頁面上，執行下列動作之一：  
  
     如果下拉式清單中提供 Northwind 範例資料庫的資料連接，請按一下這個資料連接。  
  
     -或-  
  
     按一下 [**新的連線**來開啟**加入連接**] 對話方塊。  
  
6.  如果資料庫需要密碼，請選取選項來加入敏感性資料，然後按 [下一步] 。  
  
    > [!NOTE]
    >  如果您已選取本機資料庫檔案 (而非連接至 SQL Server)，則系統可能會詢問您是否要將檔案加入至專案。 按一下 **是**將資料庫檔案加入至專案。  
  
7.  按一下 **下一步**上**將連接字串儲存到應用程式組態檔**頁面。  
  
8.  在 [選擇您的資料庫物件]  頁面上，展開 [資料表]  節點。  
  
9. 按一下核取方塊**客戶**並**訂單**資料表，然後再按一下**完成**。  
  
     NorthwindDataSet 會加入至 DataAccessTier 專案，而且會出現在**Zdroje dat**視窗。  
  
## <a name="separating-the-tableadapters-from-the-dataset"></a>分隔 TableAdapter 與資料集  
 在您建立資料集之後，請分隔產生的資料集類別與 TableAdapter。 您可以設定**資料集 Project**屬性，以在其中儲存分開之資料集類別的專案的名稱。  
  
#### <a name="to-separate-the-tableadapters-from-the-dataset"></a>分隔 TableAdapter 與資料集  
  
1. 按兩下**NorthwindDataSet.xsd**中**方案總管**若要開啟中的資料集**Dataset 設計工具**。  
  
2. 按一下設計工具上的空白區域。  
  
3. 找出**資料集 Project**中的節點**屬性**視窗。  
  
4. 在 **資料集 Project**清單中，按一下**DataEntityTier**。  
  
5. 在 [ **建置** ] 功能表上，按一下 [ **建置方案**]。  
  
   資料集和 TableAdapter 會分隔到兩個類別庫專案。 原本包含整個資料集的專案 (DataAccessTier) 現在只會包含 TableAdapter。 中指定的專案**資料集 Project**屬性 (DataEntityTier) 包含具類型資料集： NorthwindDataSet.Dataset.Designer.vb （或 NorthwindDataSet.Dataset.Designer.cs）。  
  
> [!NOTE]
>  當您分隔資料集和 Tableadapter (藉由設定**資料集 Project**屬性)，在專案中的現有部份資料集類別不會自動移動。 現有資料集部分類別必須手動移至資料集專案。  
  
## <a name="creating-a-new-service-application"></a>建立新的服務應用程式  
 因為這個逐步解說示範如何使用 WCF 服務來存取資料存取層，所以請建立新的 WCF 應用程式服務。  
  
#### <a name="to-create-a-new-wcf-service-application"></a>建立新的 WCF 應用程式服務  
  
1.  從**檔案** 功能表中，將新專案加入至 NTierWalkthrough 方案。  
  
2.  在 **新的專案**對話方塊的 **專案類型**窗格中，按一下**WCF**。 在 **範本**窗格中，按一下**WCF 服務程式庫**。  
  
3.  將專案命名為**DataService**然後按一下**確定**。  
  
     隨即建立 DataService 專案，並將它加入至 NTierWalkthrough 方案。  
  
## <a name="creating-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>在資料存取層中建立方法，以傳回 Customers 和 Orders 資料  
 資料服務必須在資料存取層中呼叫兩種方法：GetCustomers 和 GetOrders。 這些方法會傳回 Northwind Customers 和 Orders 資料表。 在 DataAccessTier 專案中，建立 GetCustomers 和 GetOrders 方法。  
  
#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>在資料存取層中建立可傳回 Customers 資料表的方法  
  
1.  在 **方案總管**，連按兩下 [NorthwindDataset.xsd]，以開啟中的資料集[建立及編輯具類型資料集](../data-tools/creating-and-editing-typed-datasets.md)。  
  
2.  CustomersTableAdapter 上按一下滑鼠右鍵，然後按一下 **加入查詢**來開啟[編輯 TableAdapters](../data-tools/editing-tableadapters.md)。  
  
3.  在 [**選擇命令類型**頁面上，保留預設值**使用 SQL 陳述式**然後按一下**下一步]**。  
  
4.  在上**選擇查詢類型**頁面上，保留預設值**會傳回資料列選取**，按一下 [**下一步]**。  
  
5.  在 [**指定 SQL SELECT 陳述式**頁面上，保留預設查詢，然後按一下**下一步]**。  
  
6.  在上**選擇要產生的方法**頁面上，輸入**GetCustomers** for**方法名稱**中**傳回 DataTable**一節。  
  
7.  按一下 [ **完成**]。  
  
#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>在資料存取層中建立可傳回 Orders 資料表的方法  
  
1.  OrdersTableAdapter 上按一下滑鼠右鍵，然後按一下 **加入查詢**。  
  
2.  在 [**選擇命令類型**頁面上，保留預設值**使用 SQL 陳述式**然後按一下**下一步]**。  
  
3.  在上**選擇查詢類型**頁面上，保留預設值**會傳回資料列選取**，按一下 [**下一步]**。  
  
4.  在 [**指定 SQL SELECT 陳述式**頁面上，保留預設查詢，然後按一下**下一步]**。  
  
5.  在上**選擇要產生的方法**頁面上，輸入**GetOrders** for**方法名稱**中**傳回 DataTable**一節。  
  
6.  按一下 [ **完成**]。  
  
7.  在 [ **建置** ] 功能表上，按一下 [ **建置方案**]。  
  
## <a name="adding-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>將資料實體和資料存取層的參考加入至資料服務  
 因為資料服務需要來自資料集和 TableAdapter 的資訊，所以請加入 DataEntityTier 和 DataAccessTier 專案的參考。  
  
#### <a name="to-add-references-to-the-data-service"></a>加入資料服務的參考  
  
1.  以滑鼠右鍵按一下中的，於 DataService**方案總管] 中**，按一下 [**加入參考**。  
  
2.  按一下 [**專案**索引標籤中**加入參考**] 對話方塊。  
  
3.  選取這兩個**DataAccessTier**並**DataEntityTier**專案。  
  
4.  按一下 [確定 **Deploying Office Solutions**]。  
  
## <a name="adding-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>將函式加入至服務，以在資料存取層中呼叫 GetCustomers 和 GetOrders 方法  
 現在，資料存取層包含方法可以傳回資料、在資料服務中建立方法以呼叫資料存取層中的方法。  
  
> [!NOTE]
>  針對 C# 專案，您必須加入下列程式碼的 `System.Data.DataSetExtensions` 組件參考以進行編譯。  
  
#### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>在資料服務中建立 GetCustomers 和 GetOrders 函式  
  
1.  在  **DataService**專案中，按兩下 IService1.vb 或 IService1.cs。  
  
2.  新增下列程式碼底下**新增您的服務作業**註解：  
  
    ```vb  
    <OperationContract()> _  
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable  
  
    <OperationContract()> _  
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable  
    ```  
  
    ```csharp  
    [OperationContract]  
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();  
  
    [OperationContract]  
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();  
  
    ```  
  
3.  在 DataService 專案中，連按兩下 Service1.vb (或 Service1.cs)。  
  
4.  將下列程式碼加入至 Service1 類別中：  
  
    ```vb  
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers  
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter  
        Return CustomersTableAdapter1.GetCustomers()  
    End Function  
  
    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders  
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter  
        Return OrdersTableAdapter1.GetOrders()  
    End Function  
    ```  
  
    ```csharp  
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()  
    {  
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter  
             CustomersTableAdapter1  
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();  
        return CustomersTableAdapter1.GetCustomers();  
  
    }  
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()  
    {  
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter  
             OrdersTableAdapter1  
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();  
        return OrdersTableAdapter1.GetOrders();  
  
    }  
    ```  
  
5.  在 [ **建置** ] 功能表上，按一下 [ **建置方案**]。  
  
## <a name="creating-a-presentation-tier-to-display-data-from-the-data-service"></a>建立呈現層以顯示來自資料服務的資料  
 現在，方案會包含有方法可以呼叫到資料存取層的資料服務、建立另一個將呼叫到資料服務的專案，並向使用者呈現資料。 在這個逐步解說中，建立 Windows Form 應用程式；這是多層式架構應用程式的呈現層。  
  
#### <a name="to-create-the-presentation-tier-project"></a>建立呈現層專案  
  
1.  從**檔案** 功能表中，將新專案加入至 NTierWalkthrough 方案。  
  
2.  在 **新的專案**對話方塊的 **專案類型**窗格中，按一下**Windows**。 在 [範本]  窗格中，按一下 [Windows Form 應用程式] 。  
  
3.  將專案命名為**PresentationTier**然後按一下**確定**。  
  
4.  隨即建立 PresentationTier 專案，並將它加入至 NTierWalkthrough 方案。  
  
## <a name="setting-the-presentationtier-project-as-the-startup-project"></a>將 PresentationTier 專案設定為啟始專案  
 因為呈現層是用來呈現資料並與之互動的實際用戶端應用程式，所以您必須將 PresentationTier 專案設定為啟始專案。  
  
#### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>將新的呈現層專案設定為啟始專案  
  
-   在 **方案總管**，以滑鼠右鍵按一下**PresentationTier** ，按一下 **設定為啟始專案**。  
  
## <a name="adding-references-to-the-presentation-tier"></a>加入呈現層的參考  
 用戶端應用程式 PresentationTier 需要有資料服務的服務參考，才能存取服務中的方法。 此外，還需要有資料集參考，才能透過 WCF 服務啟用類型共用。 除非您透過資料服務啟用類型共用，否則呈現層將無法使用加入至部分資料集類別的程式碼。 因為您通常會將驗證這類程式碼加入至變更資料表事件的資料列和資料行，所以可能會想要從用戶端存取此程式碼。  
  
#### <a name="to-add-a-reference-to-the-presentation-tier"></a>加入呈現層的參考  
  
1.  在 **方案總管**，於 PresentationTier 上按一下滑鼠右鍵，然後按一下**加入參考**。  
  
2.  在 **加入參考** 對話方塊中，按一下**專案** 索引標籤。  
  
3.  選取  **DataEntityTier**然後按一下**確定**。  
  
#### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>加入呈現層的服務參考  
  
1.  在 **方案總管**，於 PresentationTier 上按一下滑鼠右鍵，然後按一下**加入服務參考**。  
  
2.  在 [**加入服務參考**] 對話方塊中，按一下**Discover**。  
  
3.  選取  **Service1**然後按一下**確定**。  
  
    > [!NOTE]
    >  如果您在目前電腦上有多個服務，則請選取先前在這個逐步解說中建立的服務 (含有 GetCustomers 和 GetOrders 方法的服務)。  
  
## <a name="adding-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>將 DataGridViews 加入至表單以顯示資料服務所傳回的資料  
 加入服務參考加入資料服務之後, **Zdroje dat**視窗會自動填入服務所傳回的資料。  
  
#### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>將兩個繫結 DataGridViews 的資料加入至表單  
  
1.  在 [**方案總管] 中**，選取 PresentationTier 專案。  
  
2.  在 [**資料來源**] 視窗中，展開**NorthwindDataSet**並找出**客戶**節點。  
  
3.  拖曳**客戶**節點拖曳至 Form1。  
  
4.  在 [**資料來源**] 視窗中，展開**客戶**節點並找到相關**訂單**節點 (**訂單**巢狀於**客戶**節點)。  
  
5.  將相關**訂單**節點拖曳至 Form1。  
  
6.  按兩下表單的空白區域，以建立 `Form1_Load` 事件處理常式。  
  
7.  將下列程式碼加入至 `Form1_Load` 事件處理常式。  
  
    ```vb  
    Dim DataSvc As New ServiceReference1.Service1Client  
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)  
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)  
    ```  
  
    ```csharp  
    ServiceReference1.Service1Client DataSvc =   
        new ServiceReference1.Service1Client();  
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());  
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());  
  
    ```  
  
## <a name="increasing-the-maximum-message-size-allowed-by-the-service"></a>增加服務允許的訊息大小上限  
 因為服務會傳回來自 Customers 和 Orders 資料表的資料，所以 maxReceivedMessageSize 的預設值不足以保留資料，因此必須予以增加。 在這個逐步解說中，您會將此值變更為 6553600。 您將在用戶端上變更此值，而這樣會自動更新服務參考。  
  
> [!NOTE]
>  較小的預設大小是要限制拒絕服務 (DoS) 攻擊的機率。 如需詳細資訊，請參閱<xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>。  
  
#### <a name="to-increase-the-maxreceivedmessagesize-value"></a>增加 maxReceivedMessageSize 值  
  
1.  在 [**方案總管] 中**，按兩下 PresentationTier 專案中的 app.config 檔案。  
  
2.  找出**maxReceivedMessage**大小屬性，並將值變更為`6553600`。  
  
## <a name="testing-the-application"></a>測試應用程式  
 執行應用程式。 資料是擷取自資料服務，並顯示在表單上。  
  
#### <a name="to-test-the-application"></a>若要測試應用程式  
  
1.  按 F5。  
  
2.  Customers 和 Orders 資料表中的資料是擷取自資料服務，並顯示在表單上。  
  
## <a name="next-steps"></a>後續步驟  
 根據應用程式需求，當您在 Windows 應用程式中儲存相關資料之後，可能會有幾個想要執行的步驟。 例如，您可以對此應用程式進行下列增強：  
  
-   將驗證加入至資料集。 如需資訊，請參閱[逐步解說： 多層式架構資料應用程式中加入驗證](http://msdn.microsoft.com/library/b35d072c-31f0-49ba-a225-69177592c265)。  
  
-   將其他方法加入至服務，以將資料更新回資料庫。  
  
## <a name="see-also"></a>另請參閱  
 [使用多層式架構應用程式中的資料集](../data-tools/work-with-datasets-in-n-tier-applications.md)   
 [階層式更新](../data-tools/hierarchical-update.md)   
 [存取 Visual Studio 中的資料](../data-tools/accessing-data-in-visual-studio.md)

