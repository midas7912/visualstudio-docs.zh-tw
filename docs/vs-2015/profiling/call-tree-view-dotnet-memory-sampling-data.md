---
title: 呼叫樹狀圖檢視 - .NET 記憶體取樣資料 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Tree view
ms.assetid: fbb6cb60-420b-4ca9-8306-2494f7d321fe
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6667d0e0ad76210434f40eaf89e4790430ffb0e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51758616"
---
# <a name="call-tree-view---net-memory-sampling-data"></a>呼叫樹狀圖檢視 - .NET 記憶體取樣資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[呼叫樹狀圖] 檢視顯示在分析的應用程式中周遊的函式執行路徑。 樹狀圖的根是應用程式或元件的進入點。 每個函式節點都會列出它所呼叫的所有函式，以及這些函式呼叫的 .NET 記憶體配置資料。  
  
 [呼叫樹狀圖] 檢視中的值，適用於呼叫樹狀圖中父函式所呼叫的函式執行個體。 百分比值的計算方式是比較函式執行個體值與分析執行中的總配置數目或大小。  
  
## <a name="highlighting-the-execution-hot-path"></a>反白顯示執行最忙碌路徑  
 [呼叫樹狀結構] 檢視可以展開並反白顯示已建立最大或大部分記憶體物件之處理序或函式的執行路徑。 若要顯示最常使用的路徑，以滑鼠右鍵按一下處理序或函式，然後按一下 [展開最忙碌路徑]。  
  
## <a name="setting-the-call-tree-root-node"></a>設定呼叫樹狀圖根節點  
 分析執行中的每個處理序都會顯示為根節點。 若要將 [呼叫樹狀圖] 檢視的開始節點設定為不同的節點，請以滑鼠右鍵按一下您想要設定為開始節點的節點，然後選取 [設定根目錄]。  
  
 設定根節點時，除了所選取節點的樹狀子目錄以外，請從檢視中排除所有其他的項目。 您可以將根節點重設回所檢視的節點，並以滑鼠右鍵按一下 [呼叫樹狀圖檢視] 視窗，然後選取 [重設根目錄]。  
  
|資料行|描述|  
|------------|-----------------|  
|**處理序 ID**|分析執行的處理序 ID (PID)。|  
|**處理序名稱**|處理序的名稱。|  
|**模組名稱**|包含該函式的模組名稱。|  
|**模組路徑**|包含該函式的模組路徑。|  
|**原始程式檔**|含有這個函式定義的原始程式檔。|  
|**函式名稱**|函式的完整格式名稱。|  
|**函式行號**|原始程式檔中這個函式的開頭行號。|  
|**函式位址**|函式的位址。|  
|**層級**|函式在呼叫樹狀圖中的深度。|  
|**內含配置**|此函式執行個體所配置的物件數目，而函式執行個體是由呼叫樹狀結構中的父函式所呼叫。 此數目包含子函式所進行的配置。|  
|**內含配置 %**|在分析執行中建立的所有物件中，屬於此函式之內含配置的百分比。|  
|**專有配置**|此函式執行個體所配置的物件數目，而函式執行個體是由呼叫樹狀結構中的父函式所呼叫。 此數目未包含子函式所進行的配置。|  
|**專有配置 %**|在分析執行建立的所有物件中，屬於呼叫樹狀結構中父函式所呼叫之函式執行個體的專屬配置百分比。|  
|**內含位元組**|此函式執行個體所配置記憶體的位元組數目，而函式執行個體是由呼叫樹狀圖中的父函式所呼叫。 此數目包含子函式所進行的配置。|  
|**內含位元組 %**|在分析執行中配置的所有記憶體位元組中，屬於此函式之內含配置的百分比。|  
|**專有位元組**|此函式執行個體所配置記憶體的位元組數目，而函式執行個體是由呼叫樹狀圖中的父函式所呼叫。 此數目未包含子函式所進行的配置。|  
|**專有位元組 %**|在分析執行中配置的所有記憶體位元組中，屬於此函式之專有配置的百分比。|  
  
## <a name="see-also"></a>另請參閱  
 [呼叫樹狀圖檢視 - 檢測](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [呼叫樹狀圖檢視](../profiling/call-tree-view-sampling-data.md)   
 [呼叫樹狀圖檢視](../profiling/call-tree-view-instrumentation-data.md)



