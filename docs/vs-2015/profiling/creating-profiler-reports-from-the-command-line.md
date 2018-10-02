---
title: 從命令列建立分析工具報表 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d94a2c6c025ada73e1d43e041c2bf6e30f8b66c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47488368"
---
# <a name="creating-profiler-reports-from-the-command-line"></a>從命令列建立程式碼剖析工具報告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[從命令列建立 Profiler 報告](https://docs.microsoft.com/visualstudio/profiling/creating-profiler-reports-from-the-command-line)。  
  
**VSPerfReport** 命令列工具可讓您從分析資料 (.vsp) 檔案建立.xml 或以逗號分隔值 (.csv) 報表。 VSPerfReport 報表類型極符合 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 之介面的資料表檢視。 您可以篩選報表只顯示您的程式碼，以及只顯示分析資料檔案的區段。 如需詳細資訊，請參閱 [VSPerfReport](../profiling/vsperfreport.md)。  
  
 您也可以更輕鬆地共用分析資料檔案，方法是將符號內嵌到 .vsp 檔案，以及建立較小且更快速開啟的預先分析報表 (.vsps) 檔案。  
  
## <a name="common-tasks"></a>一般工作  
  
|工作|相關內容|  
|----------|---------------------|  
|**建立基本報表。** 建立所有 VSPerfReport 報表類型或其子集。|-   [建立基本報表](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**比較兩個分析資料檔案。** 建立 "diff" 報表，以比較兩個分析資料檔案中的效能資料。|-   [如何：從命令提示字元建立分析工具比較報表](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**檢視呼叫追蹤和 Windows 事件追蹤 (ETW) 資料。** 建立呼叫追蹤報表，以列出您應用程式函式每個進入點和結束點的計時資訊，以及您的函式對其他函式的每次呼叫。 或者，建立分析回合中所收集之所有 ETW 事件的詳細清單。|-   [如何：建立呼叫追蹤報表](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**篩選報表。** 限制報表，只顯示程式碼中的函式或分析資料檔案中的特定時間。|-   [如何：從命令列篩選報表](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**建立可移植的分析資料檔案。** 若要更輕鬆地共用分析資料，您可以將分析回合的符號內嵌到 .vsp 檔案。 您也可以建立較小且更快速開啟之預先分析的分析資料 (.vsps) 檔案。|-   [建立可移植的分析資料檔案](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|


