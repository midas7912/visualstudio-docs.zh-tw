---
title: 如何： 定義方法執行個體 |Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method
- Business Data Connectivity service [SharePoint development in Visual Studio], method
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6e6dd6c0d7676c6b3c2071f0fcb07e8073313633
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118592"
---
# <a name="how-to-define-a-method-instance"></a>如何： 定義方法執行個體
  在模型中，您必須定義至少一個方法執行個體，針對每個方法。  
  
 使用將新增方法執行個體**BDC 方法詳細資料**視窗。 當您新增方法執行個體時，Visual Studio 會加入`<MethodInstance>`模型檔案，在您的專案中的 XML 項目。 如需有關的屬性`<MethodInstance>`項目，請參閱 < [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282)。  
  
### <a name="to-define-a-method-instance"></a>若要定義方法執行個體  
  
1.  在 [ **BDC 方法詳細資料**] 視窗中，展開方法的節點，然後再展開**執行個體**節點。  
  
2.  在 **新增方法執行個體**清單中，選擇**建立搜尋執行個體**。  
  
     新的方法執行個體隨即出現在下方**執行個體**節點。  
  
3.  在功能表列上選擇 [**檢視** > **屬性] 視窗**。  
  
4.  在 **屬性**視窗中，將方法執行個體的屬性。 如需有關每一個屬性的詳細資訊，請參閱 < [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282)。  
  
## <a name="see-also"></a>另請參閱
 [BDC 模型設計工具概觀](../sharepoint/bdc-model-design-tools-overview.md)   
 [如何： 將實體新增至模型](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [如何： 將參數加入至方法](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [如何： 定義參數的型別描述元](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [設計商務資料連接模型](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
