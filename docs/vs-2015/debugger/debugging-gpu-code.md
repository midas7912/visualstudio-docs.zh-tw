---
title: 偵錯 GPU 程式碼 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ccad74608cc2332317a9a0c3081ef022b13a202d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51738416"
---
# <a name="debugging-gpu-code"></a>偵錯 GPU 程式碼
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以對圖形處理器 (GPU) 上執行的 C++ 程式碼進行偵錯。 在 Visual Studio 中的 GPU 偵錯支援包括競爭偵測、啟動處理序和附加至處理序，以及整合到偵錯視窗中。  
  
## <a name="supported-platforms"></a>支援的平台  
 [!INCLUDE[win7](../includes/win7-md.md)]、[!INCLUDE[win8](../includes/win8-md.md)]、[!INCLUDE[winsvr08_r2](../includes/winsvr08-r2-md.md)] 和 [!INCLUDE[winserver8](../includes/winserver8-md.md)] 都支援偵錯。 如需在軟體模擬器上偵錯，則需要使用 [!INCLUDE[win8](../includes/win8-md.md)] 或 [!INCLUDE[winserver8](../includes/winserver8-md.md)]。 如需在硬體上偵錯，您必須安裝圖形卡的驅動程式。 並非所有硬體廠商都實作所有偵錯工具功能。 請參閱廠商文件以了解限制。  
  
> [!NOTE]
>  若獨立硬體廠商想要支援 Visual Studio 中的 GPU 偵錯，則必須建立實作 VSD3DDebug 介面並且以自己的驅動程式為目標的 DLL。  
  
## <a name="configuring-gpu-debugging"></a>設定 GPU 偵錯  
 偵錯工具無法在相同應用程式執行時中斷 CPU 程式碼和 GPU 程式碼。 根據預設，偵錯工具會中斷 CPU 程式碼。 若要對 GPU 程式碼進行偵錯，請使用這兩個步驟的其中一個：  
  
-   在 **偵錯的型別**清單**標準**工具列上，選擇**僅限 GPU**。  
  
-   在 **方案總管**，在專案的捷徑功能表，選擇**屬性**。 在 **屬性頁**對話方塊中，選取**偵錯**，然後選取**僅限 GPU**中**偵錯工具類型**清單。  
  
## <a name="launching-and-attaching-to-applications"></a>啟動和附加至應用程式  
 您可以使用 Visual Studio 偵錯命令啟動和停止 GPU 偵錯。 如需詳細資訊，請參閱[使用偵錯工具巡覽程式碼](../debugger/navigating-through-code-with-the-debugger.md)。 您也可以將 GPU 偵錯工具附加至執行中的處理序，但是只有在該處理序執行 GPU 程式碼時才能這樣做。 如需詳細資訊，請參閱 <<c0> [ 附加至執行的處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。  
  
## <a name="run-current-tile-to-cursor-and-run-to-cursor"></a>執行目前 Tile 至游標處和執行至游標處  
 在 GPU 上偵錯時，您有兩個選項可以執行至游標位置。 這兩個選項的命令可從程式碼編輯器的捷徑功能表使用。  
  
1.  **執行至游標處**命令會執行您的應用程式，直到它到達游標位置，則會中斷。 這並不表示目前執行緒會執行至游標處，而是表示到達游標位置的第一個執行緒觸發中斷。 請參閱[使用偵錯工具巡覽程式碼](../debugger/navigating-through-code-with-the-debugger.md)  
  
2.  **執行目前 Tile 至游標處**命令會執行您的應用程式，直到目前 tile 中執行緒的所有連線到資料指標，然後中斷。  
  
## <a name="debugging-windows"></a>偵錯視窗  
 您可以使用某些偵錯視窗檢查和凍結 GPU 執行緒，以及為它們加上旗標。 如需詳細資訊，請參閱:  
  
-   [使用平行堆疊視窗](../debugger/using-the-parallel-stacks-window.md)  
  
-   [使用工作視窗](../debugger/using-the-tasks-window.md)  
  
-   [如何：使用平行監看式視窗](../debugger/how-to-use-the-parallel-watch-window.md)  
  
-   [偵錯執行緒和處理序](../debugger/debug-threads-and-processes.md)（[偵錯位置] 工具列）  
  
-   [如何：使用 GPU 執行緒視窗](../debugger/how-to-use-the-gpu-threads-window.md)  
  
## <a name="data-synchronization-exceptions"></a>資料同步處理的例外狀況  
 偵錯工具可能在執行期間識別出幾個資料同步處理的情況。 當偵測到某種情況時，偵錯工具就會進入中斷模式。 有兩個選項 —**中斷**或是**繼續**。 藉由使用**例外狀況** 對話方塊中，您可以設定是否要偵錯工具會偵測這些條件，並也哪些情況中斷。 如需詳細資訊，請參閱 <<c0> [ 偵錯工具管理例外狀況](../debugger/managing-exceptions-with-the-debugger.md)。 您也可以使用**選項**對話方塊來指定偵錯工具應該忽略例外狀況，是否寫入的資料不會變更資料的值。 如需詳細資訊，請參閱 [General, Debugging, Options Dialog Box](../debugger/general-debugging-options-dialog-box.md)。  
  
## <a name="troubleshooting"></a>疑難排解  
  
### <a name="specifying-an-accelerator"></a>指定加速器  
 GPU 程式碼中的中斷點才會叫用的程式碼執行[accelerator::direct3d_ref](http://msdn.microsoft.com/library/a514b1a7-3b3f-4011-be6c-f7b0d9a42663) (REF) 加速器。 如果您未在程式碼中指定加速器，做為自動選取 REF 加速器**偵錯加速器類型**專案屬性中。 如果您的程式碼明確選取加速器，則不會在偵錯期間使用 REF 加速器，而且除非您的 GPU 硬體支援偵錯，否則不會叫用中斷點。 您可以撰寫自己的程式碼補救這種情況，讓程式碼在偵錯期間使用 REF 加速器。 如需詳細資訊，請參閱專案屬性和[使用 accelerator 和 accelerator_view 物件](http://msdn.microsoft.com/library/18f0dc66-8236-4420-9f46-1a14f2c3fba1)並[c + + 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)。  
  
### <a name="conditional-breakpoints"></a>條件中斷點  
 GPU 程式碼支援條件中斷點，不過，並非所有運算式都可以在裝置上進行評估。 如果運算式無法在裝置上評估，就會在偵錯工具上評估。 偵錯工具的執行速度可能會比裝置更慢。  
  
### <a name="error-there-is-a-configuration-issue-with-the-selected-debugging-accelerator-type"></a>錯誤：選取的偵錯加速器類型發生設定問題。  
 如果專案設定和您進行偵錯所在電腦的組態不一致，就會發生這個錯誤。 如需詳細資訊，請參閱 < [c + + 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)。  
  
### <a name="error-the-debug-driver-for-the-selected-debugging-accelerator-type-is-not-installed-on-the-target-machine"></a>錯誤：選取的偵錯加速器類型的偵錯驅動程式未安裝在目標電腦上。  
 如果您是在遠端電腦上進行偵錯，就會發生這個錯誤。 在執行階段之前，偵錯工具無法判斷驅動程式是否安裝在遠端電腦上。 驅動程式可向圖形卡的製造商取得。  
  
### <a name="error-timeout-detection-and-recovery-tdr-must-be-disabled-at-the-remote-site"></a>錯誤：遠端網站必須停用「逾時偵錯與復原」(TDR)。  
 C++ AMP 計算可能會超過 Windows 逾時偵測與復原程序 (TDR) 所設定的預設時間間隔。 發生這種情況時，計算就會取消，而且資料將會遺失。 如需詳細資訊，請參閱 < [c + + AMP 中的處理 TDRs](http://go.microsoft.com/fwlink/p/?LinkId=249154)。  
  
## <a name="see-also"></a>另請參閱  
 [逐步解說： 偵錯 c + + AMP 應用程式](http://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)   
 [C + + 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [開始在 Visual Studio 中的 GPU 偵錯](http://go.microsoft.com/fwlink/p/?LinkId=255381)



