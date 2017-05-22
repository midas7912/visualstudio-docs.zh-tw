---
title: "constructor 屬性 (WeakMap) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 1e3f9333-ce75-4d32-9b14-fbe81fd73dfb
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# constructor 屬性 (WeakMap)
指定用來建立 `WeakMap` 物件的函式。  
  
## 語法  
  
```javascript  
weakmap.constructor  
```  
  
## 備註  
 必要的 `weakmap` 是 `WeakMap` 物件的名稱。  
  
 `constructor` 屬性為每個具有原型之物件的原型成員。  其中包括所有內建 JavaScript 物件，但是 `Global` 和 `Math` 物件除外。  `constructor` 屬性包含建構該特殊物件之執行個體的函式參考。  
  
## 需求  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]