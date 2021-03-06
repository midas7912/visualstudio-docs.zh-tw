---
title: 類別圖表和類別細節視窗中的鍵盤和滑鼠捷徑 (類別設計工具) | Microsoft Docs
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
- vs.classdetails.window
helpviewer_keywords:
- class diagrams, keyboard shortcuts
- class diagrams, mouse shortcuts
ms.assetid: c12d8dac-9902-4fde-b721-2a8116da53b7
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f607046609208804f349eb06e927ab8e72e28992
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247906"
---
# <a name="keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer"></a>類別圖表和類別檢視視窗中的鍵盤和滑鼠捷徑 (類別設計工具)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

除了滑鼠之外，也可以在 [類別設計工具] 和 [類別細節] 視窗中使用鍵盤執行瀏覽動作。  
  
 **本主題內容**  
  
-   [在類別設計工具中使用滑鼠](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#MouseClassDesigner)  
  
-   [在類別細節視窗中使用滑鼠](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#MouseClassDetails)  
  
-   [在類別設計工具中使用鍵盤](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#KeyboardClassDesigner)  
  
-   [在類別細節視窗中使用鍵盤](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#KeyboardClassDetails)  
  
##  <a name="MouseClassDesigner"></a>在類別設計工具中使用滑鼠  
 類別圖表中可支援下列滑鼠動作：  
  
|滑鼠組合|內容|描述|  
|-----------------------|-------------|-----------------|  
|按兩下|圖案項目|開啟程式碼編輯器。|  
||棒棒糖符號連接器|展開/摺疊棒棒糖符號。|  
||棒棒糖符號連接器標籤|叫用 [顯示介面] 命令。|  
|滑鼠滾輪|類別圖表|垂直捲動。|  
|SHIFT + 滑鼠滾輪|類別圖表|水平捲動。|  
|CTRL + 滑鼠滾輪|類別圖表|縮放。|  
|CTRL + Shift + 按一下|類別圖表|縮放。|  
  
##  <a name="MouseClassDetails"></a>在類別細節視窗中使用滑鼠  
 您可以使用滑鼠變更 [類別細節] 視窗及其顯示之資料的外觀，方法如下：  
  
-   按一下任何可編輯的儲存格，即可編輯該儲存格的內容。 您的變更會反映在資料儲存或顯示的所有位置，包括在 [屬性] 視窗和原始程式碼中。  
  
-   按一下任何一列儲存格，[屬性] 視窗就會顯示該資料列所代表的項目屬性。  
  
-   若要變更資料行的寬度，請拖曳欄位標題的右邊框線到您想要的寬度。  
  
-   按一下資料列左側的箭頭符號，可展開或摺疊區間或屬性節點。  
  
-   [類別細節] 視窗可提供數個按鈕，供您在目前的類別中建立新的成員，以及在 [類別細節] 視窗方格中的成員區間之間瀏覽。 如需詳細資訊，請參閱類別細節視窗按鈕。  
  
##  <a name="KeyboardClassDesigner"></a>在類別設計工具中使用鍵盤  
 類別圖表中可支援下列鍵盤動作：  
  
|Key|內容|描述|  
|---------|-------------|-----------------|  
|方向鍵|在類型圖形內|圖形內容的樹狀樣式瀏覽 (支援圖案循環)。 如果可展開目前的項目，則向左和向右鍵可展開/摺疊該項目；如果不可展開目前的項目，則向左和向右鍵會瀏覽至父系 (請參閱樹狀檢視瀏覽，以了解詳細的行為)。|  
||最上層的圖形|移動圖表上的圖形。|  
|SHIFT+方向鍵|在類型圖形內|建置圖形項目的連續選取項目，例如成員、巢狀類型或區間。 這些快速鍵不支援循環。|  
|首頁|在類型圖形內|瀏覽至最上層圖形標題。|  
||最上層的圖形|瀏覽至圖表上的第一個圖形。|  
|END|在類型圖形內|瀏覽至圖形內最後一個可見的項目。|  
||最上層的圖形|瀏覽至圖表上的最後一個圖形。|  
|SHIFT+HOME|在類型圖形內|從圖形內目前的項目開始選取，一直到同一圖形上最上層的項目結束。|  
|SHIFT+END|在類型圖形內|與 SHIFT+HOME 相同，但方向由上而下。|  
|ENTER|在所有內容中|在圖形上叫用預設動作，按兩下滑鼠鍵也有相同的功用。 在大部分的情況下，這是檢視程式碼，但是某些項目會以不同方式定義 (棒棒糖符號、區間標頭、棒棒糖符號標籤)。|  
|+/-|在所有內容中|如果目前的焦點項目可展開，這兩個鍵能夠展開/摺疊該項目。|  
|>|在所有內容中|在含有子系的項目上，如果該項目已摺疊，則此鍵會展開該項目並瀏覽至第一個子項。|  
|<|在所有內容中|瀏覽到父項。|  
|ALT+SHIFT+L|在類型圖形內 + 類型圖形上。|請瀏覽至目前所選的棒棒糖符號圖形 (若已存在)。|  
|ALT+SHIFT+B|在類型圖形內 + 類型圖形上。|如果基底類型清單顯示在類型圖形上，且有一個以上的項目，則此鍵會切換清單的展開狀態 (展開/摺疊)。|  
|DELETE|在類型和註解圖形上|叫用 [從圖表移除] 命令。|  
||在所有其他項目上。|叫用 [從程式碼刪除] 命令 (成員、參數、關聯、繼承、棒棒糖符號標籤)。|  
|CTRL+DELETE|在所有內容中|在選取項目上叫用 [從程式碼刪除] 命令。|  
|TAB|在所有內容中|瀏覽至同一父系內的下一個子項 (支援循環)。|  
|SHIFT+TAB|在所有內容中|瀏覽至同一父系內的上一個子項 (支援循環)。|  
|空格鍵|在所有內容中|在目前的項目上切換選取項目。|  
  
##  <a name="KeyboardClassDetails"></a>在類別細節視窗中使用鍵盤  
  
> [!NOTE]
>  下列按鍵繫結關係皆是特別為了模仿程式碼的輸入經驗而選。  
  
 使用下列機碼瀏覽 [類別細節] 視窗：  
  
|||  
|-|-|  
|Key|結果|  
|, (逗號)|如果游標位於參數資料列中，輸入逗號會將游標移至下一個參數的 [名稱] 欄位。 如果游標位於某個方法的最後一個參數資料列中，輸入逗號會將游標移至 \<新增參數> 欄位中，讓您用以建立新的參數。<br /><br /> 如果游標位於 [類別細節] 視窗的別處，輸入逗號就會在目前欄位中加入一個逗號。|  
|; (分號)<br /><br /> 或<br /><br /> ) (右括弧)|在 [類別細節] 視窗方格中，將游標移至下一個成員資料列的 [名稱] 欄位。|  
|索引標籤|將游標移到下一個欄位，先從左到右移動，然後由上而下。 如果要從某個您已輸入文字的欄位移動游標，[類別細節] 視窗會先處理該文字，若沒有產生錯誤，則會儲存該文字。<br /><br /> 如果游標位於空白欄位，例如 \<新增參數>，Tab 鍵會將游標移至下一個資料列的第一個欄位。|  
|\<空格>|將游標移到下一個欄位，先從左到右移動，然後由上而下。 如果游標位於空白欄位，例如 \<新增參數>，空格鍵會將游標移至下一個資料列的第一個欄位。 請注意，逗號之後立即輸入 \<空格> 會被忽略。<br /><br /> 如果游標位於 [摘要] 欄位中，輸入空格會加入空白字元。<br /><br /> 如果游標位於指定之資料列的隱藏資料行中，輸入空格會切換 [隱藏] 核取方塊的值。|  
|Ctrl+Tab|切換至另一個文件視窗。 例如，從 [類別細節] 視窗切換到開啟的程式碼檔案。|  
|ESC (離開)|如果您已經開始在欄位中輸入文字，按下 ESC 鍵可做為復原索引鍵，將欄位內容還原成先前的值。 如果 [類別細節] 視窗具有一般焦點，但沒有任何特定的儲存格具有焦點，則按下 ESC 鍵會將焦點從 [類別細節] 視窗移開。|  
|向上鍵或向下鍵|這兩個鍵可在 [類別細節] 視窗方格中，以垂直方向逐列移動游標。|  
|向左鍵|如果游標位於 [名稱] 資料行中，按向左鍵可摺疊階層中目前的節點 (如果已展開)。|  
|向右鍵|如果游標位於 [名稱] 資料行中，按向右鍵可展開階層中目前的節點 (如果已摺疊)。|  
  
## <a name="see-also"></a>另請參閱  
 [建立和設定類型成員 (類別設計工具)](../ide/creating-and-configuring-type-members-class-designer.md)



