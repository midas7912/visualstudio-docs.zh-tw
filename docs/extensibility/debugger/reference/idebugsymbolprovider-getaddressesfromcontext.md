---
title: IDebugSymbolProvider::GetAddressesFromContext |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 94920e72b7d83e45fc7d7e49849f3c1983b180ef
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49931515"
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
這個方法會將文件內容對應到的偵錯位址陣列。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetAddressesFromContext(   
   IDebugDocumentContext2* pDocContext,  
   BOOL                    fStatmentOnly,  
   IEnumDebugAddresses**   ppEnumBegAddresses,  
   IEnumDebugAddresses**   ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromContext(  
   IDebugDocumentContext2  pDocContext,  
   bool                    fStatmentOnly,  
   out IEnumDebugAddresses ppEnumBegAddresses,  
   out IEnumDebugAddresses ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pDocContext`  
 [in]文件內容中。  
  
 `fStatmentOnly`  
 [in]如果為 TRUE，會限制單一陳述式的偵錯位址。  
  
 `ppEnumBegAddresses`  
 [out]傳回與這個陳述式或列關聯的開始偵錯位址的列舉值。  
  
 `ppEnumEndAddresses`  
 [out]傳回[IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)結束此陳述式或列相關聯的偵錯地址的列舉值。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 文件內容通常表示一組原始程式行。 此方法可讓您提供的開始和結束偵錯位址相關聯這幾行。 有些語言允許跨越多行或包含多個陳述式的行的陳述式。 這個方法會提供要限制為單一陳述式的偵錯位址的旗標。  
  
 可以單一的陳述式，才會有多個偵錯位址，如同範本的情況。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)