---
title: "setFloat64 方法 (DataView) | Microsoft Docs"
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
ms.assetid: 63d2c631-876f-4d4b-b3b6-62b0aaffe6c5
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# setFloat64 方法 (DataView)
在從檢視開始算起的指定位元組位移處設定 Float64 值。  您可以在任何位移處設定多位元組的值，沒有任何對齊條件約束。  
  
## 語法  
  
```  
dataView.setFloat64 (byteOffset, value, littleEndian);   
```  
  
## 參數  
 `byteOffset`  
 應該在緩衝區中擷取之值的位置。  
  
 `value`  
 要設定的值。  
  
 `littleEndian`  
 選擇項。  如果是 false 或未定義，就會寫入位元組由大到小的值，否則會寫入位元組由小到大的值。  
  
## 備註  
 如果這些方法寫入的位置超過檢視的結尾，就會引發例外狀況。  
  
## 範例  
 下列範例示範如何在 DataView 中設定第一個 Float64。  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setFloat64(0, 9.1);  
        }  
    }  
  
```  
  
## 需求  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]