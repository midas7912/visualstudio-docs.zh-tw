---
title: IDebugProperty3::GetStringChars |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7d6df39bcd02fe74e2c6ada24d341cd3d2fdfb75
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49932925"
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
擷取此屬性相關聯的字串，並將它儲存在使用者提供的緩衝區。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetStringChars(  
   ULONG  buflen,  
   WCHAR* rgString,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetStringChars(  
   uint       buflen,   
   out string rgString,   
   out uint   pceltFetched  
);  
```  
  
#### <a name="parameters"></a>參數  
 `buflen`  
 [in]使用者提供的緩衝區可容納的字元數上限。  
  
 `rgString`  
 [out]傳回的字串。  
  
 [只有 c + +]`rgString`接收之字串的 Unicode 字元的緩衝區的指標。 這個緩衝區必須至少是`buflen`字元 （而不是個位元組） 的大小。  
  
 `pceltFetched`  
 [out]傳回的實際儲存在緩衝區中的字元數的位置。 (可以是`NULL`c + + 中。)  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則會傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 在 c + +，必須小心以確保至少是緩衝區`buflen`長度 Unicode 字元。 請注意，Unicode 字元長的 2 個位元組。  
  
> [!NOTE]
>  在 c + +，傳回的字串不包含結束的 null 字元。 如果指定的話，`pceltFetched`會在字串中指定的字元數。  
  
## <a name="example"></a>範例  
 
```cpp  
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)  
{  
    CStringW returnString = L"";  
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;  
    If (pProp3 != NULL) {  
        ULONG dwStrLen = 0;  
        HRESULT hr;  
        hr = pProp3->GetStringCharLength(&dwStrLen);  
        if (SUCCEEDED(hr) && dwStrLen > 0) {  
            ULONG dwRead;  
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);  
            hr = pProp3->GetStringChars(dwStrLen,  
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),  
                                        &dwRead);  
        }  
    }  
    return(returnString);
}
```    
  
## <a name="see-also"></a>另請參閱  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)