---
title: 如何：從命令列篩選報表 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c173fb5cdea4c18f3d470bd1e92bd7f9b68a62e
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2018
ms.locfileid: "34814563"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>如何：從命令列篩選報表
使用 **VSPerfReport** 命令的選項，即可將報表篩選到分析資料檔案的特定時間區段，或將資料限制到一或多個處理序或執行緒。 如需此命令的詳細資訊，請參閱 [VSPerfReport](../profiling/vsperfreport.md)。  
  
|選項|描述|  
|-------------|-----------------|  
|**StartTime:**[*Value*]|只顯示值 (以毫秒為單位) 之後所收集的資料。|  
|**EndTime:**[*Value*]|只顯示值 (以毫秒為單位) 之前所收集的資料。|  
|**FilterFile:** `VSPFFile`|指定從 [Visual Studio 效能報告] 視窗所產生之篩選器檔案的位置。|  
|**MsFilter:**[*StartTime,Duration*]|只顯示從 `StartTime` 直到 `Duration` 長度(以毫秒為單位) 的資料。|  
|**Process:**[*Pid*]|只顯示來自所指定處理序的資料。|  
|**Thread:**[*ThreadID*]|只顯示來自所指定執行緒的資料。|  
|**Thread:**[*ThreadID,ProcessID*]|只顯示來自與指定處理序建立關聯之指定執行緒的資料。|