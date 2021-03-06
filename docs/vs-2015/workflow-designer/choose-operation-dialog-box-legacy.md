---
title: 選擇作業對話方塊 （舊版） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Design.OperationPickerDialog.UI
ms.assetid: bc3ec902-7797-494e-af48-e70c97eb6779
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 75b553bd79936db7b6d8aa2f8fe361650d4ef03e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189619"
---
# <a name="choose-operation-dialog-box-legacy"></a>選擇作業對話方塊 (舊版)
本主題描述如何使用**選擇作業**對話方塊中，在舊版[!INCLUDE[wfd1](../includes/wfd1-md.md)]。 當您需要以 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 或 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 為目標時，請使用舊版 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]。  
  
 **選擇作業** 對話方塊來選取要與產生關聯的作業<xref:System.Workflow.Activities.ReceiveActivity>活動或<xref:System.Workflow.Activities.SendActivity>活動。 如需使用此對話方塊中，使用這些活動的詳細資訊，請參閱[如何： 實作 WCF 合約作業 （舊版）](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)並[How to： 叫用 WCF 合約作業 （舊版）](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)。  
  
 下表描述的使用者介面 (UI) 項目**選擇作業** 對話方塊。  
  
|UI 項目|描述|  
|----------------|-----------------|  
|**新增合約**|為您建立新合約。 您可以在這個合約上定義新作業。 (這個介面僅能與 <xref:System.Workflow.Activities.ReceiveActivity> 搭配使用)|  
|**新增作業**|將新作業加入至您在中建立的新合約**選擇作業** 對話方塊。 **注意︰** 您可以加入新的作業只透過建立的合約**選擇作業** 對話方塊。 <br /><br /> (這個介面僅能與 <xref:System.Workflow.Activities.ReceiveActivity> 搭配使用)|  
|**匯入...**|匯入先前定義的合約，並允許您從該合約選取作業。|  
|**作業名稱**|目前選取之作業的名稱。 此文字方塊是可供編輯您已建立作業時，才**選擇作業** 對話方塊。|  
|**參數**|索引標籤，包含目前所選取作業的參數定義。 **注意︰** 只有當您已建立作業時，才可以變更參數定義**選擇作業** 對話方塊。|  
|**屬性**|索引標籤，包含用於用戶端和服務之間所傳送之訊息的 <xref:System.Net.Security.ProtectionLevel> 設定。 **注意︰** 此索引標籤在您已建立作業時，才會啟用**選擇作業** 對話方塊。|  
|**權限**|索引標籤，包含允許呼叫該作業之使用者的 <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionName%2A> 和 <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionRole%2A> 屬性。 比方說，如果只允許系統管理員群組中的使用者呼叫該作業，然後您會撰寫 「 系統管理員 」**角色**文字方塊。<br /><br /> 此索引標籤都可透過建立這兩種作業**ChooseOperation**對話方塊，並透過匯入的作業**匯入** 按鈕。|  
  
> [!NOTE]
>  **選擇作業**對話方塊會顯示唯一的合約或作業所使用的其他<xref:System.Workflow.Activities.SendActivity>工作流程中的活動。 同樣地，**選擇作業** 對話方塊<xref:System.Workflow.Activities.ReceiveActivity>活動顯示唯一的合約或作業所使用的其他**ReceiveActivity**工作流程中的活動。  
  
## <a name="see-also"></a>另請參閱  
 [如何： 實作 WCF 合約作業 （舊版）](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)   
 [如何： 叫用 WCF 合約作業 （舊版）](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)   
 [舊版 Windows Workflow Foundation UI 設計工具的說明](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)