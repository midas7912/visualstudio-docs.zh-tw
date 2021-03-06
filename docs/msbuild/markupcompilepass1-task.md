---
title: MarkupCompilePass1 工作 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- converting XAML to binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], parameters
- converting XAML projects to compiled binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], converting XAML to binary format
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9db623dd06db06a1dfee3e22345564f888431d1c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49855324"
---
# <a name="markupcompilepass1-task"></a>MarkupCompilePass1 工作

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 工作會將未當地語系化的 [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] 專案檔案轉換成已編譯的二進位格式。

## <a name="task-parameters"></a>工作參數

| 參數 | 描述 |
| - | - |
| `AllGeneratedFiles` | 選擇性的 **ITaskItem[]** 輸出參數。<br /><br /> 包含 <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 工作產生的完整檔案清單。 |
| `AlwaysCompileMarkupFilesInSeparateDomain` | 選擇性的 **Boolean** 參數。<br /><br /> 指定是否在不同的 <xref:System.AppDomain> 中執行工作。 如果此參數傳回 **false**，工作就會在與 [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] 相同的 <xref:System.AppDomain> 中執行，且執行速度會較快。 如果此參數傳回 **true**，工作就會在與 [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] 隔離的第二個 <xref:System.AppDomain> 中執行，且執行速度會較慢。 |
| `ApplicationMarkup` | 選擇性的 **ITaskItem[]** 參數。<br /><br /> 指定應用程式定義 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案的名稱。 |
| `AssembliesGeneratedDuringBuild` | 選擇性的 **String[]** 參數。<br /><br /> 指定對在建置程序中變更之組件的參考。 例如，Visual Studio 解決方案可能包含一個專案，此專案參考另一個專案的已編譯輸出。 在此情況下，可以將第二個專案的已編譯輸出新增到 **AssembliesGeneratedDuringBuild** 參數。<br /><br /> 注意：**AssembliesGeneratedDuringBuild** 參數必須包含對組建方案所產生之一組完整組件的參考。 |
| `AssemblyName` | 必要的 **string** 參數。<br /><br /> 指定為專案產生之組件的簡短名稱。 例如，如果專案要產生名稱為 *WinExeAssembly.exe* 的 [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] 可執行檔，則 **AssemblyName** 參數的值會是 **WinExeAssembly**。 |
| `AssemblyPublicKeyToken` | 選擇性的 **String** 參數。<br /><br /> 指定組件的公開金鑰語彙基元。 |
| `AssemblyVersion` | 選擇性的 **String** 參數。<br /><br /> 指定組件的版本號碼。 |
| `ContentFiles` | 選擇性的 **ITaskItem[]** 參數。<br /><br /> 指定鬆散內容檔案的清單。 |
| `DefineConstants` | 選擇性的 **String** 參數。<br /><br /> 指定保留目前的 **DefineConstants** 值。 這會影響目標組件產生；如果變更此參數，就可能變更目標組件中的公用 API，而可能影響到參考區域類型之 [!INCLUDE[TLA2#tla_titlexaml](../msbuild/includes/tla2sharptla_titlexaml_md.md)] 檔案的編譯。 |
| `ExtraBuildControlFiles` | 選擇性的 **ITaskItem[]** 參數。<br /><br /> 指定可控制當 <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 工作返回時是否要觸發重建的檔案清單；如果這些檔案其中一個發生變更，就會觸發重建。 |
| `GeneratedBamlFiles` | 選擇性的 **ITaskItem[]** 輸出參數。<br /><br /> 包含採用 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 二進位格式的已產生檔案清單。 |
| `GeneratedCodeFiles` | 選擇性的 **ITaskItem[]** 輸出參數。<br /><br /> 包含已產生的 Managed 程式碼檔案清單。 |
| `GeneratedLocalizationFiles` | 選擇性的 **ITaskItem[]** 輸出參數。<br /><br /> 包含已針對每個可當地語系化的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案產生的當地語系化檔案清單。 |
| `HostInBrowser` | 選擇性的 **String** 參數。<br /><br /> 指定產生的組件是否為 [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)]。 有效的選項為 **true** 和 **false**。 如果為 **true**，就會產生程式碼來支援瀏覽器裝載。 |
| `KnownReferencePaths` | 選擇性的 **String[]** 參數。<br /><br /> 指定對在建置程序中不會變更之組件的參考。 包括位於 [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)]、位於 [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] 安裝目錄等位置中的組件。 |
| `Language` | 必要的 **String** 參數。<br /><br /> 指定編譯器支援的 Managed 語言。 有效的選項為 **C#**、**VB**、**JScript** 及 **C++**。 |
| `LanguageSourceExtension` | 選擇性的 **String** 參數。<br /><br /> 指定附加至所產生的 Managed 程式碼檔案之副檔名的副檔名：<br /><br /> `<Filename>.g<LanguageSourceExtension>`<br /><br /> 如果沒有為 **LanguageSourceExtension** 參數設定特定的值，就會使用語言的預設來源檔案副檔名：*.vb* (適用於 [!INCLUDE[TLA#tla_visualb](../msbuild/includes/tlasharptla_visualb_md.md)])、*.csharp* (適用於 [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)])。 |
| `LocalizationDirectivesToLocFile` | 選擇性的 **String** 參數。<br /><br /> 指定如何產生每個來源 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案的當地語系化資訊。 有效的選項為 **None**、**CommentsOnly** 及 **All**。 |
| `OutputPath` | 必要的 **String** 參數。<br /><br /> 指定要在其中產生所產生之 Managed 程式碼檔案和 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 二進位格式檔案的目錄。 |
| `OutputType` | 必要的 **String** 參數。<br /><br /> 指定專案所產生之組件的類型。 有效的選項為 **winexe**、**exe**、**library** 及 **netmodule**。 |
| `PageMarkup` | 選擇性的 **ITaskItem[]** 參數。<br /><br /> 要處理的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案清單。 |
| `References` | 選擇性的 **ITaskItem[]** 參數。<br /><br /> 指定從檔案到包含 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案中所使用類型之組件的參考清單。 |
| `RequirePass2ForMainAssembly` | 選擇性的 **Boolean** 輸出參數。<br /><br /> 指出專案是否包含參考內嵌至主要組件之區域類型的無法當地語系化 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案。 |
| `RequirePass2ForSatelliteAssembly` | 選擇性的 **Boolean** 輸出參數。<br /><br /> 指出專案是否包含參考內嵌至主要組件之區域類型的可當地語系化 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案。 |
| `RootNamespace` | 選擇性的 **String** 參數。<br /><br /> 指定專案內類別的根命名空間。 當對應的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案未包含 `x:Class` 屬性時，**RootNamespace** 也用來作為所產生 Managed 程式碼檔案的預設命名空間。 |
| `SourceCodeFiles` | 選擇性的 **ITaskItem[]** 參數。<br /><br /> 指定目前專案的程式碼檔案清單。 此清單不包括已產生的語言特定 Managed 程式碼檔案。 |
| `UICulture` | 選擇性的 **String** 參數。<br /><br /> 指定要在其中內嵌所產生之 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 二進位格式檔案的 UI 文化特性 (Culture) 附屬組件。 如果未設定 **UICulture**，所產生的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 二進位格式檔案就會內嵌在主要組件中。 |
| `XAMLDebuggingInformation` | 選擇性的 **Boolean** 參數。<br /><br /> 值為 **true** 時，會產生診斷資訊並包含在已編譯的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 中，以協助偵錯。 |

## <a name="remarks"></a>備註

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 工作通常會將 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 編譯成二進位格式，並產生程式碼檔。 如果 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案包含對相同專案中所定義之類型的參考，**MarkupCompilePass1** 就會將其二進位格式編譯延後至第二個標記編譯階段 (**MarkupCompilePass2**)。 這類檔案的編譯必須延後，因為它們必須等待所參考的本機定義類型編譯完成。 不過，如果 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案具有 `x:Class` 屬性，則 <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> 會產生其語言專屬的程式碼檔案。

[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案如果包含使用 `x:Uid` 屬性的元素，便是可當地語系化的檔案：

```xml
<Page x:Class="WPFMSBuildSample.Page1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Uid="Page1Uid"
    >
  ...
</Page>
```

當 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案宣告 [!INCLUDE[TLA#tla_xml](../msbuild/includes/tlasharptla_xml_md.md)] 命名空間以使用 `clr-namespace` 值來參考目前專案中的命名空間時，會參考本機定義的類型：

```xml
<Page x:Class="WPFMSBuildSample.Page1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:localNamespace="clr-namespace:WPFMSBuildSample"
    >
    <Grid>
      <Grid.Resources>
        <localNameSpace:LocalType x:Key="localType" />
      </Grid.Resources>
      ...
    </Grid>
</Page>
```

如果有任何 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案是可當地語系化的，或是參考本機定義的類型，就必須有第二個標記編譯階段，這會需要執行 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)，然後執行 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)。

## <a name="example"></a>範例

下列範例示範如何將三個「頁面」[!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 檔案轉換成二進位格式檔案。 *Page1* 包含對類型 `Class1` (位於專案的根命名空間中) 的參考，因此無法在此標記編譯階段中轉換成二進位格式檔案。 取而代之的是，會執行 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)，接著執行 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)。

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask 
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass1" 
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="MarkupCompilePass1Task">
    <MarkupCompilePass1 
      AssemblyName="WPFMSBuildSample"
      Language="C#"
      OutputType="WinExe"
      OutputPath="obj\Debug\"
      ApplicationMarkup="App.xaml"
      PageMarkup="Page1.xaml;Page2.xaml;Page3.xaml"
      SourceCodeFiles="Class1.cs"
      References="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />
  </Target>
</Project>
```

## <a name="see-also"></a>另請參閱

[WPF MSBuild 參考](../msbuild/wpf-msbuild-reference.md)  
[WPF MSBuild 工作參考](../msbuild/wpf-msbuild-task-reference.md)  
[MSBuild 參考](../msbuild/msbuild-reference.md)  
[MSBuild 工作參考](../msbuild/msbuild-task-reference.md)  
[建置 WPF 應用程式 (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)  
[WPF XAML 瀏覽器應用程式概觀](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)