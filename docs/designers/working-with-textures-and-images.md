---
title: 使用紋理和影像
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: b9fbc8fa-66d1-4055-8460-24d8b8fbe43e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cb7cc97a797d02bd8353cbcfb19af6b8f9edf674
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079656"
---
# <a name="work-with-textures-and-images"></a>使用紋理和影像

您可以使用 Visual Studio 中的影像編輯器來建立和修改紋理和影像。 影像編輯器支援豐富的紋理和影像格式，如同在 DirectX 應用程式開發中所使用的一樣。

> [!NOTE]
> 影像編輯器不支援圖示或游標等低色影像。 若要建立或修改這類影像，請使用[圖示影像編輯器 (C++)](/cpp/windows/image-editor-for-icons)。

## <a name="textures-and-images"></a>紋理和影像

紋理和影像在基本層級只是資料的資料表，可用來在圖形應用程式中提供視覺詳細資料。 紋理或影像所提供的詳細資料類型取決於其使用方式，但色彩範例、alpha (投影片) 值、曲面法線和高度值都是常見範例。 紋理和影像的主要差異在於紋理必須要與圖形表示法搭配使用 (通常為 3-D 模型) 以表達完整的物件或場景，但影像通常是物件或場景的獨立表示法。

任何紋理可以數種方式進行編碼，與紋理持有的資料類型，或紋理的維度或「圖形」成直角。 不過，不同的編碼和壓縮方法會對不同類型的資料產生更好的結果。

您可以使用影像編輯器，以類似於其他影像編輯器的方式來建立及修改紋理和影像。 影像編輯器也提供縮小貼圖和其他功能與 3D 圖形搭配使用，並支援許多 DirectX 可支援的高度壓縮、啟用硬體加速紋理的格式。

常見的材質類型包括︰

### <a name="texture-maps"></a>材質貼圖

材質貼圖包含組織為一段、兩段或 3D 矩陣的色彩值。 它們用來提供受影響物件的色彩詳細資料。 色彩通常使用 RGB (紅色、綠色、藍色) 色頻來編碼，而且可能包括第四個通道 alpha 來表示透明度。 較不常見的情況下，色彩無法在其他色彩配置中編碼，或第四個通道可能會包含 alpha 以外的資料 — 例如，高度。

### <a name="normal-maps"></a>法線貼圖

法線貼圖包含曲面法線。 它們用來提供受影響物件的光源詳細資料。 法線通常使用紅色、綠色和藍色元件來編碼，以儲存向量的 x、y 和 z 維度。 不過，存在其他編碼 — 例如，以極座標為基礎的編碼方式。

### <a name="height-maps"></a>高度貼圖

高度貼圖包含高度欄位資料。 它們用來提供受影響物件的幾何詳細資料的表單 (方法是使用著色器程式碼來計算所需的效果) 或提供資料點以供地形產生等使用。 高度值通常是使用紋理中的一個通道來編碼。

### <a name="cube-maps"></a>立方體貼圖

立方體貼圖可以包含不同類型的資料 (例如色彩或法線) 但會組織成立方體表面上的六個紋理。 因為這個緣故，立方體貼圖不是藉由提供紋理座標取樣，而是藉由提供一個來源為立方體中央的向量；會在向量與立方體交集之處取樣。 立方體貼圖用來提供可用來計算反射的環境近似值 — 這就是所謂的 *環境對應*— 或用來提供材質給具有比基本、2D 材質可提供的扭曲程度更低的球面物件。

## <a name="related-topics"></a>相關主題

|標題|描述|
|-----------|-----------------|
|[影像編輯器](../designers/image-editor.md)|描述如何使用影像編輯器來處理紋理和影像。|
|[影像編輯器範例](../designers/image-editor-examples.md)|提供示範如何使用影像編輯器來執行一般映像處理工作的主題連結。|