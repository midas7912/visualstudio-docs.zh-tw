---
title: IDebugProcessEx2::Attach |Microsoft Docs
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
- IDebugProcessEx2::Attach
helpviewer_keywords:
- IDebugProcessEx2::Attach method
ms.assetid: f3334ed7-39bf-4d02-a338-36f567b9b287
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: daeef787ff380a17da2d5afa9c0f806f807b8598
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51745223"
---
# <a name="idebugprocessex2attach"></a>IDebugProcessEx2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

這個方法會通知程序工作階段現在正在偵錯程序。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT Attach(   
   IDebugSession2* pSession  
);  
```  
  
```csharp  
int Attach(  
   IDebugSession2 pSession  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pSession`  
 [in]值，這個值可唯一識別附加至此處理序的工作階段。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 介面傳入`pSession`cookie 中，可唯一識別工作階段的偵錯管理員附加至此處理序; 值僅被視為是提供的介面上的方法沒有任何功能。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)

