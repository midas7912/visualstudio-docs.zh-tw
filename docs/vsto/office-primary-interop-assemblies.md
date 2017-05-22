---
title: "Office 主要 Interop 組件"
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
  - "主要 Interop 組件"
  - "組件 [Visual Studio 中的 Office 程式開發]，主要 Interop 組件"
  - "Office 主要 Interop 組件"
ms.assetid: aa29d12c-185f-4558-a7cd-3d85f924203d
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# Office 主要 Interop 組件
  若要從 Office 專案使用 Microsoft Office 應用程式的功能，您必須使用應用程式的主要 Interop 組件 \(PIA\)。 PIA 可讓 Managed 程式碼與 Microsoft Office 應用程式的 COM 物件模型互動。  
  
 當您建立新的 Office 專案時，Visual Studio 會加入建置專案所需的 PIA 參考。 在某些情況下，您可能需要加入其他 PIA 的參考 \(例如，如果您要在 Microsoft Office Excel 專案中使用 Microsoft Office Word 的功能\)。  
  
 本主題將說明在 Office 專案中使用 Microsoft Office PIA 的以下方面：  
  
-   [將建置和執行專案的主要 Interop 組件分開](#separateassemblies)  
  
-   [在單一專案中使用多個 Microsoft Office 應用程式的功能](#usingfeatures)  
  
-   [Microsoft Office 應用程式之主要 Interop 組件的完整清單](#pialist)  
  
 如需主要 Interop 組件的詳細資訊，請參閱[主要 Interop 組件](http://msdn.microsoft.com/zh-tw/b977a8be-59a0-40a0-a806-b11ffba5c080)。  
  
##  <a name="separateassemblies"></a> 將建置和執行專案的主要 Interop 組件分開  
 Visual Studio 在開發電腦上使用不同的 PIA 集合。 這些不同的組件集合位於下列位置：  
  
-   Program Files 目錄中的資料夾。  
  
     當您撰寫程式碼及建置專案時會使用這些組件複本。 Visual Studio 會自動安裝這些組件。  
  
-   全域組件快取。  
  
     進行某些開發工作期間會使用這些組件複本，例如執行或偵錯專案時。 Visual Studio 不會安裝及註冊這些組件，您必須自行完成此作業。  
  
### Program Files 目錄中的主要 Interop 組件  
 當您安裝 Visual Studio 時，會自動將 PIA 安裝到檔案系統的某個位置，此位置位於全域組件快取之外。 當您建立新專案時，Visual Studio 會自動將這些 PIA 複本的參考加入至專案。 當您在開發及建置專案時，Visual Studio 會使用這些 PIA 複本 \(而不是全域組件快取中的組件\) 來解析類型參考。  
  
 如果在全域組件快取中註冊了不同版本的 PIA，這些 PIA 複本可協助 Visual Studio 避免發生一些開發問題。  
  
 Visual Studio 會將這些 PIA 複本安裝到開發電腦的下列位置：  
  
-   %ProgramFiles%\\Microsoft Visual Studio 12.0\\Visual Studio Tools for Office\\PIA\\Office14  
  
     \(或 64 位元件業系統的 %ProgramFiles\(x86\)%\\Microsoft Visual Studio 12.0\\Visual Studio Tools for Office\\PIA\\Office14\)  
  
-   %ProgramFiles%\\Microsoft Visual Studio 12.0\\Visual Studio Tools for Office\\PIA\\Office15  
  
     \(或 64 位元件業系統的 %ProgramFiles\(x86\)%\\Microsoft Visual Studio 12.0\\Visual Studio Tools for Office\\PIA\\Office15\)  
  
### 全域組件快取中的主要 Interop 組件  
 為了執行特定開發工作，您必須在開發電腦的全域組件快取中安裝並註冊 PIA。 當您在開發電腦上安裝 Office 時，通常會自動安裝 PIA。 如需詳細資訊，請參閱[設定電腦以開發 Office 方案](../vsto/configuring-a-computer-to-develop-office-solutions.md)。  
  
 使用者電腦不需要 Office PIA 即可執行 Office 方案。 如需詳細資訊，請參閱[設計和建立 Office 方案](../vsto/designing-and-creating-office-solutions.md)。  
  
##  <a name="usingfeatures"></a> 在單一專案中使用多個 Microsoft Office 應用程式的功能  
 Visual Studio 中的每一個 Office 專案範本設計成只能搭配一個 Microsoft Office 應用程式使用。 若要使用多個 Microsoft Office 應用程式中的功能，或是要使用未在 Visual Studio 中擁有專案之應用程式或元件中的功能，您必須加入所需 PIA 的參考。  
  
 在大多數情況下，您應該加入由 Visual Studio 安裝在 %ProgramFiles%\\Microsoft Visual Studio 12.0\\Visual Studio Tools for Office\\PIA\\ 目錄下的 PIA 參考。 這些版本的組件會顯示在 \[參考管理員\] 對話方塊的 \[架構\] 索引標籤上。 如需詳細資訊，請參閱[如何：透過主要 Interop 組件以 Office 應用程式為目標](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)。  
  
 如果您已在全域組件快取中安裝及註冊 PIA，這些版本的組件會顯示在 \[參考管理員\] 對話方塊的 \[COM\] 索引標籤上。 您應該避免加入這些版本的組件參考，因為使用這些版本的組件參考可能會發生一些開發問題。 例如，如果您在全域組件快取中註冊了不同版本的 PIA，您的專案將會自動建置為最後註冊的組件版本 \(即使在 \[參考管理員\] 對話方塊的 \[COM\] 索引標籤上指定了不同版本的組件亦然\)。  
  
> [!NOTE]  
>  當您加入參考某些組件的單一組件時，系統會自動將這些組件加入至專案。 例如，當您加入 Word、Excel、Outlook、Microsoft Forms 或 Graph 組件的參考時，系統會自動加入 Office.dll 和 Microsoft.Vbe.Interop.dll 組件的參考。  
  
##  <a name="pialist"></a> Microsoft Office 應用程式的主要 Interop 組件  
 下表列出 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 和 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] 適用的主要 Interop 組件。  
  
|Office 應用程式或元件|主要 Interop 組件名稱|  
|--------------------|---------------------|  
|Microsoft Access 14.0 物件程式庫<br /><br /> Microsoft Access 15.0 物件程式庫|Microsoft.Office.Interop.Access.dll|  
|Microsoft Office 14.0 Access 資料庫引擎物件程式庫<br /><br /> Microsoft Office 15.0 Access 資料庫引擎物件程式庫|Microsoft.Office.Interop.Access.Dao.dll|  
|Microsoft Excel 14.0 物件程式庫<br /><br /> Microsoft Excel 15.0 物件程式庫|Microsoft.Office.Interop.Excel.dll|  
|Microsoft Graph 14.0 物件程式庫 \(用於 PowerPoint、Access 和 Word 的圖形\)<br /><br /> Microsoft Graph 15.0 物件程式庫|Microsoft.Office.Interop.Graph.dll|  
|Microsoft InfoPath 2.0 類型程式庫 \(只適用於 InfoPath 2007\)|Microsoft.Office.Interop.InfoPath.dll|  
|Microsoft InfoPath XML Interop 組件 \(只適用於 InfoPath 2007\)|Microsoft.Office.Interop.InfoPath.Xml.dll|  
|Microsoft Office 14.0 物件程式庫 \(Office 共用功能\)<br /><br /> Microsoft Office 15.0 物件程式庫 \(Office 共用功能\)|office.dll|  
|Microsoft Office Outlook 檢視控制 \(可在網頁和應用程式中用來存取 \[收件匣\]\)|Microsoft.Office.Interop.OutlookViewCtl.dll|  
|Microsoft Outlook 14.0 物件程式庫<br /><br /> Microsoft Outlook 15.0 物件程式庫|Microsoft.Office.Interop.Outlook.dll|  
|Microsoft PowerPoint 14.0 物件程式庫<br /><br /> Microsoft PowerPoint 15.0 物件程式庫|Microsoft.Office.Interop.PowerPoint.dll|  
|Microsoft Project 14.0 物件程式庫<br /><br /> Microsoft Project 15.0 物件程式庫|Microsoft.Office.Interop.MSProject.dll|  
|Microsoft Publisher 14.0 物件程式庫<br /><br /> Microsoft Publisher 15.0 物件程式庫|Microsoft.Office.Interop.Publisher.dll|  
|Microsoft SharePoint Designer 14.0 Web 物件參考庫|Microsoft.Office.Interop.SharePointDesigner.dll|  
|Microsoft SharePoint Designer 14.0 Page 物件參考庫|Microsoft.Office.Interop.SharePointDesignerPage.dll|  
|Microsoft Smart Tags 2.0 類型程式庫 **Note:**  智慧標籤在 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] 和 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)] 中已被取代。|Microsoft.Office.Interop.SmartTag.dll|  
|Microsoft Visio 14.0 類型程式庫<br /><br /> Microsoft Visio 15.0 類型程式庫|Microsoft.Office.Interop.Visio.dll|  
|Microsoft Visio 14.0 Save As Web 類型程式庫<br /><br /> Microsoft Visio 15.0 Save As Web 類型程式庫|Microsoft.Office.Interop.Visio.SaveAsWeb.dll|  
|Microsoft Visio 14.0 Drawing Control 類型程式庫<br /><br /> Microsoft Visio 15.0 Drawing Control 類型程式庫|Microsoft.Office.Interop.VisOcx.dll|  
|Microsoft Word 14.0 物件程式庫<br /><br /> Microsoft Word 15.0 物件程式庫|Microsoft.Office.Interop.Word.dll|  
|Microsoft Visual Basic for Applications Extensibility 5.3|Microsoft.Vbe.Interop.dll|  
  
### 繫結重新導向組件  
 當您在全域組件快取中安裝及註冊 Office PIA 時 \(使用 Office 或是安裝 PIA 的可轉散發套件\)，只會在全域組件快取中安裝繫結重新導向組件。 這些組件可確保執行階段載入的是正確版本的主要 Interop 組件。 例如，當參考 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] 組件的方案會在具有相同主要 Interop 組件之 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 版本的電腦上執行時，繫結重新導向組件會指示 [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] 執行階段載入 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 版本的主要 Interop 組件。 如需詳細資訊，請參閱[如何：啟用和停用自動繫結重新導向](http://msdn.microsoft.com/library/5fca42f3-bdce-4b81-a704-61e42c89d3ba)。  
  
## 請參閱  
 [如何：透過主要 Interop 組件以 Office 應用程式為目標](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Excel 物件模型概觀](../vsto/excel-object-model-overview.md)   
 [InfoPath 方案](../vsto/infopath-solutions.md)   
 [Outlook 物件模型概觀](../vsto/outlook-object-model-overview.md)   
 [PowerPoint 方案](../vsto/powerpoint-solutions.md)   
 [專案方案](../vsto/project-solutions.md)   
 [Visio 物件模型概觀](../vsto/visio-object-model-overview.md)   
 [Word 物件模型概觀](../vsto/word-object-model-overview.md)   
 [一般參考 &#40;Visual Studio 中的 Office 程式開發&#41;](../vsto/general-reference-office-development-in-visual-studio.md)  
  
  