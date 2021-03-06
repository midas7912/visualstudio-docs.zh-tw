---
title: Move 工作 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1cebddae1cc8ed980a05687208d4c8dbeaabf200
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208973"
---
# <a name="move-task"></a>Move 工作
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
將檔案移到新位置。  
  
## <a name="parameters"></a>參數  
 下表說明 `Move` 工作的參數。  
  
|參數|描述|  
|---------------|-----------------|  
|`DestinationFiles`|選擇性的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 輸出參數。<br /><br /> 指定要將來源檔案移動到其中的檔案清單。 這份清單預期會是一對一對應 `SourceFiles` 參數中指定的清單。 亦即，`SourceFiles` 中指定的第一個檔案會移動到 `DestinationFiles` 中指定的第一個位置，依此類推。|  
|`DestinationFolder`|選擇性的 <xref:Microsoft.Build.Framework.ITaskItem> 參數。<br /><br /> 指定要將檔案移動至其中的目錄。|  
|`MovedFiles`|選擇性的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 輸出參數。<br /><br /> 包含已成功移動的項目。|  
|`OverwriteReadOnlyFiles`|選擇性的 `Boolean` 參數。<br /><br /> 如果為 `true`，即使已標示為唯讀檔案，還是會覆寫這些檔案。|  
|`SourceFiles`|必要的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 參數。<br /><br /> 指定要移動的檔案。|  
  
## <a name="remarks"></a>備註  
 您必須指定 `DestinationFolder` 或 `DestinationFiles` 參數，但不能同時指定這兩者。 如果同時指定這兩者，工作即會失敗，並記錄錯誤。  
  
 除了具有表格中所列的參數之外，此工作也繼承 <xref:Microsoft.Build.Tasks.TaskExtension> 類別的參數，而該類別本身又繼承 <xref:Microsoft.Build.Utilities.Task> 類別。 如需這些其他參數的清單及其說明，請參閱 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>另請參閱  
 [工作](../msbuild/msbuild-tasks.md)   
 [工作參考](../msbuild/msbuild-task-reference.md)



