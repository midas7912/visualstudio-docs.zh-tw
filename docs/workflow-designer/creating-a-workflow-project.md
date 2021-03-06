---
title: 建立 Workflow Foundation 專案
ms.date: 06/25/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- Workflow Designer, creating a workflow project
- creating a workflow project
ms.assetid: 235a125e-ebe7-4a98-bf77-86c8558728fb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a4f8ed1effbc459bd2a17e3433738c1b461513b
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755650"
---
# <a name="workflow-project-templates"></a>工作流程專案範本

您可以使用 Visual Studio 專案範本，來建立工作流程、 Windows Communication Foundation (WCF) 工作流程服務、 自訂活動和自訂活動設計工具。 本文說明如何使用 Visual Studio 中可用的專案範本建立程式庫和應用程式。

## <a name="create-a-workflow-project"></a>建立工作流程專案

Visual Studio 提供四個不同的工作流程專案範本：

- 工作流程主控台應用程式

- WCF 工作流程服務應用程式

- 活動程式庫

- 活動設計工具程式庫

若要存取這些範本，請先安裝**Windows Workflow Foundation**元件的 Visual Studio 2017。 如需詳細指示，請參閱 <<c0> [ 安裝的 Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation)。

1. 安裝之後**Windows Workflow Foundation**元件，開啟**新增專案**對話方塊中的選取**檔案** > **新增** > **專案**。

1. 在左側窗格中，選取**Visual C#** > **工作流程**類別目錄 (或**Visual Basic** > **工作流程**如果您偏好 Visual Basic)。

1. 在中間窗格中，選取專案範本，例如**工作流程主控台應用程式**。

1. 在 **名稱**方塊中，輸入您的專案，讓您輕鬆地識別的描述性名稱。

1. 在 **位置**方塊中，輸入您要儲存您的專案，或選取的目錄**瀏覽**來巡覽找到它。

1. 在 **解決方案**方塊中，輸入新方案的名稱。 選取 **確定**建立應用程式。

   > [!NOTE]
   > 如果您想要將新的專案新增至現有的方案，在 Visual Studio 中開啟該方案，以滑鼠右鍵按一下方案中的**方案總管**，然後選取**新增** > **新增專案**以開啟**新的專案** 對話方塊。

## <a name="workflow-console-app"></a>工作流程主控台應用程式

如果您選擇**工作流程主控台應用程式**範本，Visual Studio 會建立工作流程定義在 XAML 中。 工作流程設計工具會開啟並顯示您所建立的工作流程的畫布。 若要撰寫工作流程，拖曳活動或從其他工作流程項目**工具箱**至設計介面。

## <a name="wcf-workflow-service-app"></a>WCF 工作流程服務應用程式

如果您選擇**WCF 工作流程服務應用程式**範本，Visual Studio 會建立服務定義為 XAML。 工作流程設計工具會開啟至 [設計] 檢視與<xref:System.Activities.Statements.Sequence>活動，其中包含一組<xref:System.ServiceModel.Activities.Receive>和<xref:System.ServiceModel.Activities.SendReply>活動。

## <a name="activity-library"></a>活動程式庫

如果您選擇**活動程式庫**範本，Visual Studio 會建立活動定義在 XAML 中。 工作流程設計工具會開啟並顯示您的自訂活動的畫布。 活動拖曳**工具箱**至設計介面，以將它包含在您的自訂活動。

> [!NOTE]
> 您可以在您的自訂活動的主體中只有一個子活動。 不過，該子活動可以是複合活動，例如<xref:System.Activities.Statements.Sequence>活動或<xref:System.Activities.Statements.Flowchart>活動。

## <a name="activity-designer-library"></a>活動設計工具程式庫

如果您選擇**活動設計工具程式庫**範本，Visual Studio 會建立活動設計工具定義在 XAML 和程式碼後置實作檔案中。 工作流程設計工具隨即開啟，並顯示您的活動設計工具畫布。 將 Windows Presentation Foundation (WPF) 控制項從**工具箱**至設計介面，以在您的自訂活動設計工具中使用它們。

如需如何實作自訂活動設計工具的範例，請參閱 <<c0> [ 如何： 建立自訂活動設計工具](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer)。

> [!NOTE]
> 可用於自訂活動設計工具，自訂活動和用於預設.NET Framework 的活動。

## <a name="see-also"></a>另請參閱

- [使用工作流程設計工具](../workflow-designer/using-the-workflow-designer.md)
- [設計工作流程 (.NET Framework)](/dotnet/framework/windows-workflow-foundation/designing-workflows)