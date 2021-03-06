---
title: VSPerfCLREnv | Microsoft Docs
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
- command-line tools, VSPerfCLREnv
- command line, tools
- performance tools, VSPerfCLREnv
- profiling tools,VSPerfCLREnv
- VSPerfCLREnv tool
ms.assetid: 4bc9dd6e-379c-4930-9bba-59a4faa93303
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ff359904b2b4d8b10dbc180f076606651028e80
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51741508"
---
# <a name="vsperfclrenv"></a>VSPerfCLREnv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCLREnv 工具可用來設定分析 .NET Framework 應用程式所需的環境變數。 其使用下列語法：  
  
```  
VsPerfCLREnv [/option]  
```  
  
 您選擇的選項取決於您使用的三種程式碼剖析類型︰ 取樣、檢測或全域。 需要個別的選項，才能在程式碼剖析資料中包含階層互動資料。 下表描述述每個選項的語法。  
  
> [!NOTE]
>  當您完成程式碼剖析時，搭配 **/off** 或 **/globaloff** 選項執行 **VSPerfCLREnv**，以刪除程式碼剖析所需的環境變數。 如需詳細資訊，請參閱「刪除環境設定的 VSPerfCLREnv 選項」，如下所示。  
  
 **用於包含階層互動資料的 VSPerfCLREnv 選項**  
  
> [!WARNING]
>  使用 [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)]、 [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)] 或 [!INCLUDE[vs_pro_current_short](../includes/vs-pro-current-short-md.md)] 可以收集階層互動分析。 不過，只能在 [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)] 和 [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]檢視階層互動分析資料。  
  
 階層互動分析會提供多介層應用程式中有關 ADO.NET 查詢的其他資訊。 只針對同步函式呼叫收集資料。 互動資料可以使用任何程式碼剖析方法加入至任何程式碼剖析執行。  
  
 **InteractionOn** 和 **GlobalInteractionOn** 選項可啟用收集階層互動資料的功能。 在設定分析應用程式所需的 VSPerfCLREnv 環境變數之後，必須設定互動選項。  
  
 下列範例包含使用取樣方法執行程式碼剖析的階層互動資料︰  
  
```  
VSPerfCLREnv /SampleOn  
VSPerfCLREnv /InteractionOn  
VSPerfCmd /Start:Sample /Output:MyApp.exe.vsp /Launch:MyApp.exe  
```  
  
 下列範例包含對 Windows 服務執行程式碼剖析的階層互動資料︰  
  
```  
VSPerfCLREnv /GlobalSampleOn  
VSPerfCLREnv /GlobalInteractionOn  
REM Restart the computer and start the service  
VSPerfCmd /Start:Sample /Output:MyService.exe.vsp   
VSPerfCmd /Attach:MyService.exe  
```  
  
 **用於處理序檢測程式碼剖析的 VSPerfCLREnv 選項**  
  
 下表描述用於檢測程式碼剖析的 VSPerfCLREnv 選項︰  
  
|選項|描述|  
|------------|-----------------|  
|**TraceOn**|使用檢測方法啟用程式碼剖析功能。 不會啟用記憶體配置程式碼剖析功能或收集物件存留期資料。|  
|**TraceGC**|使用檢測方法啟用記憶體配置程式碼剖析功能。 不會啟用收集物件存留期資料的功能。|  
|**TraceGCLife**|使用檢測方法啟用記憶體配置程式碼剖析功能和收集物件存留期資料。|  
  
 **用於處理序取樣程式碼剖析的 VSPerfCLREnv 選項**  
  
 下表描述用於取樣程式碼剖析的 VSPerfCLREnv 選項︰  
  
|選項|描述|  
|------------|-----------------|  
|**SampleOn**|使用取樣方法啟用程式碼剖析功能。 不會啟用記憶體配置程式碼剖析功能或收集物件存留期資料。|  
|**SampleGC**|使用取樣方法啟用記憶體配置程式碼剖析功能。 不會啟用收集物件存留期資料的功能。|  
|**SampleGCLife**|使用取樣方法啟用記憶體配置程式碼剖析功能。 也會啟用收集物件存留期資料的功能。|  
|**SampleLineOff**|停用收集 .NET 程式行層級程式碼剖析資料的功能。|  
  
 **用於全域程式碼剖析的 VSPerfCLREnv 選項**  
  
 若要分析受管理服務和由作業系統啟動而不是使用者啟動的 ASP.NET Web 應用程式，請選擇使用進行全域程式碼剖析的 VSPerfCLREnv 選項。 下表描述 VSPerfCLREnv 選項的全域版本︰ 這些選項可在登錄中設定適當的環境變數。  
  
|選項|描述|  
|------------|-----------------|  
|**GlobalTraceOn**|使用檢測方法啟用全域程式碼剖析功能。 不會收集記憶體配置事件或物件存留期資料。|  
|**GlobalTraceGC**|使用檢測方法啟用全域記憶體配置程式碼剖析功能。 不會啟用收集物件存留期資料的功能。|  
|**GlobalTraceGCLife**|使用檢測方法啟用全域記憶體配置程式碼剖析功能。 也會啟用收集物件存留期資料的功能。|  
|**GlobalSampleOn**|使用取樣方法啟用全域程式碼剖析功能。 不會啟用收集記憶體配置事件或物件存留期資料的功能。|  
|**GlobalSampleGC**|使用取樣方法啟用全域記憶體配置程式碼剖析功能。 不會啟用收集物件存留期資料的功能。|  
|**GlobalSampleGCLife**|使用取樣方法啟用全域記憶體配置程式碼剖析功能。 也會啟用收集物件存留期資料的功能。|  
  
 **刪除環境設定的 VSPerfCLREnv 選項**  
  
 當您完成對 Managed 應用程式進行程式碼剖析時，使用下列其中一個選項來刪除 VSPerfCLREnv 所加入的環境變數。 下表描述如何刪除這兩個標準和全域環境變數︰  
  
|選項|描述|  
|------------|-----------------|  
|**Off**|刪除標準 .NET 程式碼剖析的環境變數。 使用非全域 VSPerfClrEnv 選項來設定分析工具環境變數時，請使用此選項。|  
|**GlobalOff**|刪除全域 .NET 程式碼剖析的環境變數。 當應用程式由作業系統啟動且不是分析工具時，請使用此選項。|  
  
## <a name="remarks"></a>備註  
 如果使用 IDE 中的 [效能總管] 來啟動應用程式，對 Managed 應用程式進行程式碼剖析時，不需要這些選項。 [效能總管] 可為您設定所有必要的環境設定。  
  
 如果程式碼剖析期間未設定正確的環境，會在分析期間報告警告且無法正確解析 Managed 函式名稱。  
  
## <a name="see-also"></a>另請參閱  
 [從命令列進行程式碼剖析](../profiling/using-the-profiling-tools-from-the-command-line.md)



