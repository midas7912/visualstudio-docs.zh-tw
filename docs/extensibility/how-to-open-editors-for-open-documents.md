---
title: 如何： 開啟編輯器開啟的文件 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], opening for open documents
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 05e91dd296958e44d0c06f2b77d410efdd71fb1c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49823121"
---
# <a name="how-to-open-editors-for-open-documents"></a>如何： 開啟編輯器開啟的文件
開啟的文件視窗的專案之前，專案首先必須決定檔案是否已開啟另一個編輯器的文件視窗中。 檔案可以在專案特定的編輯器中，請開啟，或其中一個標準編輯器向[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。  
  
## <a name="open-a-project-specific-editor"></a>開啟專案特定編輯器  
 您可以使用下列程序來開啟專案特定的編輯器已開啟的檔案。  
  
### <a name="to-open-a-project-specific-editor-for-an-open-file"></a>若要開啟專案特定的編輯器開啟的檔案  
  
1. 呼叫 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 方法。  
  
    此呼叫會傳回指標的文件階層、 階層項目，以及視窗框架中，如果適用的話。  
  
2. 如果文件開啟時，專案必須檢查是否只有文件資料物件存在，或如果文件檢視物件也會出現。  
  
   - 如果文件檢視物件存在，此檢視會針對不同的階層或階層項目，專案會使用檢視的視窗框架指標 resurface 現有的視窗。  
  
   - 如果文件檢視物件存在，此檢視位於相同的階層和階層項目，專案可以開啟第二個檢視，如果它可以附加至基礎的文件資料物件。 否則，專案也應該使用檢視的視窗框架的指標，來 resurface 現有的視窗。  
  
   - 如果只有文件資料物件存在時，專案應該判斷是否可以使用其檢視文件資料物件。 如果相容的文件資料物件，完成步驟所述[開啟專案特定編輯器](../extensibility/how-to-open-project-specific-editors.md)。  
  
     如果文件資料物件不相容，應該會顯示錯誤，指出檔案正在使用中的使用者。 這個錯誤應該只在暫時的情況下，顯示，例如使用者正在同時編譯檔案時嘗試開啟檔案，而不使用編輯器[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]核心文字編輯器。 核心文字編輯器可以分享編譯器的文件資料物件。  
  
3. 如果文件不是開啟的因為沒有任何文件資料物件或文件檢視物件，完成中的步驟[開啟專案特定編輯器](../extensibility/how-to-open-project-specific-editors.md)。  
  
## <a name="open-a-standard-editor"></a>開啟標準編輯器  
 使用下列程序，若要開啟的檔案已存在的標準編輯器開啟。  
  
### <a name="to-open-a-standard-editor-for-an-open-file"></a>若要開啟 開啟檔案的標準編輯器  
  
1.  呼叫 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>。  
  
     這個方法會先確認，文件尚未開啟藉由呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>。 如果已開啟文件，則被 resurfaced 其編輯器視窗。  
  
2.  如果文件尚未開啟，然後完成中的步驟[如何： 開啟標準編輯器](../extensibility/how-to-open-standard-editors.md)。  
  
## <a name="see-also"></a>另請參閱  
 [開啟和儲存專案項目](../extensibility/internals/opening-and-saving-project-items.md)   
 [如何： 開啟專案特定的編輯器](../extensibility/how-to-open-project-specific-editors.md)   
 [如何： 開啟標準編輯器](../extensibility/how-to-open-standard-editors.md)
