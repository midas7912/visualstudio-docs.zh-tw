---
title: Creating an Extension with 工具視窗 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: afa24a7faceade36cf6b3d19c7e86fb8d6676ba8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47486339"
---
# <a name="creating-an-extension-with-a-tool-window"></a>使用工具視窗建立延伸模組
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[工具視窗建立擴充](https://docs.microsoft.com/visualstudio/extensibility/creating-an-extension-with-a-tool-window)。  
  
在此程序中，了解如何使用 VSIX 專案範本並**自訂工具視窗**建立工具視窗的延伸模組的項目範本。  
  
## <a name="prerequisites"></a>必要條件  
 從 Visual Studio 2015 中，從下載中心取得未安裝 Visual Studio SDK。 包含為 Visual Studio 安裝程式的選用功能。 您也可以在稍後安裝 VS SDK。 如需詳細資訊，請參閱 <<c0> [ 安裝 Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md)。  
  
### <a name="creating-a-tool-window"></a>建立工具視窗  
  
1.  建立 VSIX 專案，名為**FirstWindow**。 您可以找到在 VSIX 專案範本**新的專案**下方的對話方塊**Visual C# / 擴充性**。  
  
2.  當專案開啟時，新增名為的工具視窗項目範本**FirstWindow**。 在 **方案總管**，以滑鼠右鍵按一下專案節點，然後選取**新增 / 新項目**。 在 **加入新項目**對話方塊中，移至**Visual C# / 擴充性**，然後選取**自訂工具視窗**。 在 **名稱**在視窗底部的欄位、 變更工具視窗的檔案名稱，以**FirstWindow.cs**。  
  
3.  建置此專案並開始偵錯。  
  
     Visual Studio 的實驗執行個體隨即出現。 如需詳細的實驗執行個體的詳細資訊，請參閱[實驗的執行個體](../extensibility/the-experimental-instance.md)。  
  
4.  在實驗執行個體中，移至**檢視 / 其他 Windows**。  
  
     您應該會看到的功能表項目**FirstWindow**。 按一下它。  
  
     您應該會看到工具視窗的標題**FirstWindow**和一個按鈕，指出**Click Me ！。**
