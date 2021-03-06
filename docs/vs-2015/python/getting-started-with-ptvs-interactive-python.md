---
title: Ptvs 快速入門： 互動式 Python |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa594314-bdd0-4da5-874a-57b03414b675
caps.latest.revision: 5
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 7d9438d7d80480349dd53384c2538742a22b4d36
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49183907"
---
# <a name="getting-started-with-ptvs-interactive-python"></a>PTVS 快速入門：互動式 Python
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

互動式提示或讀取 - 求值 - 輸出迴圈 (REPL) 是高產能程式設計語言的重要工具。  它們可讓您執行程式碼片段來探索和學習 API，使用 API 進行實驗，並以互動方式開發可運作的程式碼，以包含在專案或程式中。  
  
 您可以在這段簡短的 [YouTube 影片 (英文)](https://www.youtube.com/watch?v=yc2CROtTsC0&index=5&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff) 中觀看這些指示。  
  
 在 [Python 環境] 視窗中，您會看到一份您所有 Python 環境的清單。  您可以選取其中任何一項來開啟互動式視窗或 REPL。  如果您曾經在命令提示字元中執行過 Python.exe，則您之前就已見過 Python REPL。  REPL 會提示您，而且您可以輸入程式碼，按 Enter 鍵然後立即查看程式碼結果。  這是即時的執行內容，其中包含所有程式執行、指派變數等的所有狀態。您可以在稍後對 REPL 提示的提交中參考含有變數的結果。  您可以撰寫多行程式碼，並一次就執行全部 (例如方法宣告或多個陳述式)。  
  
 當您開始使用新的程式庫時，REPL 是嘗試程式庫的好方法。  您可以匯入程式庫，檢查子封裝、類別和函式。  Python 可透過其 `help()` 函式告訴您所有資訊。  此外，Python Tools for Visual Studio (PTVS) 可給您以編輯器中使用的程式碼模型為基礎的建議和文件，而不需要執行程式庫。  當您執行程式碼時，PTVS 會使用來自 Python 執行階段的資訊以改善 PTVS 建議。  
  
 [互動式視窗] 也可用於反覆或演化的程式碼開發，包含當您在開發時測試程式碼。  您可以在編輯器視窗中選取函式，請按右指標按鈕，並選擇 [傳送至互動式]。  此命令會將選取範圍複製到 [互動式視窗] 做為下一個輸入並執行。  您可立即查看結果。  如果您需變更先前的輸入，您可以按向上鍵，以取回程式碼，請修改它，並按下 Ctrl + Enter 來執行程式碼。  在輸入結束後按下 Enter 鍵執行，但在輸入中間按下 Enter 鍵則會插入一個新行。  
  
 您可以視需要為每個 Python 安裝開啟一個 [互動式視窗]。  視窗頂端有幾個按鈕可用來清除顯示和重設執行內容等。您的歷程記錄會維持不變。  
  
 您可以在這段簡短的 [YouTube 影片 (英文)](https://www.youtube.com/watch?v=yc2CROtTsC0&index=5&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff) 中觀看這些指示。  
  
## <a name="see-also"></a>另請參閱  
 [Wiki 文件 (英文)](https://github.com/Microsoft/PTVS/wiki/Interactive-REPL)   
 [PTVS 快速入門及深度剖析影片 (英文)](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)

