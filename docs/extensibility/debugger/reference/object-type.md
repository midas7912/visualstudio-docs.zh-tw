---
title: OBJECT_TYPE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- OBJECT_TYPE
helpviewer_keywords:
- OBJECT_TYPE enumeration
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: eff83198e337a3f89c88663722bf34046d3d4f62
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49905736"
---
# <a name="objecttype"></a>OBJECT_TYPE
指定運算式評估工具中的物件的類型。  
  
## <a name="syntax"></a>語法  
  
```cpp  
enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
typedef DWORD OBJECT_TYPE;  
```  
  
```csharp  
public enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
```  
  
## <a name="members"></a>成員  
 OBJECT_TYPE_BOOLEAN  
 指出物件是布林值。  
  
 OBJECT_TYPE_CHAR  
 指出物件是一個字元。  
  
 OBJECT_TYPE_I1  
 指出物件是一個位元組帶正負號的整數。  
  
 OBJECT_TYPE_U1  
 指出物件是一個位元組不帶正負號的整數。  
  
 OBJECT_TYPE_I2  
 指出物件是二位元組帶正負號的整數。  
  
 OBJECT_TYPE_U2  
 指出物件是二位元組不帶正負號的整數。  
  
 OBJECT_TYPE_I4  
 指出物件是四位元組帶正負號的整數。  
  
 OBJECT_TYPE_U4  
 指出物件是四位元組不帶正負號的整數。  
  
 OBJECT_TYPE_I8  
 表示此物件是八位元組帶正負號的整數。  
  
 OBJECT_TYPE_U8  
 表示物件的八位元組不帶正負號的整數。  
  
 OBJECT_TYPE_R4  
 指出物件是四位元組浮點數。  
  
 OBJECT_TYPE_R8  
 指出物件是 8 位元組浮點數。  
  
 OBJECT_TYPE_OBJECT  
 表示物件的物件。  
  
 OBJECT_TYPE_NULL  
 表示為 NULL 的物件。  
  
 OBJECT_TYPE_CLASS  
 表示物件的類別。  
  
## <a name="remarks"></a>備註  
 作為引數[CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)並[CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)方法。  
  
## <a name="requirements"></a>需求  
 標頭： ee.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)   
 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)