---
title: 在 偵錯工具中建立資料的自訂檢視 |Microsoft Docs
ms.custom: ''
ms.date: 11/20/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59e6c1879d5463682ee41d60e3928fce85c74a8d
ms.sourcegitcommit: 81e9d90843ead658bc73b30c869f25921d99e116
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2018
ms.locfileid: "52305139"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>在 Visual Studio 偵錯工具中建立資料的自訂檢視
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]偵錯工具會提供許多工具，可檢查及修改程式狀態。 這些工具大多數只能在中斷模式下運作。

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>在變數視窗和 DataTips 中建立資料的自訂檢視
 許多[偵錯工具視窗](../debugger/debugger-windows.md)，例如**自動變數**並**監看式**windows 中，可讓您檢查變數。 您可以自訂原生類型，受管理的物件，和您自己的類型會顯示在偵錯工具變數視窗中，以及在[DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md)。 如需詳細資訊，請參閱 <<c0> [ 建立原生物件的自訂檢視](../debugger/create-custom-views-of-native-objects.md)並[建立受管理物件的自訂檢視](../debugger/create-custom-views-of-dot-managed-objects.md)。
  
## <a name="create-custom-visualizers"></a>建立自訂視覺化檢視  
 視覺化檢視可讓您檢視物件或變數的內容中有意義的方式。 在 Visual Studio 偵錯工具視覺化檢視是指不同的視窗，您可以開啟使用放大鏡![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "視覺化檢視圖示")圖示。 例如，HTML 視覺化檢視會顯示會如何解譯及顯示在瀏覽器的 HTML 字串。 您可以從資料提示方塊、 存取視覺化工具**監看式** 視窗中，**自動變數**視窗中，而**區域變數**視窗。 **快速監看式**對話方塊也會提供視覺化檢視。 如需詳細資訊，請參閱[建立自訂視覺化檢視](../debugger/create-custom-visualizers-of-data.md)。
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具基礎](../debugger/getting-started-with-the-debugger.md)   
 [命令視窗](../ide/reference/command-window.md)   
 [偵錯工具安全性](../debugger/debugger-security.md)