---
title: IDE 所實作的回呼函式 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
caps.latest.revision: 25
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5d2bf114a22419e5ed4621db52a68d266e2e7d0e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807517"
---
# <a name="callback-functions-implemented-by-the-ide"></a>IDE 所實作的回呼函式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

若要與整合做越好，並提供統一的使用者體驗，無縫整合式的開發環境 (IDE) 的原始檔控制外掛程式可以使用由 IDE 所實作的回呼函式。 此外掛程式可以呼叫這些函式在適當的時間期間將資訊傳遞給在 IDE 中; 的原始檔控制作業IDE 可以做為內嵌的項目在其原生 UI 中顯示這項資訊。 使用者會有較分散的體驗，在此案例中比若外掛程式採用自己的 UI。  
  
 Scc.h 為必要的標頭檔案。 預設位置是 \Program Files\VSIP 8.0\EnvSDK\common\inc\\。 它也會處於 \Program Files\VSIP 8.0\MSSCCI 在有原始檔控制外掛程式範例的 VSIP 資料夾\\。  
  
## <a name="in-this-section"></a>本節內容  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 描述回呼函式，以供[SccOpenProject](../extensibility/sccopenproject-function.md)顯示從原始檔控制外掛程式，透過 IDE 的訊息。  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 描述回呼函式，以供[SccPopulateList](../extensibility/sccpopulatelist-function.md)當 IDE 並沒有完整存取權僅適用於原始檔控制外掛程式，例如版本控制下的檔案的完整清單的資訊。  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 描述回呼函式，以供[SccQueryChanges](../extensibility/sccquerychanges-function.md)作業。  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 描述回呼函式，以供[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)作業。  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 描述設定呼叫的回呼函式[SccSetOption](../extensibility/sccsetoption-function.md) ，可讓原始檔控制外掛程式名稱變更回 IDE 進行通訊。  
  
## <a name="related-sections"></a>相關章節  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 開啟專案。  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 會檢查其目前狀態的檔案清單。 此外，會使用`pfnPopulate`檔案類型不符合的準則時告知呼叫端函式`nCommand`。  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 會檢查目錄和檔案的專案或在原始檔控制的專案中的清單。 每個找到的目錄和檔案名稱會傳遞至回呼函式。  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 會檢查已對一份檔案的名稱變更。 每個檔案名稱會傳遞至回呼函式，以及其變更狀態。  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 設定各種不同的選項。 每個選項開頭`SCC_OPT_xxx`而且有它自己組已定義的值。  
  
 [原始檔控制外掛程式](../extensibility/source-control-plug-ins.md)  
 描述內容的原始檔控制外掛程式 SDK 參考 > 一節。

