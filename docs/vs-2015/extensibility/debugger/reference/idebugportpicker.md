---
title: IDebugPortPicker |Microsoft Docs
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
- IDebugPortPicker interface
ms.assetid: 8b7f6685-a3c5-4355-b706-c1b574f6ff84
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 486efef813d3657b3a1b76ff5f64834f3b84a628
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51800987"
---
# <a name="idebugportpicker"></a>IDebugPortPicker
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

代表自訂的 UI 中選取連接埠。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugPortPicker : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 連接埠提供者會實作這個介面。 連接埠提供者會定義將其公開為 CLSID，並指向其連接埠選擇器`metricPortPickerCLSID`計量在公開的 CLSID。  
  
## <a name="methods"></a>方法  
 下表顯示的方法`IDebugPortPicker`。  
  
|方法|描述|  
|------------|-----------------|  
|[DisplayPortPicker](../../../extensibility/debugger/reference/idebugportpicker-displayportpicker.md)|顯示指定的對話方塊中，可讓使用者選取一個連接埠。|  
|[SetSite](../../../extensibility/debugger/reference/idebugportpicker-setsite.md)|設定服務提供者。|  
  
## <a name="requirements"></a>需求  
 標頭： Msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

