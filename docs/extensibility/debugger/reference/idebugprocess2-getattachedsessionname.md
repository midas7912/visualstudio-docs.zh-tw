---
title: IDebugProcess2::GetAttachedSessionName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 89f1ea6e91176486c55ca2d84188e8183278cc1f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49928980"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
取得正在偵錯此處理程序之工作階段的名稱。 IDE 可以顯示這項資訊偵錯特定的電腦上特定處理序的使用者。  
  
> [!NOTE]
>  這個方法已被取代，且它的實作應該一律會傳回`E_NOTIMPL`。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pbstrSessionName`  
  
## <a name="return-value"></a>傳回值  
 這個方法應該一律傳回`E_NOTIMPL`。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)