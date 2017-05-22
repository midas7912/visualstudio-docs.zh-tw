---
title: "Office 方案中的應用程式和部署資訊清單"
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
  - "資訊清單 [Visual Studio 中的 Office 程式開發]"
  - "部署資訊清單 [Visual Studio 中的 Office 程式開發]"
  - "應用程式資訊清單 [Visual Studio 中的 Office 程式開發]"
  - "組件 [Visual Studio 中的 Office 程式開發]，更新"
ms.assetid: 4e9abc7c-ef9f-4cb2-a7a9-c95c5f4a1fb7
caps.latest.revision: 45
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 44
---
# Office 方案中的應用程式和部署資訊清單
  應用程式資訊清單是提供資訊讓 Office 方案用來尋找及更新其組件的 XML 檔案。 應用程式資訊清單可以搭配部署資訊清單使用，部署資訊清單是伺服器上儲存的 XML 檔案，可提供尋找最新版應用程式資訊清單和組件所需的資訊。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## Office 方案的資訊清單結構  
 對於在 Visual Studio 中使用 Office 開發工具所建立的 Microsoft Office 方案，所有資訊清單都是根據標準的 ClickOnce 結構描述。 當您部署 Office 方案時，文件層級和 VSTO 增益集專案的應用程式資訊清單都位於 ClickOnce 快取。 部署資訊清單不會複製到用戶端電腦。  
  
 如需 Office 專案的應用程式和部署資訊清單內容的相關資訊，請參閱 [Office 方案的應用程式資訊清單](../vsto/application-manifests-for-office-solutions.md)和 [Office 方案的部署資訊清單](../vsto/deployment-manifests-for-office-solutions.md)。  
  
## 建立應用程式和部署資訊清單  
 應用程式資訊清單會在建置流程中自動建立。 每次建置文件層級專案時，部署資訊清單的位置會內嵌在文件中做為自訂文件屬性。 對於 VSTO 增益集，部署資訊清單的位置儲存在登錄中。  
  
 如需 \[發行精靈\] 的詳細資訊，請參閱[使用 ClickOnce 部署 Office 方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)。  
  
 如需資訊清單如何搭配 Office 方案運作的詳細資訊，請參閱[部署 Office 方案](../vsto/deploying-an-office-solution.md)。  
  
## 請參閱  
 [文件層級自訂的架構](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO 增益集的架構](../vsto/architecture-of-vsto-add-ins.md)   
 [設計和建立 Office 方案](../vsto/designing-and-creating-office-solutions.md)   
 [Office 方案的應用程式資訊清單](../vsto/application-manifests-for-office-solutions.md)   
 [Office 方案的部署資訊清單](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 應用程式資訊清單](../deployment/clickonce-application-manifest.md)   
 [ClickOnce 部署資訊清單](../deployment/clickonce-deployment-manifest.md)  
  
  