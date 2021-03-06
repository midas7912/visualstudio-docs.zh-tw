---
title: 在建置大型專案時有效使用記憶體 | Microsoft Docs
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
- memory use (MSBuild)
- msbuild, efficient memory use building large trees
- caching (MSBuild)
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89c7102a789f07cc9f0434dd5bf351ea4814d073
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49218507"
---
# <a name="using-memory-efficiently-when-you-build-large-projects"></a>在建置大型專案時有效使用記憶體
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
大型專案通常會包含許多子專案和其他相依性，而且這些可能會在建置時間耗用大量系統記憶體。 可用系統記憶體減少時，系統效能也可能會降低。 舊版 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 專案會保留在記憶體中；而在 3.5 版中則會移除專案，但它會將建置結果保留在快取中，以供稍後擷取。  
  
 4.0 版會自動處理此記憶體管理，並儲存專案；而不需要使用 `UnloadProjectsOnCompletion` 和 `UseResultsCache` 這類屬性。  
  
## <a name="see-also"></a>另請參閱  
 [同時建置多個專案](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)



