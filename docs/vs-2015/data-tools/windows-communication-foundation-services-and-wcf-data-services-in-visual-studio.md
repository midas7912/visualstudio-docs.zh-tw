---
title: Windows Communication Foundation 服務和 Visual Studio 中的 WCF Data Services |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- services, WCF Data
- WCF services, binding to
- WCF services, asynchronous service methods
- service references [Visual Studio]
- WCF Data Services
- asynchronous calls
- service references [Visual Studio], type sharing
- endpoints [WCF]
- asynchronous service methods
- service references [Visual Studio] endpoints
- WCF services, type sharing
- Windows Communication Foundation, in Visual Studio
- services, WCF
- WCF service, Visual Studio
- data services, WCF
- services, in Visual Studio
- data binding [Visual Studio], WCF
- service endpoints [Visual Studio]
- service references [Visual Studio], asynchronous calls
- services, Windows Communication Foundation
- type sharing in WCF services
- WCF services, endpoints
- service method, called asynchronously[Visual Studio]
ms.assetid: d56f12cb-e139-4fec-b3e4-488383356642
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 55b6ddc1d0e8e3a3caaee89547874e9e38115a17
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49194684"
---
# <a name="windows-communication-foundation-services-and-wcf-data-services-in-visual-studio"></a>Visual Studio 中的 Windows Communication Foundation 服務和 WCF 資料服務
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Visual Studio 提供使用與 Windows Communication Foundation (WCF) 工具和[!INCLUDE[ssAstoria](../includes/ssastoria-md.md)]，Microsoft 技術，用於建立分散式應用程式。 本主題提供簡介服務[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]觀點來看。 如需完整的文件，請參閱[WCF Data Services 4.5](http://msdn.microsoft.com/library/73d2bec3-7c92-4110-b905-11bb0462357a)。  
  
## <a name="what-is-wcf"></a>WCF 是什麼？  
 [!INCLUDE[vsindigo](../includes/vsindigo-md.md)] 是用來建立安全、 可靠、 交易，且可互通的分散式應用程式的統一的架構。 它會取代較舊的處理序間通訊技術，例如 ASMX Web 服務、.NET 遠端處理、 Enterprise Services (DCOM) 及 MSMQ。 WCF 結合了統一的程式設計模型下的所有這些技術的功能。 這可簡化開發分散式應用程式的體驗。  
  
#### <a name="what-are-wcf-data-services"></a>WCF 資料服務有哪些？  
 [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] 是開放式資料 (OData) 通訊協定實作的標準。  WCF Data Services 可讓您將表格式資料公開為一組 REST Api，可讓您傳回資料，例如使用標準 HTTP 動詞命令 GET、 POST、 PUT 或 DELETE。 在伺服器端，WCF Data Services 正由取代[ASP.NET Web API](http://www.asp.net/web-api)用於建立新的 OData 服務。 WCF Data Services 用戶端程式庫仍然是不錯的選擇，以便使用.NET 應用程式從 Visual Studio 中的 OData 服務 (**專案&#124;加入服務參考**)。 如需詳細資訊，請參閱 < [WCF Data Services 4.5](http://go.microsoft.com/fwlink/?LinkID=119952)。  
  
### <a name="wcf-programming-model"></a>WCF 程式設計模型  
 WCF 程式設計模型以兩個實體之間的通訊為基礎： WCF 服務和 WCF 用戶端。 程式設計模型會封裝在<xref:System.ServiceModel>中的命名空間[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]。  
  
#### <a name="wcf-service"></a>WCF 服務  
 WCF 服務根據這個介面會定義服務和用戶端之間的合約。 它以標示<xref:System.ServiceModel.ServiceContractAttribute>屬性，如下列程式碼所示：  
  
 [!code-csharp[WCFWalkthrough#6](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#6)]
 [!code-vb[WCFWalkthrough#6](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#6)]  
  
 [!code-csharp[WCFWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#1)]
 [!code-vb[WCFWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#1)]  
  
 您定義的函式或透過標示與 WCF 服務所公開的方法<xref:System.ServiceModel.OperationContractAttribute>屬性。 此外，您可以在這裡公開序列化的資料來標記的複合類型<xref:System.Runtime.Serialization.DataContractAttribute>屬性。 這可讓用戶端中的資料繫結。  
  
 介面和其方法定義之後，它們都會封裝在實作介面的類別。 單一的 WCF 服務類別可實作多個服務合約。  
  
 透過什麼的耗用量就所謂的 WCF 服務會公開*端點*。 此端點會提供與服務; 進行通訊的唯一方法您無法存取服務透過直接參考，如同使用其他類別。  
  
 端點是由位址、 繫結和合約所組成。 位址會定義服務所在的位置;這可能是 URL、 FTP 位址，或網路或本機路徑。 繫結會定義您與服務通訊的方式。 WCF 繫結會提供具彈性的模型，用於指定的通訊協定，例如 HTTP 或 FTP，安全性機制，例如 Windows 驗證或使用者名稱和密碼，以及其他更多功能。 合約包含由 WCF 服務類別公開的作業。  
  
 可以為單一 WCF 服務公開多個端點。 這可讓不同的用戶端不同的方式，與相同的服務進行通訊。 例如，銀行服務可能會提供一個端點的員工和另一個供外部客戶，每個使用不同的位址、 繫結，及/或合約。  
  
#### <a name="wcf-client"></a>WCF 用戶端  
 WCF 用戶端組成*proxy*可讓應用程式來與 WCF 服務，通訊，而且符合端點的端點定義的服務。 Proxy 會在 app.config 檔案中的用戶端上產生，並包含服務所公開的方法與類型的相關資訊。 對於公開多個端點的服務，用戶端可以選取最符合其需求，例如，透過 HTTP 進行通訊，並使用 Windows 驗證。  
  
 在建立 WCF 用戶端之後，您參考服務在您的程式碼就如同任何其他物件。 例如，若要呼叫`GetData`方法更早版本，您會撰寫程式碼，如下所示：  
  
 [!code-csharp[WCFWalkthrough#3](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/form1.cs#3)]
 [!code-vb[WCFWalkthrough#3](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/form1.vb#3)]  
  
## <a name="wcf-tools-in-visual-studio"></a>Visual Studio 中的 WCF 工具  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 提供工具，可協助您建立 WCF 服務和 WCF 用戶端。 如需示範這些工具的逐步解說，請參閱 <<c0> [ 逐步解說： 在 Windows Forms 中建立簡單的 WCF 服務](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)。  
  
### <a name="creating-and-testing-wcf-services"></a>建立及測試 WCF 服務  
 您可以使用 WCF[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]做為基礎，快速建立您自己的服務範本。 您接著可以使用 WCF 服務自動主機和 WCF 測試用戶端偵錯和測試服務。 這些工具一起提供快速且方便的偵錯和測試循環，並排除在早期階段認可裝載模型的需求。  
  
#### <a name="wcf-templates"></a>WCF 範本  
 WCF[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]範本提供的服務開發的基本類別結構。 會提供數個 WCF 範本**加入新的專案** 對話方塊。 其中包括 WCF 服務庫專案中，WCF 服務網站和 WCF 服務項目範本。  
  
 當您選取範本時，就會將檔案新增的服務合約、 服務實作中，和服務組態。 已加入所有必要的屬性，建立服務的簡單"Hello World"型別，您不需要撰寫任何程式碼。 您當然會想要加入程式碼來提供函式和方法，為您實際的服務，但範本提供基本的基礎。  
  
 若要深入了解 WCF 範本，請參閱[WCF Visual Studio 範本](http://msdn.microsoft.com/library/6a608575-3535-4190-89da-911e24c8374f)。  
  
#### <a name="wcf-service-host"></a>WCF 服務主機  
 當您啟動[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]（藉由按下 F5） 為 WCF 服務專案，WCF 服務主機工具會自動啟動來裝載服務在本機偵錯工具。 WCF 服務主機列舉中的 WCF 服務專案的服務、 載入專案的組態，並具現化每個找到的服務主機。  
  
 藉由使用 WCF 服務主機，您可以測試 WCF 服務，而不需要撰寫額外程式碼或認可特定主機在開發期間。  
  
 若要深入了解 WCF 服務主機，請參閱[WCF 服務主機 (WcfSvcHost.exe)](http://msdn.microsoft.com/library/8643a63d-a357-4c39-bd6c-cdfdf71e370e)。  
  
#### <a name="wcf-test-client"></a>WCF 測試用戶端  
 WCF 測試用戶端工具可讓您輸入測試參數時，提交輸入至 WCF 服務，並檢視服務傳回的回應。 它提供便利的服務測試經驗，當您將其與 WCF 服務主機。 \Common7\IDE 資料夾中，Visual Studio 2015 安裝在磁碟機 c： 就在這裡可以找到這個工具： **C:\Program Files (x86) \Microsoft Visual Studio 14.0\Common7\IDE\\**。  
  
 當您按 F5 以偵錯 WCF 服務專案時，WCF 測試用戶端就會開啟，並顯示組態檔中所定義的服務端點的清單。 您可以測試參數並啟動服務，並重複此程序，以持續測試及驗證您的服務。  
  
 若要深入了解 WCF 測試用戶端，請參閱[WCF 測試用戶端 (WcfTestClient.exe)](http://msdn.microsoft.com/library/d4302855-677f-4640-aa90-c5d785d72fb7)。  
  
### <a name="accessing-wcf-services-in-visual-studio"></a>存取 Visual Studio 中的 WCF 服務  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 可簡化建立 WCF 用戶端，會自動產生 proxy 和您使用新增的服務端點的工作**加入服務參考** 對話方塊。 所有的必要的組態資訊會新增至 app.config 檔案中。 大部分的情況下，您必須執行的所有已具現化服務才能使用它。  
  
 **加入服務參考**對話方塊可讓您輸入的服務位址，或搜尋您的解決方案中所定義的服務。 對話方塊傳回服務與這些服務所提供的作業的清單。 它也可讓您定義會參考程式碼中的服務命名空間。  
  
 **設定服務參考**對話方塊可讓您自訂服務的組態。 您可以變更服務的位址、 指定存取層級、 非同步行為，以及訊息合約型別，以及設定型別重複使用。  
  
## <a name="how-to-select-a-service-endpoint"></a>如何： 選取服務端點  
 某些 Windows Communication Foundation (WCF) 服務會公開透過該用戶端可能會與服務通訊的多個端點。 例如，服務可能會公開一個端點使用 HTTP 繫結和使用者名稱 / 密碼安全性和使用 FTP 和 Windows 驗證的第二個端點。 可能會存取服務的外部防火牆的應用程式所用的第一個端點，而第二個可能會使用內部網路上。  
  
 在此情況下，您可以指定`endpointConfigurationName`做為服務參考的建構函式的參數。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-select-a-service-endpoint"></a>若要選取的服務端點  
  
1.  加入 WCF 服務的參考，以滑鼠右鍵按一下方案總管 中的專案節點，然後選擇**加入服務參考**  
  
2.  在程式碼編輯器中，加入服務參考的建構函式：  
  
    ```vb  
    Dim proxy As New ServiceReference.Service1Client(  
    ```  
  
    ```csharp  
    ServiceReference.Service1Client proxy = new ServiceReference.Service1Client(  
    ```  
  
    > [!NOTE]
    >  取代*ServiceReference*與服務參考和取代命名空間*Service1Client*與服務的名稱。  
  
3.  使用建構函式多載，將會顯示 IntelliSense 清單。 選取`endpointConfigurationName As String`多載。  
  
4.  下列多載中，輸入`=` *ConfigurationName*，其中*ConfigurationName*是您想要使用之端點的名稱。  
  
    > [!NOTE]
    >  如果您不知道可用的端點名稱，您可以在 app.config 檔案中找到它們。  
  
#### <a name="to-find-the-available-endpoints-for-a-wcf-service"></a>若要尋找可用的端點的 WCF 服務  
  
1.  在 **方案總管**，以滑鼠右鍵按一下包含 服務參考的專案的 app.config 檔案，然後按一下**開啟**。 檔案會出現在程式碼編輯器。  
  
2.  搜尋`<Client>`檔案中的標記。  
  
3.  搜尋下方`<Client>`開頭的標記的標記`<Endpoint>`。  
  
     如果服務參考文件提供多個端點，會有兩個或多個`<Endpoint`標記。  
  
4.  內部`<EndPoint>`標記，您會發現`name="` *SomeService* `"`參數 (其中*SomeService*代表端點名稱)。 這是可以傳遞至端點的名稱`endpointConfigurationName As String`服務參考的建構函式的多載。  
  
## <a name="how-to-call-a-service-method-asynchronously"></a>如何： 以非同步方式呼叫服務方法  
 Windows Communication Foundation (WCF) 服務中的大部分方法可能在同步或非同步呼叫。 以非同步方式呼叫方法，可讓您的應用程式繼續運作，而其運作方式的低速連線時，要呼叫的方法。  
  
 根據預設，服務參考加入至專案時它被設定為以同步方式呼叫方法。 您可以變更以非同步方式呼叫方法，藉由變更中的設定行為**設定服務參考** 對話方塊。  
  
> [!NOTE]
>  此選項設定以個別服務為基礎。 如果以非同步方式呼叫服務的一種方法，就必須以非同步方式呼叫所有方法。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-call-a-service-method-asynchronously"></a>以非同步方式呼叫服務方法  
  
1.  在 **方案總管 中**，選取 服務參考。  
  
2.  在 **專案**功能表上，按一下**設定服務參考**。  
  
3.  在 **設定服務參考**對話方塊中，選取**產生非同步作業**核取方塊。  
  
## <a name="how-to-bind-data-returned-by-a-service"></a>如何： 將服務所傳回的資料繫結  
 您可以繫結一樣，您可以將任何其他資料來源繫結至控制項，Windows Communication Foundation (WCF) 服務所傳回的控制項的資料。 當您新增 WCF 服務的參考，如果服務包含傳回資料的複合類型時，它們會自動加入**Zdroje dat**視窗。  
  
#### <a name="to-bind-a-control-to-single-data-field-returned-by-a-wcf-service"></a>將控制項繫結至 WCF 服務所傳回的單一資料欄位  
  
1.  按一下 [ **資料** ] 功能表上的 [ **顯示資料來源**]。 **Zdroje dat**視窗會出現。  
  
2.  在 [ **Zdroje dat** ] 視窗中，展開您的服務參考的節點。 將會顯示服務所傳回的任何複合類型。  
  
3.  展開類型節點。 將顯示該類型的資料欄位。  
  
4.  選取的欄位，然後按一下下拉箭號，以顯示一份可供使用的資料類型的控制項。  
  
5.  按一下您想要繫結至控制項的類型。  
  
6.  將欄位拖曳到表單上。 控制項將會加入至搭配表單<xref:System.Windows.Forms.BindingSource>元件和<xref:System.Windows.Forms.BindingNavigator>元件。  
  
7.  重複步驟 4，6 個用於任何其他欄位，但您想要繫結。  
  
#### <a name="to-bind-a-control-to-composite-type-returned-by-a-wcf-service"></a>將控制項繫結至 WCF 服務所傳回的複合類型  
  
1.  在 **資料**功能表上，選取**顯示資料來源**。 **Zdroje dat**視窗會出現。  
  
2.  在 [ **Zdroje dat** ] 視窗中，展開您的服務參考的節點。 將會顯示服務所傳回的任何複合類型。  
  
3.  選取類型節點，然後按一下下拉箭號，以顯示一份可用的選項。  
  
4.  按一下  **DataGridView**方格中顯示資料或**詳細資料**個別控制項中顯示資料。  
  
5.  將節點拖曳至表單。 會將控制項加入至表單，並搭配<xref:System.Windows.Forms.BindingSource>元件和<xref:System.Windows.Forms.BindingNavigator>元件。  
  
## <a name="how-to-configure-a-service-to-reuse-existing-types"></a>如何： 設定服務，以重複使用現有的類型  
 當服務參考加入至專案時，在服務中定義的任何型別會產生在本機專案中。 在許多情況下，這會建立重複的型別時服務會使用常見[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]類型共用的文件庫中已定義。  
  
 若要避免這個問題，預設為共用參考的組件中的型別。 如果您想要停用共用的一或多個組件的型別，則可以在**設定服務參考** 對話方塊。  
  
#### <a name="to-disable-type-sharing-in-a-single-assembly"></a>若要停用的單一組件中的類型共用  
  
1.  在 **方案總管 中**，選取 服務參考。  
  
2.  在 **專案**功能表上，按一下**設定服務參考**。  
  
3.  在 **設定服務參考**對話方塊中，選取**重複使用指定的參考組件中的型別**。  
  
4.  選取您要在其中啟用類型共用的每個組件的核取方塊。 若要停用共用組件的型別，保持核取方塊。  
  
#### <a name="to-disable-type-sharing-in-all-assemblies"></a>若要停用所有組件中的類型共用  
  
1.  在 **方案總管 中**，選取 服務參考。  
  
2.  在 **專案**功能表上，按一下**設定服務參考**。  
  
3.  在 **設定服務參考**對話方塊中，清除**重複使用參考組件中的型別**核取方塊。  
  
## <a name="related-topics"></a>相關主題  
  
|標題|描述|  
|-----------|-----------------|  
|[逐步解說：在 Windows Forms 中建立簡單的 WCF 服務](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)|提供建立和使用中的 WCF 服務的逐步示範[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。|  
|[逐步解說︰使用 WPF 和 Entity Framework 建立 WCF 資料服務](../data-tools/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework.md)|提供建立和使用方式的逐步示範[!INCLUDE[ssAstoria](../includes/ssastoria-md.md)]在[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。|  
|[使用 WCF 開發工具](http://msdn.microsoft.com/library/054adb87-c244-4d5a-83d1-0b2b44bd454b)|討論如何建立和測試中的 WCF 服務[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。|  
|[如何： 加入、 更新或移除服務參考](http://msdn.microsoft.com/library/cacc14bd-4455-4a44-be78-d2ac16113dd9)|描述如何新增、 更新或移除專案中的 WCF 服務。|  
|[如何：新增、更新或移除 WCF 資料服務參考](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)|討論如何參考，並使用[!INCLUDE[ssAstoria](../includes/ssastoria-md.md)]在[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。|  
|[服務參考的疑難排解](../data-tools/troubleshooting-service-references.md)|提供服務的參考，以及如何避免它們可能會發生的一些常見錯誤。|  
|[偵錯 WCF 服務](../debugger/debugging-wcf-services.md)|描述常見的偵錯問題和偵錯 WCF 服務時，可能會遇到的技術。|  
|[Windows Communication Foundation 的驗證服務概觀](http://msdn.microsoft.com/library/6e121a28-89e8-4974-88a8-70aaa6a7d52b)|描述如何使用 WCF 來提供網站的角色服務。|  
|[逐步解說：建立多層式架構 (N-Tier) 資料應用程式](../data-tools/walkthrough-creating-an-n-tier-data-application.md)|提供用於建立具類型資料集以及將 TableAdapter 和資料集程式碼分成多個專案的逐步指示。|  
|[設定服務參考對話方塊](../data-tools/configure-service-reference-dialog-box.md)|描述使用者介面項目**設定服務參考** 對話方塊。|  
  
## <a name="reference"></a>參考資料  
 <xref:System.ServiceModel>  
  
 <xref:System.Data.Services>  
  
## <a name="see-also"></a>另請參閱  
 [適用於 .NET 的 Visual Studio Data Tools](../data-tools/visual-studio-data-tools-for-dotnet.md)

