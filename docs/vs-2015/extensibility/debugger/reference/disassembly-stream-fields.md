---
title: DISASSEMBLY_STREAM_FIELDS |Microsoft Docs
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
- DISASSEMBLY_STREAM_FIELDS
helpviewer_keywords:
- DISASSEMBLY_STREAM_FIELDS enumeration
ms.assetid: cfc9b4de-c756-4844-bea7-d9f186a51d1b
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d65c51f1589d245ab0fcbbfe8c62d77277d925ee
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51775793"
---
# <a name="disassemblystreamfields"></a>DISASSEMBLY_STREAM_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定要擷取反組譯碼欄位的相關資訊。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
typedef DWORD DISASSEMBLY_STREAM_FIELDS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
```  
  
## <a name="members"></a>成員  
 DSF_ADDRESS  
 初始化/使用`bstrAddress`欄位。  
  
 DSF_ADDRESSOFFSET  
 初始化/使用`bstrAddressOffset`欄位。  
  
 DSF_CODEBYTES  
 初始化/使用`bstrCodeBytes`欄位。  
  
 DSF_OPCODE  
 初始化/使用`bstrOpCode`欄位。  
  
 DSF_OPERANDS  
 初始化/使用`bstrOperands`欄位。  
  
 DSF_SYMBOL  
 初始化/使用`bstrSymbol`欄位。  
  
 DSF_CODELOCATIONID  
 初始化/使用`uCodeLocationId`欄位。  
  
 DSF_POSITION  
 初始化/使用`posBeg`和`posEnd`欄位。  
  
 DSF_DOCUMENTURL  
 初始化/使用`bstrDocumentUrl`欄位。  
  
 DSF_BYTEOFFSET  
 初始化/使用`dwByteOffset`欄位。  
  
 DSF_FLAGS  
 初始化/使用`dwFlags`([DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)) 欄位。  
  
 DSF_OPERANDS_SYMBOLS  
 包含符號名稱，在`bstrOperands`欄位。  
  
 DSF_ALL  
 指定反組譯碼資料流的所有欄位。  
  
## <a name="remarks"></a>備註  
 做為參數傳遞[讀取](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)方法，以表示哪些欄位[DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)結構會進行初始化。  
  
 用於`dwFields`隸屬`DisassemblyData`表示哪些欄位是使用和有效時，會傳回這個結構的結構。  
  
 這些值可能會合併的位元`OR`。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [讀取](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)

