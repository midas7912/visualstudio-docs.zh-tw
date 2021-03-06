---
title: 如何： 使用平行監看式視窗 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parallelwatch
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel watch window
ms.assetid: 28004d9b-420c-48f7-b80e-ab1519802558
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 43783ad2b7d0f08aace55ff3b974d64301a38db2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51753132"
---
# <a name="how-to-use-the-parallel-watch-window"></a>如何：使用平行監看式視窗
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在 [平行監看式] 視窗中，您可以同時在多個執行緒上顯示某個運算式保存的值。 每一列代表應用程式中執行的一個執行緒，不過一個執行緒可能在多列上表示。 更精確的說，每一列代表一個函式呼叫，該函式呼叫的簽章與目前堆疊框架上的函式相符。 您可以將資料行中的項目排序、重新排列、移除和設為群組。 您可以將執行緒加上旗標、取消旗標、凍結 (暫止) 和解除凍結 (繼續)。 下列資料行所示**平行監看式**視窗：  
  
- 旗標資料行，您可以在該資料行中標示想要特別注意的執行緒。  
  
- 框架資料行，其中的箭號表示選取的框架。  
  
- 可以顯示電腦、處理序、Tile、工作和執行緒的可設定資料行。  
  
  > [!TIP]
  >  您必須開啟**平行工作** 視窗顯示中的工作資訊**平行監看式**視窗。  
  
- **\<新增監看式 >** 資料行中，您可以在其中輸入要監看的運算式。  
  
  [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-display-the-parallel-watch-window"></a>若要顯示 [平行監看式] 視窗  
  
1.  在程式碼中設定中斷點。  
  
2.  在功能表列上，選擇 [偵錯]、[開始偵錯]。 等候應用程式到達中斷點。  
  
3.  在功能表列上選擇 **偵錯**， **Windows**，**平行監看式**，然後選擇 監看式視窗。 您最多可以開啟四個視窗。  
  
### <a name="to-add-a-watch-expression"></a>若要加入監看運算式  
  
-   選取 [ **\<新增監看式 >** ]，然後指定監看式運算式。  
  
### <a name="to-flag-or-unflag-a-thread"></a>若要將執行緒加上旗標或取消旗標  
  
-   選取的旗標資料行，資料列中，或開啟執行緒的捷徑功能表並選擇 **旗標**或是**取消旗標**。  
  
### <a name="to-display-only-flagged-threads"></a>若只要顯示加上旗標的執行緒  
  
-   選擇 [僅顯示已標幟] 按鈕的左上角**平行監看式**視窗。  
  
### <a name="to-switch-frames"></a>若要切換框架  
  
-   按兩下框架資料行  (鍵盤：選取資料列並按 Enter)。  
  
### <a name="to-sort-a-column"></a>若要排序資料行  
  
-   選取資料行標題。  
  
### <a name="to-group-threads"></a>若要群組執行緒  
  
-   開啟 平行監看式 視窗的捷徑功能表，選擇  **Group By**，然後選擇適當的子功能表項目。  
  
### <a name="to-freeze-or-thaw-threads"></a>若要凍結或解除凍結執行緒  
  
-   開啟資料列的捷徑功能表，然後選擇**凍結**或是**解除凍結**。  
  
### <a name="to-export-the-data-in-the-parallel-watch-window"></a>若要匯出 [平行監看式] 視窗中的資料  
  
-   選擇**在 Excel 中開啟**按鈕，然後選擇**在 Excel 中開啟**或是**匯出至 CSV**。  
  
### <a name="to-filter-by-a-boolean-expression"></a>若要依布林運算式篩選  
  
-   輸入中的布林運算式**依布林運算式篩選** 方塊中。 偵錯工具會針對每個執行緒內容評估運算式。 只有值為 `true` 的列才會顯示。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯多執行緒應用程式](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [如何： 使用 GPU 執行緒視窗](../debugger/how-to-use-the-gpu-threads-window.md)   
 [逐步解說：偵錯 C++ AMP 應用程式](http://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)



