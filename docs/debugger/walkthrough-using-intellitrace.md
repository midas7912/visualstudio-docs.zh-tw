---
title: 使用 IntelliTrace 檢視事件 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: e1c9c91a-0009-4c4e-9b4f-c9ab3a6022a7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f46113365b66a75d3f9e149181637c79068645ab
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542321"
---
# <a name="view-events-with-intellitrace-in-visual-studio"></a>在 Visual Studio 中使用 IntelliTrace 檢視事件
您可以使用 IntelliTrace 收集特定事件或事件分類的相關資訊，或是事件及個別函式呼叫的相關資訊。 下列程序說明如何執行此作業。  
  
 在 Visual Studio Enterprise 版本，但不是是 Professional 或 Community 版本中，您可以使用 IntelliTrace。  
  
##  <a name="GettingStarted"></a> 設定 Intellitrace  
 您可以嘗試只針對 IntelliTrace 事件進行偵錯。 IntelliTrace 事件是偵錯工具事件、例外狀況、.NET Framework 事件，以及其他系統事件。 您應在開始偵錯之前，先開啟或關閉特定事件，以控制 IntelliTrace 所記錄的事件。 如需詳細資訊，請參閱 < [IntelliTrace 功能](../debugger/intellitrace-features.md)。  
  
 - 開啟檔案存取的 IntelliTrace 事件。 移至**工具 > 選項 > IntelliTrace > IntelliTrace 事件**頁面，然後展開**檔案**類別目錄。 核取 [檔案]  事件分類。 這會核取所有的檔案事件 (存取、關閉、刪除)。

## <a name="create-your-app"></a>建立您的應用程式
  
1.  建立 C# 主控台應用程式。 在 Program.cs 檔案中，加入下列 `using` 陳述式：  
  
    ```csharp  
    using System.IO;  
    ```  
  
2.  在 Main 方法中建立 <xref:System.IO.FileStream> ，接著加以讀取、關閉，然後再刪除該檔案。 加入另一行，以設定中斷點：  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        FileStream fs = File.Create("WordSearchInputs.txt");  
        fs.ReadByte();  
        fs.Close();  
        File.Delete("WordSearchInputs.txt");  
  
        Console.WriteLine("done");  
    }  
    ```  
  
3.  在 `Console.WriteLine("done");`上設定中斷點  

## <a name="start-debugging-and-view-intellitrace-events"></a>開始偵錯，以及檢視 IntelliTrace 事件
  
1.  照常開始偵錯 (按下**F5**或按**偵錯 > 啟動偵錯**。  
  
    > [!TIP]
    >  保持**區域變數**並**自動變數**windows 開啟當您偵錯以查看和記錄這些視窗中的值。  
  
2.  執行會在中斷點停止。 如果您看不見**診斷工具** 視窗中，按一下**偵錯 > Windows > IntelliTrace 事件**。  
  
     在 [診斷工具]  視窗中，尋找 [事件]  索引標籤 (應有 3 個索引標籤：[事件] 、[記憶體使用量] 及 [CPU 使用量] )。 [事件]  索引標籤會依時間列出事件，其結尾會是偵錯工具中斷執行前的最後一個事件。 您應該會看到一個名為 **Access WordSearchInputs.txt**的事件。  
  
     下列螢幕擷取畫面來自 Visual Studio 2015 Update 1。  
  
     ![IntelliTrace&#45;Update1](../debugger/media/intellitrace-update1.png "IntelliTrace-Update1")  
  
3.  選取該事件，然後展開其詳細資料。  
  
     下列螢幕擷取畫面來自 Visual Studio 2015 Update 1。  
  
     ![IntelliTraceUpdate1&#45;SingleEvent](../debugger/media/intellitraceupdate1-singleevent.png "IntelliTraceUpdate1 SingleEvent")  
  
     您可以選擇路徑名稱連結來開啟該檔案。 如果無法使用完整路徑名稱，會顯示 [開啟檔案 ]  對話方塊。  
  
     按一下 **啟用歷程偵錯**，其中設定偵錯工具的內容時所選的事件的時間所收集、 顯示歷程記錄資料**呼叫堆疊**，**區域變數**及其他參與偵錯工具視窗。 如果原始程式碼可用，Visual Studio 會將指標移至對應來源視窗中的程式碼，因此您可以檢查它。  
  
     下列螢幕擷取畫面來自 Visual Studio 2015 Update 1。  
  
     ![HistoricalDebugging&#45;Update1](../debugger/media/historicaldebugging-update1.png "HistoricalDebugging Update1")  
  
4.  如果沒有發現 Bug，請嘗試檢查導致 Bug 的其他事件。 您也可以讓 IntelliTrace 記錄呼叫資訊，以便您能逐步執行函式呼叫。 
  
## <a name="next-steps"></a>後續步驟

您可以使用的一些進階功能的 IntelliTrace 歷程偵錯：

 - 若要檢視快照集，請參閱[檢查先前使用 IntelliTrace 的應用程式狀態](../debugger/view-historical-application-state.md)
 - 若要了解如何檢查變數，以及巡覽程式碼，請參閱[檢查您的應用程式，使用歷程偵錯](../debugger/historical-debugging-inspect-app.md)