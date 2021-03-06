---
title: 如何： 重新啟用 VSTO 增益集已停用
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Warning.DisabledAddIn
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disabled add-ins
- add-ins [Office development in Visual Studio], disabled
- add-ins [Office development in Visual Studio], enabling
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c81e44b548f4d1139810780731741a489e624047
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2018
ms.locfileid: "35671493"
---
# <a name="how-to-re-enable-a-vsto-add-in-that-has-been-disabled"></a>如何： 重新啟用 VSTO 增益集已停用
  Microsoft Office 應用程式可以停用無法如預期般運作的 VSTO 增益集。 如果應用程式在您嘗試進行偵錯時並未載入 VSTO 增益集，表示應用程式可能已經強制停用或非強制停用 VSTO 增益集。  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="hard-disabled-vsto-add-ins"></a>強制停用 VSTO 增益集  
 當 VSTO 增益集導致應用程式意外關閉時，可以發生強制停用。 在開發電腦上，如果您在 VSTO 增益集中的 <xref:Microsoft.Office.Tools.AddIn.Startup> 事件處理常式正在執行時停止偵錯工具，也可能發生這種情形。  
  
### <a name="to-re-enable-a-vsto-add-in"></a>若要重新啟用 VSTO 增益集  
  
1.  在應用程式中，按一下 [檔案]  索引標籤。  
  
2.  按一下 [ *ApplicationName* **選項**] 按鈕。  
  
3.  在分類窗格中，按一下 [增益集] 。  
  
4.  在詳細資料窗格中，確認 VSTO 增益集出現在 [停用的應用程式增益集]  清單中。  
  
     [名稱]  資料行指定組件的名稱，而 [位置]  資料行會指定應用程式資訊清單的完整路徑。  
  
5.  按一下 [管理]  方塊中的 [停用的項目] ，然後按一下 [移至] 。  
  
6.  選取 VSTO 增益集，然後按一下 [啟用] 。  
  
7.  按一下 [ **關閉**]。  
  
## <a name="soft-disabled-vsto-add-ins"></a>強制停用 VSTO 增益集  
 當 VSTO 增益集產生的錯誤不會導致應用程式意外關閉時，可能會發生非強制停用。 例如，如果在 <xref:Microsoft.Office.Tools.AddIn.Startup> 事件處理常式正在執行時擲回未處理的例外狀況，應用程式可能會非強制停用 VSTO 增益集。  
  
> [!NOTE]  
>  當您重新啟用非強制停用的 VSTO 增益集時，應用程式會立即嘗試載入 VSTO 增益集。 如果未修正當初造成應用程式非強制停用 VSTO 增益集的問題，則應用程式會再次非強制停用 VSTO 增益集。  
  
### <a name="to-re-enable-a-vsto-add-in"></a>若要重新啟用 VSTO 增益集  
  
1.  在應用程式中，按一下 [檔案]  索引標籤。  
  
2.  按一下 [ *ApplicationName* **選項**] 按鈕。  
  
3.  在分類窗格中，按一下 [增益集] 。  
  
4.  在詳細資料窗格中，確認 VSTO 增益集出現在 [非使用中應用程式增益集]  清單中。  
  
     [名稱]  資料行指定組件的名稱，而 [位置]  資料行會指定應用程式資訊清單的完整路徑。  
  
5.  按一下 [管理]  方塊中的 [COM 增益集] ，然後按一下 [移至] 。  
  
6.  在 [COM 增益集]  對話方塊中，選取已停用 VSTO 增益集旁邊的核取方塊。  
  
7.  按一下 [確定 **Deploying Office Solutions**]。  
  
## <a name="see-also"></a>另請參閱  
 [建置 Office 方案](../vsto/building-office-solutions.md)   
 [偵錯 Office 專案](../vsto/debugging-office-projects.md)   
 [程式 VSTO 增益集](../vsto/programming-vsto-add-ins.md)  
  
  