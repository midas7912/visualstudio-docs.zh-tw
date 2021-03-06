---
title: 擴充 Visual Studio for Mac
description: Visual Studio for Mac 的特性與功能可以使用稱為延伸模組套件的模組來擴充。 本指南的第一個部分會建立簡單的 Visual Studio for Mac 延伸模組套件，在文件中插入日期和時間。 本指南的第二個部分則介紹延伸模組套件系統的基本概念，和形成 Visual Studio for Mac 基礎的一些核心應用程式開發介面。
author: conceptdev
ms.author: crdun
ms.date: 04/14/2017
ms.technology: vs-ide-sdk
ms.assetid: D5245AB0-8404-426B-B538-F49125E672B2
ms.openlocfilehash: 8212039cd4f83cd9ea2b53a1050f32ed5dbad367
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "51295133"
---
# <a name="extending-visual-studio-for-mac"></a>擴充 Visual Studio for Mac

Visual Studio for Mac 包含一組稱為「延伸模組套件」的模組。 您可以使用延伸模組套件，為 Visual Studio for Mac 引入新功能，例如支援其他語言或新的專案範本。

延伸模組套件會從其他延伸模組套件的「延伸模組」點建置。 擴充點是可擴充區域的預留位置，例如功能表或 IDE 命令的清單。 延伸模組套件可以從擴充點建置，方法是註冊一個稱為延伸模組的結構化資料節點，例如新的功能表項目或新的命令。 每個擴充點會接受特定類型的延伸模組，例如「命令」、「板」或「檔案範本」。 包含延伸模組的模組，稱為「增益集主機」，因為它可以由其他延伸模組套件加以擴充。

若要自訂 Visual Studio for Mac，您可以建立一個延伸模組套件，從 Visual Studio for Mac 現有程式庫內的增益集主機中所包含的擴充點建置，如下列圖所示：

![增益集架構](media/extending-visual-studio-mac-addin1.png)

為了讓延伸模組套件從 Visual Studio for Mac 建置，它必須具有從 Visual Studio for Mac IDE 內現有擴充點建置的延伸模組。 當延伸模組套件依賴增益集主機中所定義的擴充點時，它會被稱為對該延伸模組套件具有「相依性」 __ 。

此模組化設計的好處是，Visual Studio for Mac 可以擴充 -- 有許多擴充點可供自訂延伸模組套件建置之用。 目前的延伸模組套件範例包括支援 C# 和 F#、偵錯工具和專案範本。

> [!NOTE]
> **注意**：如果您有在增益集製作程式 1.2 之前建立的增益集製作程式專案，則需要移轉專案，如[這裡](https://mhut.ch/addinmaker/1.2)的步驟中所述。

<!---The [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) topic explains how to build an extension package that uses a *Command* to insert the date and time into an open text document.--->

本節探討由增益集製作程式產生的不同檔案，以及命令延伸模組所需的資料。

## <a name="attribute-files"></a>屬性檔

延伸模組套件會將其名稱、版本、相依性以及其他資訊的相關中繼資料儲存在 C# 屬性。 增益集製作程式會建立兩個檔案 `AddinInfo.cs` 和 `AssemblyInfo.cs`，來儲存和組織這項資訊。 延伸模組套件必須在其「增益集屬性」中指定唯一的識別碼和命名空間：

```csharp
[assembly:Addin (
   "DateInserter",
   Namespace = "DateInserter",
   Version = "1.0"
)]
```

延伸模組套件也必須宣告對擁有它們插入之擴充點的延伸模組套件具有相依性。 這些會在建置階段自動參考。

此外，可以透過專案的 Solution Pad 中的增益集參考節點，新增其他參考，如下圖所示：

![插入日期螢幕擷取畫面](media/extending-visual-studio-mac-addin13.png)

它們也會有對應的 `assembly:AddinDependency` 屬性在建置階段新增。 中繼資料和相依性宣告就緒之後，您就可以專注於延伸模組套件的基本建置組塊。

## <a name="extensions-and-extension-points"></a>延伸模組和擴充點

擴充點是一個預留位置，其定義資料結構 (類型)，而延伸模組則定義符合特定擴充點指定之結構的資料。 擴充點在其宣告中指定可以接受的延伸模組類型。 延伸模組是使用型類型稱或延伸模組路徑來宣告。 如需如何建立所需擴充點的更深入說明，請參閱[擴充點參考](https://github.com/mono/mono-addins/wiki/Extension-Points)。

延伸模組/擴充點的架構讓 Visual Studio for Mac 的開發能維持快速且模組化。

<!--Since there are a large number of extension types, this article focuses on the ones used in the extension package that was built in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md).-->

### <a name="command-extensions"></a>命令延伸模組

<!--[Walkthrough](~/extending-visual-studio-mac-walkthrough.md) uses a Command Extension - an extension that points to methods that are called every time it is executed. -->

命令延伸模組為指向每次執行時所呼叫之方法的延伸模組。

命令延伸模組是藉由新增項目至 `/MonoDevelop/Ide/Commands` 擴充點來定義。 我們使用下列程式碼，在 `Manifest.addin.xml` 中定義了延伸模組：

 ```xml
<Extension path="/MonoDevelop/Ide/Commands/Edit">
  <command id="DateInserter.DateInserterCommands.InsertDate"
            _label="Insert Date"
            _description="Insert the current date"
            defaulthandler="DateInserter.InsertDateHandler" />
</Extension>
```

擴充節點包含路徑屬性，它指定插入到的擴充點，在此案例中為 `/MonoDevelop/Ide/Commands/Edit`。 此外，它會作為命令的父節點。 命令節點具有下列屬性：

*   **id** - 指定此命令的識別碼。 命令識別碼必須宣告為列舉成員，並且會用來將命令連接至 CommandItem。
*   **_label** - 要顯示在功能表中的文字。
*   **_description** - 要顯示為工具列按鈕之工具提示的文字。
*   **defaultHandler** - 指定賦予命令功能的 `CommandHandler` 類別

<!--To invoke the command from the Edit Menu, the walkthrough creates a CommandItem extension that plugs into the `/MonoDevelop/Ide/MainMenu/Edit` extension point:-->

下列程式碼片段會示範插入 `/MonoDevelop/Ide/MainMenu/Edit` 擴充點的 CommandItem 延伸模組：

```xml
<Extension path="/MonoDevelop/Ide/MainMenu/Edit">
  <commanditem id="DateInserter.DateInserterCommands.InsertDate" />
</Extension>
```

CommandItem 將其 id 屬性中指定的命令放入功能表。 此 CommandItem 會擴充 `/MonoDevelop/Ide/MainMenu/Edit` 擴充點，讓命令的標籤出現在 [編輯] 功能表。 請注意，CommandItem 中的 **id** 對應到命令節點的識別碼 `InsertDate`。 如果您要移除 CommandItem，[插入日期] 選項就會從 [編輯] 功能表消失。

### <a name="command-handlers"></a>命令處理常式

`InsertDateHandler` 是 `CommandHandler` 類別的延伸模組。 它覆寫兩個方法：`Update` 和 `Run`。 每當命令顯示在功能表中或透過按鍵繫結執行時，便會查詢 `Update`。 藉由變更資訊物件，您可以停用命令或讓它成為不可見、填入陣列命令等等。 這個 `Update` 方法會停用命令，如果它找不到作用中的「文件」與「文字編輯器」來插入文字：

```csharp
protected override void Update (CommandInfo info)
{
    info.Enabled = IdeApp.Workbench.ActiveDocument?.Editor != null;
}
```

您只需要在有啟用或隱藏命令的特殊邏輯時才覆寫 `Update` 方法。 每當使用者執行命令，`Run` 方法便會執行，在此案例中則是當使用者從 [編輯] 功能表選取命令時發生。 這個方法會在文字編輯器的插入號位置插入日期和時間：

```csharp
protected override void Run ()
{
  var editor = IdeApp.Workbench.ActiveDocument.Editor;
  var date = DateTime.Now.ToString ();
  editor.InsertAtCaret (date);
}
```

在 `DateInserterCommands` 內將命令類型宣告為列舉成員：

```csharp
public enum DateInserterCommands
{
  InsertDate,
}
```

此將命令和 CommandItem 繫結在一起，從 [編輯] 功能表選取 CommandItem 時，CommandItem 會呼叫命令。

## <a name="ide-apis"></a>IDE API

<!--The extension package detailed in the [Walkthrough](~/extending-visual-studio-mac-walkthrough.md) deals with the Text Editor in Visual Studio for Mac, but this is only one of many possible areas for customization. -->

如需可供開發的區域範圍資訊，請參閱 [Extension Tree Reference](http://monodevelop.com/Developers/Articles/Extension_Tree_Reference) (延伸模組樹狀目錄參考) 和 [API Overview](http://monodevelop.com/Developers/Articles/API_Overview) (API 概觀)。 建置進階延伸模組套件時，也請參閱 [Developer Articles](http://monodevelop.com/Developers/Articles) (開發人員文章)。 以下是自訂區域的部分清單：

*   板
*   按鍵繫結配置
*   原則
*   程式碼格式器
*   專案檔案格式
*   喜好設定面板
*   選項面板
*   偵錯工具通訊協定
*   偵錯工具視覺化檢視
*   工作區版面配置
*   Solution Pad 樹狀節點
*   原始檔編輯器邊界
*   單元測試引擎
*   程式碼產生器
*   程式碼片段
*   目標 Framework
*   目標執行階段
*   VC 後端
*   重構
*   執行處理常式
*   語法醒目提示

## <a name="additional-information"></a>其他資訊

> [!NOTE]
> 我們目前正努力改善 Visual Studio for Mac 的擴充性情節。 如果您正在建立延伸模組並需要其他協助或相關資訊，或是想要提供意見反應，請填寫 [Visual Studio for Mac 延伸模組製作](https://aka.ms/vsmac-extensions-survey) \(英文\) 表單。

## <a name="see-also"></a>另請參閱

- [開發 Visual Studio 延伸模組 (Windows 上)](/visualstudio/extensibility/starting-to-develop-visual-studio-extensions)