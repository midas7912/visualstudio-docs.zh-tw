---
title: 快速監看式命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: afe27d567601e43b10323f9dcc3417bcf15e9298
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269408"
---
# <a name="quick-watch-command"></a>快速監看式命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
顯示的 [運算式] 欄位中的選取或指定的文字[快速監看式對話方塊](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)。 您可以使用此對話方塊來計算偵錯工具辨識的變數或運算式目前的值，或暫存器的內容。 此外，您可以變更任何非 const 變數的值或任何暫存器的內容。  
  
## <a name="syntax"></a>語法  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>引數  
 `text`  
 選擇性。 要新增至 [快速監看式] 對話方塊的文字。  
  
## <a name="remarks"></a>備註  
 如果省略 `text`，則會將游標處目前選取的文字或字組新增至監看式視窗。  
  
## <a name="example"></a>範例  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>另請參閱  
 [如何： 使用 快速監看式對話方塊](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [命令視窗](../../ide/reference/command-window.md)   
 [尋找/命令方塊](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



