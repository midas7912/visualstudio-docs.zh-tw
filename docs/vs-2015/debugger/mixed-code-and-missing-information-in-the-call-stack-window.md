---
title: 混合程式碼和遺失的資訊，在呼叫堆疊視窗 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
caps.latest.revision: 23
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f4ae8e527e5f6ce04680c444baad58802bfad48
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51788923"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>呼叫堆疊視窗內的混合程式碼和遺失的資訊
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

因為 Managed 和機器碼呼叫堆疊之間的差異，當程式碼類型混合時，偵錯工具則無法永遠顯示完整的呼叫堆疊。 當機器碼呼叫 managed 程式碼時，您可能會發現下列不一致的地方**呼叫堆疊**視窗：  
  
- 正上方的 managed 程式碼的原生框架可能遺漏**呼叫堆疊**視窗。 如需詳細資訊，請參閱 <<c0> [ 如何： 原生框架遺失於呼叫堆疊視窗時跳離 Managed 程式碼](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)。  
  
- 混合式應用程式啟動偵錯工具，之外**呼叫堆疊**視窗會顯示 managed 程式碼，並且沒有任何原生框架會顯示。  
  
  這兩個狀況都相當少見。 在大多數呼叫 Managed 程式碼的原生呼叫中，呼叫堆疊看起來都是正確的。  
  
## <a name="see-also"></a>另請參閱  
 [如何：使用呼叫堆疊視窗](../debugger/how-to-use-the-call-stack-window.md)





