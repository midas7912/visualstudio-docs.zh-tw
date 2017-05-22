---
title: "prototype 屬性 (Map) | Microsoft Docs"
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
ms.assetid: c7b429cb-97b7-400e-a214-1b18bddd6b02
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# prototype 屬性 (Map)
傳回對應的原型參考。  
  
## 語法  
  
```javascript  
map.prototype  
```  
  
## 備註  
 `map` 引數是對應的名稱。  
  
 使用 `prototype` 屬性 \(Property\)，將基本功能組提供給某一物件類別。  該物件的新執行個體會「繼承」指定給該物件的原型行為。  
  
 例如，若要將方法加入至 `Map` 物件 \(此方法會傳回集合最大項目的值\)，請宣告函式，並將它加入至 `Map.prototype`，然後使用它。  
  
## 需求  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]