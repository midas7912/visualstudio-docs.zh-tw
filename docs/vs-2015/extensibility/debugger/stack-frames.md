---
title: 堆疊框架 |Microsoft Docs
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
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebd9f1881f0e0579a3b319f6608cdbf348ed027b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789326"
---
# <a name="stack-frames"></a>堆疊框架
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

偵錯工具就架構而言，**堆疊框架**:  
  
-   是抽象的提供執行緒的執行內容堆疊。 執行緒永遠是在函式內執行。 堆疊框架會保留它的函式和引數的本機變數。 若要使用 Visual Studio 進行偵錯，語言或正在進行偵錯的環境必須支援堆疊框架。  
  
-   可以同時識別並描述自己，並可傳回相關聯的執行緒。 表示目前的指令指標，以及相關聯的文件的程式碼內容和運算式評估內容，也可以傳回堆疊框架。  
  
-   具有的屬性名稱、 類型和值的本機變數和引數，也是如此，和哪些要顯示在各種不同的 IDE 偵錯視窗。  
  
-   由[IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)通常所偵錯引擎 (DE) 或由於執行執行緒的虛擬機器建立的介面。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具內容](../../extensibility/debugger/debugger-contexts.md)   
 [偵錯工具概念](../../extensibility/debugger/debugger-concepts.md)   
 [偵錯引擎](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)

