---
title: 屬性&lt;屬性名稱&gt;無法刪除，因為它正參與關聯&lt;關聯名稱&gt;|Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cdd2c2ab26709a017801e8ae34e4ee6f2223c2c3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49177732"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>屬性&lt;屬性名稱&gt;無法刪除，因為它正參與關聯&lt;關聯名稱&gt;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
選取的屬性設定為**關聯屬性**錯誤訊息中所指出的類別之間的關聯。 如果屬性已參與資料類別之間的關聯，就無法刪除屬性。  
  
 設定**關聯屬性**不同的屬性，可以成功刪除要刪的屬性資料類別。  
  
### <a name="to-correct-this-error"></a>更正這個錯誤  
  
1.  在 O/R Designer 上，選取在錯誤訊息指出的資料類別之間連接的關聯線。  
  
2.  若要開啟的該行上按兩下**關聯編輯器** 對話方塊。  
  
3.  從中移除屬性**關聯屬性**。  
  
4.  試著再次刪除屬性。  
  
## <a name="see-also"></a>另請參閱  
 [LINQ to SQL 工具，在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [如何： 建立 LINQ to SQL 類別 （O/R 設計工具） 之間的關聯 （關聯性）](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [逐步解說： 建立 LINQ to SQL 類別 （O-R 設計工具）](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)

