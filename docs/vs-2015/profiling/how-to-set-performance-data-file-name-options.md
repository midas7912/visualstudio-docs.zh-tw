---
title: 如何：設定效能資料檔案名稱選項 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19a29c143ecc2ce413e6f6480b2c49e52277af3f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47489218"
---
# <a name="how-to-set-performance-data-file-name-options"></a>如何：設定效能資料檔案名稱選項
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 設定效能資料檔案名稱選項](https://docs.microsoft.com/visualstudio/profiling/how-to-set-performance-data-file-name-options)。  
  
根據預設，您要使用下列語法來儲存程式碼剖析資料 (.vsp) 檔案：  
  
 *Path\VSP-File\YYMMDD(N)* **.vsp**  
  
 您可以在效能工作階段中屬性對話方塊的 [一般] 頁面上，變更任何命名參數。  
  
 **需求**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
|||  
|-|-|  
|*路徑*|包含報告的目錄。 預設位置是方案資料夾，或是使用者專案及方案的預設位置。|  
|*VSP-File*|程式碼剖析資料檔案的名稱。 預設的名稱是經過程式碼剖析的方案或可執行檔的名稱。|  
|*YYMMDD*|日期戳記，顯示收集程式碼剖析資料的年、月、日。|  
|*(N)*|如果有一個以上程式碼剖析資料檔案，則檔名會加入括號和遞增數字。|  
  
### <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>變更效能工作階段之程式碼剖析資料檔案的命名語法  
  
1.  在 [效能總管] 中，以滑鼠右鍵按一下效能工作階段的名稱，然後按一下 [屬性]。  
  
2.  按一下 [一般]。  
  
3.  變更 [報告] 中的下列設定：  
  
    |||  
    |-|-|  
    |**報告位置**|指定儲存程式碼剖析資料檔案的目錄。|  
    |**報告名稱**|指定檔案的基底名稱。|  
    |**自動將新報告加入至工作階段**|選取此核取方塊以自動將資料檔案加入至效能工作階段。|  
    |**將累加號碼附加至產生的報告**|當一個以上的檔案使用相同的名稱時，選取此核取方塊以將累加號碼加入至檔案名稱。 清除核取方塊，以覆寫現有的檔案。|  
    |**號碼使用時間戳記**|選取核取方塊以新增時間戳記至檔案名稱。|


