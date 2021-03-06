---
title: 錯誤： Web 伺服器找不到要求的資源 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8769c84237d877f02b7c9d3d02c6391f9e955ff3
ms.sourcegitcommit: 40b6438b5acd7e59337a382c39ec711b9e99cc8a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2018
ms.locfileid: "49100974"
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>錯誤：Web 伺服器找不到要求的資源
基於安全性考量，IIS 已傳回泛型錯誤。  

原因可能是伺服器的安全性組態。 IIS 6.0 (含) 以前版本中使用了一個稱為 URLScan 的附加元件程式，用於篩選出可疑和格式錯誤的要求。 IIS 7.0 內建了要求篩選功能，可達到相同的目的。 在這兩種情況下，太過嚴格的要求篩選可能會阻止 Visual Studio 對伺服器進行偵錯。  

此錯誤的另一個可能的原因是，IIS 的 W3SVC 服務未啟動。 請確認此服務已啟動 （灰色） 在 [服務] 視窗中 (*services.msc*)。

有許多其他的可能原因，此錯誤。 其中幾個最常見的原因包括 IIS 的安裝或組態、網站組態或檔案系統的權限發生問題。 您可以嘗試使用瀏覽器存取資源。 根據 IIS 的設定方式，您可能必須使用伺服器上的本機瀏覽器，或檢查 IIS 錯誤記錄檔，以取得詳細的錯誤訊息。  
  
 如需有關 IIS 疑難排解的詳細資訊，請參閱 < [IIS 管理](/iis/manage/provisioning-and-managing-iis/iis-management-and-administration)。  
  
## <a name="see-also"></a>另請參閱  
 [錯誤：Web 伺服器已經鎖定，並會封鎖 DEBUG 動詞命令](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)