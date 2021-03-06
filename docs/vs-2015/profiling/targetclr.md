---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 517cf1eccd296716b0105539f6ae81cbc3519fd0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51759305"
---
# <a name="targetclr"></a>TargetCLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**TargetCLR** 選項指定當應用程式載入多個 CLR 版本時要分析的 Common Language Runtime (CLR) 版本。  
  
 根據預設，[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具以應用程式載入的第一個 CLR 版本為目標。  
  
## <a name="syntax"></a>語法  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>參數  
 `ClrVersion`  
 CLR 的版本號碼。 使用版本格式 **vN.N.NNNNN**。  
  
## <a name="required-options"></a>必要選項  
 **TargetCLR** 選項僅能與 [啟動] 或 [附加] 選項一起使用。  
  
 **Launch：** `AppName`  
 啟動指定的應用程式並開始分析。  
  
 **Attach:** `PID`  
 開始分析指定的處理序。  
  
## <a name="example"></a>範例  
 本例使用 TargetCLR 選項確定分析的 CLR 版本是 4.0.11003。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```



