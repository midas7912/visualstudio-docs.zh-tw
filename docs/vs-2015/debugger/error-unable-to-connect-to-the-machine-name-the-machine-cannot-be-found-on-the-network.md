---
title: 錯誤： 無法連接至電腦&lt;名稱&gt;。 網路上找不到這部電腦。 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8660b08adb0d925eb0f1b084673877734a47207
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733765"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>錯誤： 無法連接至電腦&lt;名稱&gt;。 網路上找不到這部電腦。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如果下列其中一種情況為 true 時，就會發生這個行為：  
  
-   與遠端電腦的連線中斷。  
  
-   在遠端電腦上的使用者帳戶已停用。  
  
-   遠端電腦上的密碼已到期。  
  
### <a name="to-resolve-this-behavior"></a>若要解決這個行為  
  
-   請確定本機電腦與遠端電腦位於相同的網路上。 方法是，使用 Microsoft Windows [檔案總管] (或 [檔案總管]) 嘗試存取遠端電腦。  
  
     -和-  
  
-   請確定已啟用您用以連接遠端電腦的使用者帳戶。  
  
     -和-  
  
-   請確定您用以連接遠端電腦的密碼是有效的，而且尚未到期。  
  
## <a name="see-also"></a>另請參閱  
 [設定裝置上的遠端工具](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [偵錯設定和準備](../debugger/debugger-settings-and-preparation.md)



