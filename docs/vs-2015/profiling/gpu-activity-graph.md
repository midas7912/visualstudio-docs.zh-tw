---
title: GPU 活動圖 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38ba74ac314710b1202f13373685ddbdda0df0f6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51791120"
---
# <a name="gpu-activity-graph"></a>GPU 活動圖
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

並行視覺化檢視中的 GPU 活動圖顯示系統上的 DirectX 活動層級，這是以一段時間內使用中的 DirectX 引擎數目來測量。  活動圖不會顯示使用哪些特定引擎。  正在處理任一 GPU 工作的引擎會視為使用中。  
  
## <a name="gpu-activity-graph-colors"></a>GPU 活動圖色彩  
 綠色表示目前處理序的 DirectX 引擎的耗用量。  
  
 淺灰色表示系統上其他處理序的 DirectX 引擎耗用量。 若要減少其他處理序的 DirectX 引擎耗用量，請減少系統上執行的其他處理序數目。  
  
 白色表示系統上未使用的 DirectX 引擎的可用性。 如果您可以找到更多機會利用它們，這些引擎都適用於您的處理序。 部分引擎只能用於特定種類的工作。  
  
## <a name="see-also"></a>另請參閱  
 [使用率檢視](../profiling/utilization-view.md)



