---
title: "byteOffset 屬性 (Int8Array) | Microsoft Docs"
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
ms.assetid: b155bf97-d567-4921-8edd-dbca0d84b6cf
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# byteOffset 屬性 (Int8Array)
唯讀。  這個陣列從其 ArrayBuffer 開頭起算的位移 \(以位元組為單位\)，在建構階段位移都不會改變。  
  
## 語法  
  
```javascript  
var arrayOffset = int8Array.byteOffset;  
```  
  
## 範例  
 下列範例會示範如何取得陣列的位移。  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            alert(intArr.byteOffset);  
        }  
    }  
  
```  
  
## 需求  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]