---
title: "IMachineDebugManagerCookie::EnumApplications | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IMachineDebugManagerCookie.EnumApplications
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IMachineDebugManagerCookie::EnumApplications"
ms.assetid: 03f863cf-fa7f-4ec4-b1a1-1ae0ad296c39
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IMachineDebugManagerCookie::EnumApplications
傳回正在執行的應用程式目前清單的列舉值。  
  
## 語法  
  
```  
HRESULT EnumApplications(  
   IEnumRemoteDebugApplications**  ppeda  
);  
```  
  
#### 參數  
 `ppeda`  
 \[in\] 包含後續應用程式目前清單的列舉值。  
  
## 傳回值  
 方法會傳回 `HRESULT`。  可能的值包括，，但不限於\)，這些在下表中。  
  
|值|描述|  
|-------|--------|  
|`S_OK`|方法成功。|  
  
## 備註  
 這個方法傳回執行的應用程式目前清單的列舉值。  偵錯工具 IDE 使用這個方法會顯示和其他應用程式進行偵錯。  
  
## 請參閱  
 [IMachineDebugManagerCookie 介面](../../winscript/reference/imachinedebugmanagercookie-interface.md)