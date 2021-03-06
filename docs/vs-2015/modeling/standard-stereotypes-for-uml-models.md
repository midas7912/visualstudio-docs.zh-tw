---
title: UML 模型的標準造型 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML, stereotypes
- UML diagrams, stereotypes
ms.assetid: 8a8c2321-1cae-4ba8-bb9e-23495c3404d8
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1fcc876a847429c0de9600a5a727b19334819119
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51763234"
---
# <a name="standard-stereotypes-for-uml-models"></a>UML 模型的標準造型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以將造型加入 UML 模型項目，以提供其他資訊給讀取器或電腦處理。 造型在設定檔中定義，且每個設定檔會提供一組造型。 有些設定檔隨 Visual Studio 提供。 您也可以定義自己的設定檔來自己的造型。 如需詳細資訊，請參閱 <<c0> [ 定義要擴充 UML 的設定檔](../modeling/define-a-profile-to-extend-uml.md)。  
  
 若要查看哪些 Visual Studio 版本支援這項功能，請參閱 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。  
  
## <a name="the-standard-profiles"></a>標準設定檔  
 下列設定檔可在支援的 Visual Studio 版本中，您可能已安裝在您安裝。  
  
|設定檔|用途|  
|-------------|-------------|  
|[UML 標準設定檔 L2](#L2)|一組標準造型，可以用來加入項目或關聯性的額外相關資訊。|  
|[UML 標準設定檔 L3](#L3)|一組標準造型，可以用來加入項目或關聯性的額外相關資訊。|  
|[C# 設定檔](#NetProfile)|如果您想要以一個類別或 UML 模型中的其他項目代表程式碼，可以套用 C# 設定檔的其中一個造型來表示。<br /><br /> 這些造型也會將屬性加入模型項目。|  
  
 當您建立新的 UML 模型時，除非您移除連結，否則 UML 標準設定檔 L2 和 L3 會連結到模型。  
  
 若要使用這些設定檔中的造型，您必須先將設定檔連結到套件或模型來包含要套用至模型的項目。  
  
#### <a name="to-link-a-profile-to-a-model-or-a-package"></a>將設定檔連結至模型或套件  
  
1.  開啟**UML 模型總管**。 在 [**架構**功能表上，指向**Windows**，然後按一下**UML 模型總管]**。  
  
2.  找出套件或模型，其中包含您想要在設定檔中套用造型的所有項目。  
  
3.  以滑鼠右鍵按一下封裝或模型，然後按一下**屬性**。  
  
4.  在 **屬性**視窗中，將**設定檔**屬性，以您想要的設定檔。  
  
#### <a name="to-remove-the-link-between-a-profile-and-a-model-or-package"></a>移除設定檔與模型或套件之間的連結  
  
1.  在 UML 模型總管 中，模型或套件上按一下滑鼠右鍵，然後按一下**屬性**。  
  
2.  在 [屬性] 視窗中，設定**設定檔**屬性為空白。  
  
    > [!NOTE]
    >  只有當所有模型或套件中的項目都未使用該設定檔造型，才能取消設定檔的連結。  
  
#### <a name="to-apply-a-stereotype-to-a-model-element"></a>將造型套用至模型項目  
  
1.  以滑鼠右鍵按一下模型項目在圖表上或在**UML 模型總管**，然後按一下**屬性**。  
  
2.  按一下 **造型**屬性，並選取您想要套用的造型。  
  
     對大部分種類的項目而言，所選造型會顯示在模型項目的 «＞ 形箭號» 中。  
  
    > [!NOTE]
    >  如果您看**造型**屬性，或如果您想要的造型未出現，請確認模型項目位於套件或模型，適當的設定檔連結。  
  
3.  有些造型可讓您設定模型項目其他屬性的值。 若要查看這些屬性，依序展開**造型**屬性。  
  
###  <a name="L2"></a> UML 標準設定檔 L2  
 下列造型可以用來特製化的 UML 模型項目的意義，除非設定檔的連結從模型中移除。  
  
 這些造型的確切意義是由您自己的本機慣例以及您可能會用來處理模型的任何工具來判斷。  
  
|造型|適用於|意義|  
|----------------|----------------|-------------|  
|輔助|類別|支援另一個類別的類別，通常是藉由實作額外的邏輯來支援。 其他類別可能具有 «焦點» 造型。|  
|call|相依性|用戶端類別會呼叫供應商的作業。|  
|建立|相依性|用戶端類別會建立供應商的執行個體。|  
|建立|訊息|傳送者會建立接收器。|  
|建立|運算|這項作業是建構函式。|  
|衍生|相依性|用戶端項目是由供應商完整或部分計算。|  
|終結|運算|作業會終結其執行個體。|  
|文件|成品|不是來源或不是可執行檔的 «檔案»。|  
|實體|元件|此元件代表商務概念。|  
|可執行檔|成品|可執行檔 «檔案»。|  
|檔案|成品|實體檔案。|  
|焦點|類別|定義核心商務邏輯的類別，由數個 «輔助» 類別支援。|  
|架構|Package|此套件會定義可重複使用的設計模式。|  
|實作|元件|«規格» 的實作。|  
|implementationClass|類別|此類別描述實作，並且每個執行階段執行個體都有一個固定的實作類別。 與 «類型» 對照。|  
|執行個體化|相依性|用戶端會建立供應商的執行個體。|  
|程式庫|成品|程式庫 «檔案»。|  
|metaclass|類別|此類別的執行個體也是類別。|  
|modelLibrary|Package|包含以匯入套件方式要重複使用的模型項目。 通常定義為設定檔，並且由設定檔的應用程式自動匯入。|  
|處理序|元件|以交易為基礎的元件，或攜帶執行緒的元件。|  
|實現|類別、介面、元件|描述實作。|  
|精簡|相依性|用戶端類別、元件或套件提供比供應商更多的規格或設計詳細資訊。|  
|責任|相依性|位於相依性之供應商結尾的註解會定義用戶端類別或元件的責任。|  
|指令碼|成品|可解譯 «檔案»。|  
|傳送|相依性|來源作業會傳送目標信號。|  
|服務|元件|無狀態的元件。|  
|來源|成品|可編譯 «檔案»。|  
|規格|類別、介面、元件|定義元件的行為或物件，而不定義內部運作方式。|  
|子系統|元件|大型系統的一部分。 使用案例圖表上的子系統是具備子系統造型的元件。|  
|追蹤|相依性|此用戶端項目是實現供應商之設計的一部分。 這種相依性的兩端通常位在不同的模型中。 其中一個模型是其他模型的實現。|  
|類型|類別|指定物件的行為，而不陳述實作的方式。 物件如果符合規格，則會是類型的成員。|  
|utility|類別|靜態函式的集合 此類別沒有執行個體。|  
  
###  <a name="L3"></a> UML 標準設定檔 L3  
 下列造型可以用來特製化 UML 模型項目的意義，除非設定檔的連結從模型取消。  
  
 這些造型的確切意義是由您自己的本機慣例以及您可能會用來處理模型的任何工具來判斷。  
  
|造型|適用於|描述|  
|----------------|----------------|-----------------|  
|buildComponent|元件|用來定義組建的元素集合。|  
|metamodel|模型|定義模型語言 (例如 UML 的變數) 或網域的特定語言。|  
|systemModel|模型|一個模型，是套用至相同系統之模型的集合，例如規格、實現和兩者之間的追蹤關聯性。|  
  
##  <a name="NetProfile"></a> C# 設定檔  
 在此設定檔中定義的造型，可讓您表示模型項目是用於轉譯成程式碼。 每個造型都會定義您可以在模型項目設定的其他屬性。  
  
 若要讓這些造型可用，請將模型或套件連結到 C# 設定檔。 然後，您就可以將造型套用至該模型或套件中的模型項目。  
  
 可用造型、它們所套用至的項目以及變成可用的其他屬性，都摘要在下列資料表中。  
  
|造型|適用於|屬性|  
|----------------|----------------|----------------|  
|**C# 類別**|UML 類別<br /><br /> 元件|**Clr 屬性**<br /><br /> **是部分**<br /><br /> **是密封格式，**<br /><br /> **為靜態**<br /><br /> **不安全**<br /><br /> **封裝可視性**|  
|**C# 結構**|UML 類別<br /><br /> 元件|**Clr 屬性**<br /><br /> **是部分**<br /><br /> **不安全**<br /><br /> **封裝可視性**|  
|**C# 全域成員**|UML 類別<br /><br /> 元件|**Clr 屬性**|  
|**C# 介面**|UML 介面|**Clr 屬性**<br /><br /> **是部分**<br /><br /> **封裝可視性**|  
|**C# 列舉**|UML 列舉|**ClrAttributes**<br /><br /> **基底型別**|  
|**C# 命名空間**|UML 套件|**Clr 屬性**<br /><br /> **基底名稱**<br /><br /> **使用命名空間**|  
  
## <a name="see-also"></a>另請參閱  
 [將造型加入 UML 模型項目](../modeling/add-stereotypes-to-uml-model-elements.md)   
 [自訂您的模型，使用設定檔和造型](../modeling/customize-your-model-with-profiles-and-stereotypes.md)   
 [定義要擴充 UML 的設定檔](../modeling/define-a-profile-to-extend-uml.md)



