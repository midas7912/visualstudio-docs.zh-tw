---
title: 如何： 新增和移除功能和項目加入封裝時，使用 [封裝總管] |Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.RAD.PackagingExplorer
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7875401dee07961d63de6c7b71a97e647c21a0b7
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755608"
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>如何： 新增和移除功能和項目加入封裝時，使用 [封裝總管]
  若要設定要部署的 SharePoint 項目和功能的套件，您可以使用 [封裝總管] 中。 您的.wsp 檔內，您可以調整的 SharePoint 專案項目和功能。  
  
 或者，您可以使用 封裝設計工具來檢視和重新排列的功能變更的啟動順序。 如需詳細資訊，請參閱 <<c0> [ 如何： 新增與移除功能和封裝的項目使用 Package Designer](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)。  
  
## <a name="open-the-packaging-explorer"></a>開啟 [封裝總管]  
 您可以使用下列程序以開啟 [封裝總管] 中，如果 Visual Studio 方案中有至少一個 SharePoint 專案中。 或者，[封裝總管] 會自動開啟功能或封裝的設計工具的檢視時。 在您關閉所有的功能和封裝設計工具之後，[封裝總管] 中也會關閉。  
  
#### <a name="to-open-the-packaging-explorer"></a>若要開啟 封裝總管  
  
1.  在功能表列上選擇 **檢視** > **其他 Windows** > **封裝總管**。  
  
     **封裝總管**會出現在**工具箱**。  
  
## <a name="adding-a-feature-to-a-package"></a>將功能加入封裝  
 您可以加入封裝時加入新的和現有的功能，使用 [封裝總管] 中。  
  
#### <a name="to-add-a-sharepoint-feature"></a>若要新增的 SharePoint 功能
  
1.  開啟**封裝總管**，開啟專案的捷徑功能表，然後選擇**加入功能**。  
  
#### <a name="to-move-an-existing-sharepoint-feature"></a>若要移動現有的 SharePoint 功能  
  
1.  開啟**封裝總管**，然後執行下列步驟的其中一個：  
  
    -   拖曳**功能**從另一個專案的一個專案。  
  
    -   開啟功能的捷徑功能表，選擇 **剪下**，開啟您想要移動功能，再選擇的專案的捷徑功能表**貼上**。  
  
    > [!NOTE]  
    >  如果您的方案中有一個以上的 SharePoint 專案，請使用此程序。  
  
## <a name="validate-a-feature-or-package"></a>驗證功能或封裝  
 您可以識別潛在的問題中的 SharePoint 功能和封裝驗證的檔案。 警告和錯誤會顯示在輸出視窗 和 錯誤清單 視窗中。  
  
#### <a name="to-validate-a-sharepoint-feature-or-package"></a>若要驗證的 SharePoint 功能或封裝
  
1.  開啟**封裝總管**。  
  
2.  對某個功能或封裝中，開啟捷徑功能表，然後選擇**驗證**。  
  
## <a name="see-also"></a>另請參閱
 [封裝和部署 SharePoint 方案](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
