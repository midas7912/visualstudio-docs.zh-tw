---
title: 如何： 更新狀態列 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b7f7d52ad8dc75f8e8bd313794b44c231522cde7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829933"
---
# <a name="how-to-update-the-status-bar"></a>如何： 更新狀態列
**狀態列**一種控制列位於底部的許多應用程式視窗，其中包含一或多個狀態的文字行或指標。  
  
## <a name="to-update-the-status-bar"></a>若要更新狀態列  
  
1.  實作<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>提供您的編輯器，例如表單檢視和程式碼檢視每個個別的檢視物件 (DocView) 上。  
  
2.  當呼叫 IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>，更新中的資訊**狀態列**藉由呼叫的方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>。  
  
    > [!NOTE]
    >  IDE 呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>只當您的文件視窗一開始啟動。 您的文件視窗是作用中的時間所剩期間內，您必須更新**狀態列**編輯器變更的狀態資訊。  
  
## <a name="robust-programming"></a>穩固程式設計  
 A**狀態列**包含四個不同的欄位：  
  
- 狀態文字  
  
- 進度列  
  
- 動畫的圖示  
  
- 編輯器的資訊  
  
  如需詳細資訊，請參閱 <<c0> [ 狀態列](/cpp/mfc/status-bars)。  
  
  IDE 會自動呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>方法的程式<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>文件視窗啟用時的實作。  
  
  VSPackage 實作器會負責更新狀態列中的狀態文字。 IDE 在 [狀態] 文字欄位設為空的文字時，會重設此字串，以 「 就緒 」 ("") 在閒置的時間。  
  
## <a name="see-also"></a>另請參閱  
 [狀態列](/cpp/mfc/status-bars)