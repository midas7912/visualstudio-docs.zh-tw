---
title: 加入專案和專案項目範本 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88411bd5fe985c398bd9e4e09ed3bcfb6a7610f0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51780213"
---
# <a name="adding-project-and-project-item-templates"></a>新增專案與專案項目範本
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

當您建立您自己的專案類型時，您必須提供支援加入新的專案和專案項目使用標準[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]整合式開發環境 (IDE) 對話方塊。 下列主題討論不同的技術，讓您新增的專案和專案項目。  
  
## <a name="in-this-section"></a>本節內容  
 [專案內容](../../extensibility/internals/project-context.md)  
 說明專案提供大部分的什麼瓿在環境中的內容資訊。  
  
 [專案優先順序](../../extensibility/internals/project-priority.md)  
 說明專案項目通常是一個專案的成員，才能避免模稜兩可，哪些專案用來開啟項目。  
  
 [其他檔案專案](../../extensibility/internals/miscellaneous-files-project.md)  
 提供專案扮演判斷哪一個編輯器，開啟專案項目時所要使用的兩種可用來在專案和角色中開啟檔案的編輯器類型的資訊。  
  
 [註冊專案和項目範本](../../extensibility/internals/registering-project-and-item-templates.md)  
 說明發生的狀況時[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]建立專案。  
  
 [將項目新增至加入新項目對話方塊](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 說明的程序新增項目**加入新項目** 對話方塊。  
  
 [將目錄新增至新增專案對話方塊](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 提供註冊新的目錄，其中包含 VSPackage 所提供的自訂範本的範例。  
  
 [將目錄新增至加入新項目對話方塊](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 提供的範例註冊一組新的目錄**加入新項目** 對話方塊。  
  
 [用來擴充專案系統的 IDE 定義的命令](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 列出不同類型的擴充專案系統使用的命令項目。  
  
 [通常用來擴充專案的物件 CATID](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 列出可用來擴充的物件 Catid [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)]， [!INCLUDE[csprcs](../../includes/csprcs-md.md)]，和[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]專案系統。  
  
## <a name="related-sections"></a>相關章節  
 [如何︰開啟專案特定的編輯器](../../extensibility/how-to-open-project-specific-editors.md)  
 提供逐步指示，開啟本質繫結至特定的編輯器專案項目。  
  
 [如何︰開啟標準編輯器](../../extensibility/how-to-open-standard-editors.md)  
 提供逐步指示，開啟標準編輯器。  
  
 [專案子類型](../../extensibility/internals/project-subtypes.md)  
 提供專案子類型概念性主題的連結。 專案子類型會延伸現有[!INCLUDE[csprcs](../../includes/csprcs-md.md)]和[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]專案。  
  
 [專案類型](../../extensibility/internals/project-types.md)  
 提供額外的主題提供有關如何設計新的專案類型的資訊連結。

