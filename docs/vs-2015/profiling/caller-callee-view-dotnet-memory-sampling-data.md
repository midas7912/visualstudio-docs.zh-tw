---
title: 呼叫端-被呼叫端檢視 - .NET 記憶體取樣資料 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Caller/Callee view
ms.assetid: 36f5b4de-5686-4f40-9e72-f4aee27d833c
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04ba2a522c6accb9dcb5e316ea8c63beb260e739
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47489251"
---
# <a name="callercallee-view---net-memory-sampling-data"></a>呼叫端/被呼叫端檢視 - .NET 記憶體取樣資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[呼叫端-被呼叫端檢視-.NET 記憶體取樣資料](https://docs.microsoft.com/visualstudio/profiling/caller-callee-view-dotnet-memory-sampling-data)。  
  
[呼叫端/被呼叫端] 檢視會顯示所選取函式及其父函式和子函式的 .NET 記憶體分析資料。 [呼叫端/被呼叫端] 檢視包含三個方格。  
  
 **目前的函式**會顯示在中間方格中，顯示所選取函式的記憶體分析資訊。 這些值包括對函式的所有取樣呼叫。  
  
 **呼叫目前函式的函式**會顯示在上方方格中，顯示所選取 (目前) 函式 (從呼叫端 (父) 函式的呼叫所產生) 的值數量。  
  
 **目前的函式所呼叫的函式**會顯示在下方方格中，顯示所選取函式之被呼叫端 (子) 函式 (由目前函式呼叫) 的記憶體分析資料。  
  
 按兩下呼叫端或被呼叫端函式資料列，讓該資料列變成目前的函式。  
  
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
|**Type**|函式的內容︰<br /><br /> **0** - 目前的函式<br /><br /> **1** - 呼叫目前函式的函式<br /><br /> **2** - 目前的函式所呼叫的函式<br /><br /> 只存在於 [VSPerfReport](../profiling/vsperfreport.md) 命令列報表中。|  
|**層級**|函式在呼叫樹狀圖中的深度。 只存在於 [VSPerfReport](../profiling/vsperfreport.md) 命令列報表中。|  
|**內含配置**|- 若為目前的函式，這是函式在分析執行中所配置的物件數目。 這個數目包括在被呼叫端函式中所建立的物件。<br />- 若為呼叫端函式，這是目前函式 (從此函式的呼叫所產生) 的內含配置數目。<br />- 若為被呼叫端函式，這是此函式之執行個體 (由目前函式呼叫) 所配置的物件數目。 這個數目包含由被呼叫端函式所呼叫之函式所做的配置。|  
|**內含配置 %**|在分析執行中建立的所有物件中，屬於此函式之內含配置的百分比。|  
|**專有配置**|- 若為目前的函式，這是當函式執行函式主體程式碼時 (即函式位於呼叫堆疊的最上方) 所建立的物件數目。 這個數目不包含由此函式呼叫之函式建立的物件。<br />- 若為呼叫端函式，這是目前函式 (從此函式的呼叫所產生) 的專有配置數目。<br />- 若為被呼叫端函式，這是此函式之執行個體 (由目前函式呼叫) 所建立的物件數目。 這個數目不包含被呼叫端函式呼叫之函式建立的物件。|  
|**專有配置 %**|在分析執行中建立的所有物件中，屬於此函式之內含配置的百分比。|  
|**內含位元組**|- 若為目前的函式，這是函式在分析執行中所配置的記憶體位元組數目。 這個數目包含配置在由此函式所呼叫之函式中的記憶體。<br />- 若為呼叫端函式，這是目前函式 (由呼叫端函式呼叫所產生) 的內含位元組數目。<br />- 若為被呼叫端函式，這是此函式之執行個體 (從目前函式的呼叫所產生) 所配置的位元組數目。 這個數目包含由被呼叫端函式呼叫之函式所配置的位元組。|  
|**內含位元組 %**|在分析執行中配置的所有記憶體位元組中，屬於此函式之內含配置的百分比。|  
|**專有位元組**|- 若為目前的函式，這是函式在分析執行中所配置的記憶體位元組數目。 這個數目不包含由目前函式呼叫之函式所配置的記憶體。<br />- 若為呼叫端函式，這是目前函式 (從呼叫端函式的呼叫所產生) 的專有位元組數目。<br />- 若為被呼叫端函式，這是函式之執行個體 (從目前函式的呼叫所產生) 所配置的位元組數目。 這個數目不包含由被呼叫端函式呼叫之函式所配置的位元組。|  
|**專有位元組 %**|在分析執行中配置的所有記憶體位元組中，屬於此函式之專有配置的百分比。|  
  
## <a name="see-also"></a>另請參閱  
 [如何：自訂報表檢視資料行](../profiling/how-to-customize-report-view-columns.md)   
 [呼叫端/被呼叫端檢視 - .NET 記憶體檢測資料](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [呼叫端/被呼叫端檢視 - 取樣資料](../profiling/caller-callee-view-sampling-data.md)   
 [呼叫者/被呼叫者檢視 - 檢測資料](../profiling/caller-callee-view-instrumentation-data.md)


