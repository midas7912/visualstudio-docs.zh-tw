---
title: IDebugEvent2::GetAttributes |Microsoft Docs
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
- IDebugEvent2::GetAttributes
helpviewer_keywords:
- IDebugEvent2::GetAttributes
ms.assetid: 2ac5b5fb-da17-43f7-811a-313f677e60d7
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 36facb636797f92788d32ef090250ad44316ee56
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51791341"
---
# <a name="idebugevent2getattributes"></a>IDebugEvent2::GetAttributes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

取得這個偵錯事件的屬性。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT GetAttribute(   
   DWORD* pdwAttrib  
);  
```  
  
```csharp  
int GetAttribute(   
   out uint pdwAttrib  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pdwAttrib`  
 [out]從旗標的組合[EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)列舉型別。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)介面是通用於所有事件。 這個方法會描述類型的事件;比方說，是同步或非同步的事件，並就停止事件。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)

