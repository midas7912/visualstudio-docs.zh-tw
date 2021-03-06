---
title: 操作功能表 （XML 結構描述總管） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42ab17ca-b8c1-40d7-beda-d033f66fe874
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 854ea473f2f606b28052b093978253372b4fec59
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2018
ms.locfileid: "49294609"
---
# <a name="context-menus-xml-schema-explorer"></a>操作功能表 (XML 結構描述總管)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
下列操作功能表項目用於執行結構描述特定搜尋和其他作業。  
  
## <a name="node-type-schema-set"></a>節點型別：結構描述設定  
 下表描述結構描述集節點可用的選項。  
  
|選項|描述|  
|------------|-----------------|  
|**顯示最可能的根項目**|尋找並反白顯示除了本身以外沒有其他全域項目參考的所有全域項目。|  
|**顯示全域型別**|尋找並反白顯示結構描述集中的所有全域型別。|  
|**顯示全域項目**|尋找並反白顯示結構描述集中的所有全域項目。|  
|**屬性視窗**|會開啟**屬性**視窗 （如果它尚未開啟）。 這個視窗會顯示與節點有關的資訊。|  
  
## <a name="node-type-namespace"></a>節點型別：命名空間  
 下表描述命名空間節點可用的選項。  
  
|選項|描述|  
|------------|-----------------|  
|**顯示所有對內的參考**|尋找並反白顯示匯入選取之命名空間的檔案。|  
|**顯示所有對外參考**|針對選取之命名空間內的每個檔案，尋找並反白顯示下列項目：<br /><br /> -所有中參考的命名空間匯入陳述式，而不需要`schemaLocation`屬性。<br />-所有檔案中指定的選取一個以外的命名空間中`schemaLocation`中匯入的屬性和 include 陳述式。|  
|**顯示全域型別**|尋找並反白顯示所選命名空間中的所有全域型別。|  
|**顯示全域項目**|尋找並反白顯示所選命名空間中的所有全域項目。|  
|**屬性視窗**|會開啟**屬性**視窗 （如果它尚未開啟）。 這個視窗會顯示與節點有關的資訊。|  
  
## <a name="node-type-file"></a>節點型別：檔案  
 下表描述檔案節點可用的選項。  
  
|選項|描述|  
|------------|-----------------|  
|**顯示所有對內的參考**|尋找並反白顯示在 include 和 import 陳述式之 `schemaLocation` 屬性中指定選取檔案的所有檔案。|  
|**顯示所有對外參考**|尋找並反白顯示下列項目：<br /><br /> -所有命名空間中的所有命名空間屬性指定匯入陳述式沒有`schemaLocation`屬性。<br />-所有檔案中指定`schemaLocation`屬性之所有 import 和 include 陳述式。|  
|**顯示全域型別**|尋找並反白顯示此檔案中的所有全域型別。|  
|**顯示全域項目**|尋找並反白顯示此檔案中的所有全域項目。|  
|**檢視程式碼**|在 XML 編輯器中開啟包含所選節點的檔案。 在 XML 結構描述總管中選取的項目也會在 XML 編輯器中選取。|  
|**屬性視窗**|會開啟**屬性**視窗 （如果它尚未開啟）。 這個視窗會顯示與節點有關的資訊。|  
  
## <a name="all-global-node-types"></a>所有全域節點型別  
 下表描述所有全域節點可用的選項。  
  
|選項|描述|  
|------------|-----------------|  
|**在 [圖形] 檢視中顯示**|開啟圖表檢視。 如果所選的節點不在工作空間中，請將其加入至工作空間並選取該節點。|  
|**在內容模型檢視中顯示**|開啟內容模型檢視。 如果所選的節點不在工作空間中，請將其加入至工作空間並選取該節點。|  
|**檢視程式碼**|在 XML 編輯器中開啟包含所選節點的檔案。 在 XML 結構描述總管中選取的項目也會在 XML 編輯器中選取。|  
|**屬性視窗**|會開啟**屬性**視窗 （如果它尚未開啟）。 這個視窗會顯示與節點有關的資訊。|  
  
## <a name="node-type-element"></a>節點型別：項目  
 除了上述的全域節點選項外，項目節點的內容功能表還包含下列選項：  
  
|選項|描述|  
|------------|-----------------|  
|**移至型別定義**|瀏覽至選取之項目的型別定義。 當用於此項目的型別是全域型別時，這個選項就會適用。|  
|**請移至原始項目**|針對項目參考，瀏覽至此項目的實際定義。|  
|**顯示所有參考**|針對全域項目，尋找並反白顯示所選項目的所有參考 (具有 `ref="selectedElement"` 的項目)。|  
|**顯示替代群組的成員**|針對替代群組的標頭，尋找並反白顯示選取之項目屬於其成員之替代群組的成員的所有項目。 這個選項會顯示直接和間接參與者。|  
|**顯示替代群組標頭**|針對屬於替代群組之成員的全域項目，尋找並反白顯示選取之項目的所有直接和間接標頭，例如下列項目：<br /><br /> 為選取的項目上指定替代群組標頭。<br />為在其標頭項目上指定替代群組標頭。|  
|**產生範例 XML**|僅適用於全域項目。 針對全域項目產生範例 XML 檔案。|  
  
## <a name="node-type-global-types"></a>節點型別：全域型別  
 除了上述的全域節點選項外，全域型別節點的內容功能表還有下列選項：  
  
|選項|描述|  
|------------|-----------------|  
|**顯示基底類型**|如果選取的型別衍生自全域型別，就會瀏覽至選取之型別的基底型別。|  
|**顯示所有參考**|尋找並反白顯示選取之型別的所有參考。 這包括選取的型別以及衍生自選取型別之型別的項目和屬性。|  
|**顯示所有衍生型別**|尋找並反白顯示直接和間接衍生自選取之型別的所有型別。|  
|**顯示所有祖系**|顯示所有父 (基底) 型別。|  
  
## <a name="node-type-attribute"></a>節點型別：屬性  
 除了上述的全域節點選項外，屬性節點的內容功能表還有下列選項：  
  
|選項|描述|  
|------------|-----------------|  
|**移至型別定義**|當用於屬性的型別是全域型別時，就會瀏覽至選取之屬性的型別定義。|  
|**請移至原始屬性**|針對屬性參考，瀏覽至此屬性的實際定義。|  
|**顯示所有參考**|針對全域屬性，尋找並反白顯示所選屬性的所有參考 (其他具有 `ref="selectedAttribute"` 的屬性)。|  
  
## <a name="node-type-attribute-group"></a>節點型別：屬性群組  
 除了上述的全域節點選項外，屬性群組節點的內容功能表還包含下列選項：  
  
|選項|描述|  
|------------|-----------------|  
|**移至定義**|針對參考，瀏覽至此屬性的實際定義。|  
|**顯示所有成員**|尋找並反白顯示屬性群組的所有成員。|  
|**顯示所有參考**|尋找並反白顯示所選屬性群組的所有參考 (具有 `ref="selectedAttributeGroup"` 的屬性群組)。|  
  
## <a name="node-type-named-group"></a>節點型別：具名群組  
 除了上述的全域節點選項外，具名群組節點的內容功能表還包含下列選項：  
  
|選項|描述|  
|------------|-----------------|  
|**移至定義**|針對參考，瀏覽至此屬性的實際定義。|  
|**顯示所有成員**|尋找並反白顯示具名群組的所有成員。|  
|**顯示所有參考**|尋找並反白顯示所選群組的所有參考 (具有 `ref="selectedGroup"` 的群組)。|  
  
## <a name="see-also"></a>另請參閱  
 [XML 結構描述總管](../xml-tools/xml-schema-explorer.md)   
 [搜尋結構描述集合](../xml-tools/searching-the-schema-set.md)



