---
title: 連接字串包含具有純文字密碼的認證，而且未使用整合式的安全性 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f1ec13cab1b8c41225cb1934740b8dd3e7f59ac0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230864"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>連接字串包含具有純文字密碼的認證，並且不使用整合式安全性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
是否要將連接字串連同這些敏感資訊一起儲存到目前的 DBML 檔案和應用程式組態檔？  按 [否] 會只儲存連接字串，不會儲存敏感資訊。  
  
 使用內含敏感資訊 (含在連接字串中的密碼) 的資料連接時，可以選擇是否在將連接字串儲存至專案的 DBML 檔案和應用程式組態檔時包含敏感資訊。  
  
> [!WARNING]
>  明確設定**連接**屬性**應用程式設定**屬性設**False**會加入到 DBML 檔案的密碼。  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>若要將連接字串連同敏感資訊一起儲存到專案的應用程式設定中  
  
-   按一下 [ **是**]。  
  
     連接字串會儲存為應用程式設定。 連接字串會包含純文字的敏感資訊。 DBML 檔案不包含敏感資訊。  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>若要將連接字串儲存到專案的應用程式設定中，但不儲存敏感資訊  
  
-   按一下 [否] 。  
  
     連接字串會儲存為應用程式設定，但是不包含密碼。  
  
## <a name="see-also"></a>另請參閱  
 [LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) (Visual Studio 中的 LINQ to SQL 工具)

