---
title: 錯誤： 使用者無法執行預存程序 sp_enable_sql_debug |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.sqlde_accessdenied
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 795dcb07459318326085d5e1fe99554d9c8d1311
ms.sourcegitcommit: bc43970c000f07c9cc2051f1264a9742943a9755
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "51349500"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>錯誤：使用者無法執行預存程序 sp_enable_sql_debug
預存程序 sp_enable_sql_debug 無法在伺服器上執行。 可能的原因如下：  
  
- 連接問題。 您需要穩定的連接到伺服器。  
  
- 沒有必要的伺服器使用權限。 若要在 SQL Server 2005 上進行偵錯，執行 Visual Studio 的帳戶和用來連接至 SQL Server 的帳戶都必須是系統管理員角色的成員。 用來連接至 SQL Server 的帳戶就是您的 Windows 使用者帳戶 (如果您使用 Windows 驗證)，或具有使用者 ID 和密碼的帳戶 (如果您使用 SQL 驗證)。  
  
  如需詳細資訊，請參閱 <<c0> [ 如何： 設定 SQL Server 權限進行偵錯](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)。  
  
## <a name="see-also"></a>另請參閱  
 [如何： 設定 SQL Server 權限偵錯](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [設定 SQL 偵錯](/previous-versions/visualstudio/visual-studio-2010/s4sszxst\(v\=vs.100\))