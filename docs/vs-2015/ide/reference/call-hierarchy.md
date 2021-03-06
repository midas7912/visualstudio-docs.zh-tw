---
title: 呼叫階層 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.CallHierarchy
helpviewer_keywords:
- Call Hierarchy
ms.assetid: c55bda01-d7de-4823-8f9a-1bcc37dbb74a
caps.latest.revision: 45
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 86cf4e12f412e6448f4a4b7c38af8268f10d9c56
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49851106"
---
# <a name="call-hierarchy"></a>呼叫階層
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
呼叫階層可藉由顯示與選取的方法、屬性或建構函式的所有呼叫，讓您巡覽您的程式碼。 這可讓您深入了解程式碼的流程，並評估程式碼變更的影響。 您可以檢查數個程式碼階層，以檢視複雜的方法呼叫鏈結及程式碼的其他進入點，讓您探索所有可能的執行路徑。  
  
 與呼叫堆疊 (由偵錯工具顯示) 不同，呼叫階層可以在設計階段使用。  
  
## <a name="using-call-hierarchy"></a>使用呼叫階層  
 若要顯示 [呼叫階層] 視窗，請以滑鼠右鍵按一下方法、屬性或建構函式呼叫的名稱，然後按一下 [檢視呼叫階層]。  
  
 成員名稱會顯示在 [呼叫階層] 視窗的樹狀檢視窗格中。 如果您展開成員節點，則 [呼叫目標 <成員名稱>] 和 [呼叫來源 <成員名稱>] 子節點會隨即出現。 下圖顯示 [呼叫階層] 視窗中的上述節點。  
  
 ![已開啟一個節點的 [呼叫階層]](../../ide/reference/media/onenode.png "OneNode")  
呼叫階層視窗  
  
- 如果您展開 [呼叫目標] 節點，則會顯示呼叫選取之成員的所有成員。  
  
- 如果您展開 [呼叫來源] 節點，則會顯示選取之成員呼叫的所有成員。  
  
  接著，您可以將上述每個子節點成員都展開成 [呼叫目標] 和 [呼叫來源] 節點。 這可讓您巡覽至呼叫端的堆疊中，如同下圖所示。  
  
  ![已開啟多個節點的 [呼叫階層]](../../ide/media/multiplenodes.png "MultipleNodes")  
  呼叫階層視窗  
  
  若是定義為虛擬或抽象的成員，則會出現 [覆寫方法名稱] 節點。 若是介面成員，會出現 [實作方法名稱] 節點。 這些可展開的節點都會在相同階層顯示為 [呼叫目標] 和 [呼叫來源] 節點。  
  
  工具列上的 [搜尋範圍] 方塊包含 [我的方案]、[目前專案] 和 [目前文件] 的選項。  
  
  當您選取 [呼叫階層]  樹狀檢視窗格中的子成員時：  
  
- [呼叫階層] 詳細資料窗格會顯示從父成員中呼叫子成員的所有程式碼行。  
  
- [程式碼定義視窗] 若已開啟，則顯示所選取之成員的程式碼。 在 C# 和 C++ 中可以使用這個視窗。 如需這個視窗的詳細資訊，請參閱[檢視程式碼的結構](../../ide/viewing-the-structure-of-code.md)。  
  
> [!NOTE]
>  呼叫階層找不到方法群組參考，其中包含將方法新增為事件處理常式，或將方法指派給委派的位置。 若要尋找某個方法的所有參考，您可以使用 [尋找所有參考] 命令。  
  
## <a name="shortcut-menu-items"></a>捷徑功能表項目  
 下表描述幾個當您以滑鼠右鍵按一下樹狀檢視窗格中的節點時，可以使用的捷徑功能表選項。  
  
|操作功能表項目|描述|  
|-----------------------|-----------------|  
|**增為新根目錄**|將選取的節點新增至樹狀檢視窗格作為新的根節點。 這可讓您將注意力放在特定樹狀子目錄。|  
|**移除根目錄**|從樹狀檢閱窗格移除所選根節點。 這個選項只能從根節點使用。<br /><br /> 您也可以使用 [移除根目錄] 工具列按鈕來移除選取的根節點。|  
|**移至定義**|在選取的節點上執行 [移至定義] 命令。 如此即可巡覽至成員呼叫的原始定義或變數定義。<br /><br /> 若要執行 [移至定義] 命令，您也可以按兩下選取的節點，或在選取的節點上按 F12。|  
|**尋找所有參考**|在選取的節點上執行 [尋找所有參考] 命令。 如此即可尋找專案中參考類別或成員的所有程式碼行。<br /><br /> 您也可以使用 SHIFT+F12，在選取的節點上執行 [尋找所有參考] 命令。|  
|**複製**|複製選取之節點 (而非其子節點) 的內容。|  
|**重新整理**|摺疊選取的節點，以便於再次展開時顯示目前的資訊。|



