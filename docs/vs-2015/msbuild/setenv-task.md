---
title: SetEnv 工作 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.task.setenv
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- SetEnv task (MSBuild (Visual C++))
ms.assetid: fd9e4225-68cb-4608-8b27-468b0218c936
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c15f0be4498c3ff3014c273d31657851c9e65b8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205663"
---
# <a name="setenv-task"></a>SetEnv 工作
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
設定或刪除指定環境變數的值。  
  
## <a name="parameters"></a>參數  
 下表說明 **SetEnv** 工作的參數。  
  
|參數|描述|  
|---------------|-----------------|  
|**名稱**|必要的 **String** 參數。<br /><br /> 環境變數的名稱。|  
|**OutputEnvironmentVariable**|選擇性的 **String** 輸出參數。<br /><br /> 包含指派給環境變數 (由 **Name** 參數所指定) 的值。|  
|**前置詞**|必要的 `Boolean` 參數。<br /><br /> 如果系統會先將 **Value** 參數的值串連到 **Name** 參數所指定的環境變數值，然後將結果指派給環境變數，則為 `true`。 如果系統只會將 **Value** 參數的值指派給環境變數，則為 `false`。|  
|**Target**|選擇性的 **String** 參數。<br /><br /> 指定儲存環境變數的位置。 請指定 "`User`" 或 "`Machine`"。<br /><br /> 如需詳細資訊，請參閱 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 網站上的「EnvironmentVariableTarget 列舉」。|  
|**值**|選擇性的 **String** 參數。<br /><br /> 指派給環境變數 (由 **Name** 參數所指定) 的值。 如果 **Value** 是空的但存在變數，則會刪除變數。 如果變數不存在，即使無法執行此作業也不會發生任何錯誤。<br /><br /> 如需詳細資訊，請參閱 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 網站上的「Environment::SetEnvironmentVariable 方法」。|  
  
## <a name="remarks"></a>備註  
  
## <a name="see-also"></a>另請參閱  
 [工作參考](../msbuild/msbuild-task-reference.md)



