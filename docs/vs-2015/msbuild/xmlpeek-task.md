---
title: XmlPeek 工作 | Microsoft Docs
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
- XmlPeek task [MSBuild]
- MSBuild, XmlPeek task
ms.assetid: 19196031-a3bc-41b5-9c4a-f2572630e179
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6ad86c061d089b7cedaf040082fe9f51ae26120
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289766"
---
# <a name="xmlpeek-task"></a>XmlPeek 工作
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
從 XML 檔案傳回 XPath 查詢所指定的值。  
  
## <a name="parameters"></a>參數  
 下表說明 `XmlPeek` 工作的參數。  
  
|參數|描述|  
|---------------|-----------------|  
|`Namespaces`|選擇性的 `String` 參數。<br /><br /> 指定 XPath 查詢前置詞的命名空間。|  
|`Query`|選擇性的 `String` 參數。<br /><br /> 指定 XPath 查詢。|  
|`Result`|選擇性的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 輸出參數。<br /><br /> 包含此工作所傳回的結果。|  
|`XmlContent`|選擇性的 `String` 參數。<br /><br /> 以字串形式指定 XML 輸入。|  
|`XmlInputPath`|選擇性的 <xref:Microsoft.Build.Framework.ITaskItem> 參數。<br /><br /> 將 XML 輸入指定為檔案路徑。|  
  
## <a name="remarks"></a>備註  
 除了具有表格中所列的參數之外，此工作也繼承 <xref:Microsoft.Build.Tasks.TaskExtension> 類別的參數，而該類別本身又繼承 <xref:Microsoft.Build.Utilities.Task> 類別。 如需這些其他參數的清單及其說明，請參閱 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="see-also"></a>另請參閱  
 [工作](../msbuild/msbuild-tasks.md)   
 [工作參考](../msbuild/msbuild-task-reference.md)



