---
title: 如何： 列印時隱藏工作表的控制項
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- controls [Office development in Visual Studio], hiding while printing
- printing [Office development in Visual Studio], hiding controls
- worksheets, hiding controls when printing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e240f4b4be5ce4092705615f060f4e0ef0076e3a
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254470"
---
# <a name="how-to-hide-controls-on-worksheets-when-printing"></a>如何： 列印時隱藏工作表的控制項
  當您列印 Windows Form 控制項的 Microsoft Office Excel 文件時，控制項也會顯示在列印的工作表上。 列印工作表時，您可以隱藏控制項。  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  如果您隱藏控制項，顯示資料，例如<xref:Microsoft.Office.Tools.Excel.Controls.TextBox>，控制項中的資料將不會顯示在列印的工作表上。  
  
> [!NOTE]  
>  在下列指示的某些 Visual Studio 使用者介面項目中，您的電腦可能會顯示不同的名稱或位置。 您所擁有的 Visual Studio 版本以及使用的設定會決定這些項目。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](../ide/personalizing-the-visual-studio-ide.md)。  
  
## <a name="to-hide-controls-when-a-worksheet-is-printed"></a>若要隱藏工作表時的控制項列印  
  
1.  建立或在 Visual Studio 中開啟 Excel 專案並確認**Sheet1**會顯示在設計工具。 如需建立專案資訊，請參閱 <<c0> [ 如何： 在 Visual Studio 中的建立 Office 專案](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
2.  從**通用控制項**索引標籤**工具箱**，拖曳<xref:Microsoft.Office.Tools.Excel.Controls.Button>控制的儲存格上`Sheet1`。  
  
3.  在 **屬性**視窗中，將<xref:Microsoft.Office.Tools.Excel.Controls.Button.PrintObject%2A>屬性設**False**。  
  
## <a name="see-also"></a>另請參閱  
 [Office 文件上的控制項](../vsto/controls-on-office-documents.md)   
 [在 Office 文件概觀上的 Windows Form 控制項](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [如何： 將 Windows Form 控制項加入 Office 文件](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [如何： 在工作表儲存格內的控制項重新調整大小](../vsto/how-to-resize-controls-within-worksheet-cells.md)  
  
  