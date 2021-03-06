---
title: 參考 （程式設計擷取） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66e80d02ac41d78f2c79e7b2accb11388d456ad8
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744278"
---
# <a name="reference-programmatic-capture"></a>參考 (程式設計擷取)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

透過程式設計擷取應用程式開發介面，圖形診斷支援以程式設計方式控制其擷取功能。 您可以使用這個應用程式開發介面，在圖形診斷抬頭顯示器 (HUD) 切換並加入訊息、初始化和建立圖形記錄檔，以及擷取圖形資訊。  
  
## <a name="programmatic-capture-apis"></a>程式設計擷取應用程式開發介面  
  
### <a name="classes"></a>類別  
  
|名稱|描述|  
|----------|-----------------|  
|[VsgDbg 類別](../debugger/vsgdbg-class.md)|表示以程式設計方式控制圖形診斷應用程式內部元件的介面。|  
  
### <a name="preprocessor-symbols"></a>前置處理器符號  
  
|名稱|描述|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)|出現時，定義圖形記錄檔是否儲存到使用者的暫存檔目錄。|  
|[VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)|定義圖形記錄檔的預設檔案名稱。|  
|[VSG_NODEFAULT_INSTANCE](../debugger/vsg-nodefault-instance.md)|出現時，定義是否提供 `VsgDbg` 類別的預設執行個體。|  
  
## <a name="related-articles"></a>相關文章  
  
|標題|描述|  
|-----------|-----------------|  
|[Capturing Graphics Information](../debugger/capturing-graphics-information.md)|示範如何從 DirectX 應用程式擷取圖形資訊，以便使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 圖形診斷工具來診斷轉譯問題。|  
|[概觀](../debugger/overview-of-visual-studio-graphics-diagnostics.md)|示範圖形診斷如何協助您偵錯 DirectX 遊戲和應用程式的轉譯錯誤。|



