---
title: 混合程式碼和遺失的資訊，在呼叫堆疊視窗 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdcde5a0a597d038015c80f5d26add66158542ff
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49850928"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>呼叫堆疊視窗內的混合程式碼和遺失的資訊
因為 Managed 和機器碼呼叫堆疊之間的差異，當程式碼類型混合時，偵錯工具則無法永遠顯示完整的呼叫堆疊。 當機器碼呼叫 managed 程式碼時，您可能會發現下列不一致的地方**呼叫堆疊**視窗：  
  
- 正上方的 managed 程式碼的原生框架可能遺漏**呼叫堆疊**視窗。 如需詳細資訊，請參閱 <<c0> [ 如何： 原生框架遺失於呼叫堆疊視窗時跳離 Managed 程式碼](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)。  
  
- 混合式應用程式啟動偵錯工具，之外**呼叫堆疊**視窗會顯示 managed 程式碼，並且沒有任何原生框架會顯示。  
  
  這兩個狀況都相當少見。 在大多數呼叫 Managed 程式碼的原生呼叫中，呼叫堆疊看起來都是正確的。  
  
## <a name="see-also"></a>另請參閱  
 [如何：使用呼叫堆疊視窗](../debugger/how-to-use-the-call-stack-window.md)