---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- StartTrackingContextWithRoot
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f93a82aea513eec6417b61c009ec239989f2d0c0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269698"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
使用指定根標記的回應檔啟動追蹤內容。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>參數  
 [in] `intermediateDirectory`  
 儲存追蹤記錄的目錄。  
  
 [in] `taskName`  
 找到追蹤內容。 這個名稱是用來建立記錄檔的名稱。  
  
 [in] `rootMarkerResponseFile`  
 包含根標記的回應檔路徑名稱。 根名稱是用來將內容所有的追蹤集合在一起。  
  
## <a name="return-value"></a>傳回值  
 [HRESULT] (<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) 與 [成功] (<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) 位元集，如果建立追蹤內容。  
  
## <a name="requirements"></a>需求  
 **標頭：** FileTracker.h  
  
## <a name="see-also"></a>另請參閱  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)



