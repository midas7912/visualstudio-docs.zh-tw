---
title: 如何： 發行具有特定地區設定的專案 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, localized projects
- locales, publishing for
- deploying applications [ClickOnce], localized projects
- locales, deploying for
- publishing localized projects
- macros, deploying with
- macros, publishing with
ms.assetid: 7c4cd83a-f985-4c85-9022-fadb5dbd2b39
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca121a8f8a68ca7a036b14c0f0c2bd6d1a84ff00
ms.sourcegitcommit: 6a955a2d179cd0e137942389f940d9fcbbe125de
ms.translationtype: MTE95
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2018
ms.locfileid: "51607584"
---
# <a name="how-to-publish-a-project-that-has-a-specific-locale"></a>如何： 發行具有特定地區設定的專案
一個應用程式包含不同地區設定的元件是很常見的情況。 在此情況下，您會建立一個內含數個專案的方案，然後針對每個地區設定發行不同的專案。 本程序示範如何使用巨集，發行方案中地區設定為 'en' 的第一個專案。 如果您要使用 'en' 以外的地區設定來嘗試執行這個程序，請確定將巨集中的 `localeString` 設定為符合您所使用的地區設定 (例如 'de' 或 'de-DE')。  
  
> [!NOTE]
>  當您使用這個巨集時，發行位置應為有效的 URL 或通用命名慣例 (UNC) 共用。 此外，電腦上也必須安裝 Internet Information Services (IIS)。 在上安裝 IIS，**開始**功能表上，按一下**控制台**。 按兩下**新增或移除程式**。 在 **新增或移除程式**，按一下**新增/移除 Windows 元件**。 在 [ **Windows 元件精靈]**，選取**Internet Information Services (IIS)** 中的核取方塊**元件**清單。 然後按一下**完成**即可關閉精靈。  
  
### <a name="to-create-the-publishing-macro"></a>建立發行巨集  
  
1.  若要開啟 [巨集總管] 中，在**工具**功能表上，指向**巨集**，然後按一下**巨集總管**。  
  
2.  建立新的巨集模組。 在 [巨集總管] 中，選取**MyMacros**。 在上**工具**功能表上，指向**巨集**，然後按一下**新增巨集模組**。 將模組**命名為 PublishSpecificCulture**。  
  
3.  在巨集總管 中，依序展開**MyMacros**節點，然後再開啟**PublishAllProjects**按兩下模組 (或從**工具**功能表上，指向**巨集**，然後按一下**巨集 IDE**)。  
  
4.  在 [巨集 IDE] 中，將下列程式碼加入至模組中的 `Import` 陳述式後面：  
  
    ```vb  
    Module PublishSpecificCulture  
        Sub PublishProjectFirstProjectWithEnLocale()  
            ' Note: You should publish projects by using the IDE at least once  
            ' before you use this macro. Items such as the certificate and the   
            ' security zone must be set.  
            Dim localeString As String = "en"  
  
            ' Get first project.  
            Dim proj As Project = DTE.Solution.Projects.Item(1)  
            Dim publishProperties As Object = proj.Properties.Item("Publish").Value  
  
            ' GenerateManifests and SignManifests must always be set to  
            ' True for publishing to work.   
            proj.Properties.Item("GenerateManifests").Value = True  
            proj.Properties.Item("SignManifests").Value = True  
  
            'Set the publish language.  
            'This will set the deployment language and pick up all   
            ' en resource dlls:  
            Dim originalTargetCulture As String = _  
                publishProperties.Item("TargetCulture").Value  
            publishProperties.Item("TargetCulture").Value = localeString  
  
            'Append 'en' to end of publish, install, and update URLs if needed:  
            Dim originalPublishUrl As String = _  
                publishProperties.Item("PublishUrl").Value  
            Dim originalInstallUrl As String = _  
                publishProperties.Item("InstallUrl").Value  
            Dim originalUpdateUrl As String = _  
                publishProperties.Item("UpdateUrl").Value  
            publishProperties.Item("PublishUrl").Value = _  
                AppendStringToUrl(localeString, New Uri(originalPublishUrl))  
            If originalInstallUrl <> String.Empty Then  
                publishProperties.Item("InstallUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalInstallUrl))  
            End If  
            If originalUpdateUrl <> String.Empty Then  
                publishProperties.Item("UpdateUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalUpdateUrl))  
            End If  
            proj.Save()  
  
            Dim slnbld2 As SolutionBuild2 = _  
                CType(DTE.Solution.SolutionBuild, SolutionBuild2)  
            slnbld2.Clean(True)  
  
            slnbld2.BuildProject( _  
            proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
            proj.UniqueName, True)  
  
            ' Only publish if build is successful.  
            If slnbld2.LastBuildInfo <> 0 Then  
                MsgBox("Build failed for " & proj.UniqueName)  
            Else  
                slnbld2.PublishProject( _  
                proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
                proj.UniqueName, True)  
                If slnbld2.LastPublishInfo = 0 Then  
                    MsgBox("Publish succeeded for " & proj.UniqueName _  
                    & vbCrLf & "." _  
                    & " Publish Language was '" & localeString & "'.")  
                Else  
                    MsgBox("Publish failed for " & proj.UniqueName)  
                End If  
            End If  
  
            ' Return URLs and target culture to their previous state.  
            publishProperties.Item("PublishUrl").Value = originalPublishUrl  
            publishProperties.Item("InstallUrl").Value = originalInstallUrl  
            publishProperties.Item("UpdateUrl").Value = originalUpdateUrl  
            publishProperties.Item("TargetCulture").Value = originalTargetCulture  
            proj.Save()  
        End Sub  
  
        Private Function AppendStringToUrl(ByVal str As String, _  
        ByVal baseUri As Uri) As String  
            Dim returnValue As String = baseUri.OriginalString  
            If baseUri.IsFile OrElse baseUri.IsUnc Then  
                returnValue = IO.Path.Combine(baseUri.OriginalString, str)  
            Else  
                If Not baseUri.ToString.EndsWith("/") Then  
                    returnValue = baseUri.OriginalString & "/" & str  
                Else  
                    returnValue = baseUri.OriginalString & str  
                End If  
            End If  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
5.  關閉 [巨集 IDE]。 焦點將回到 Visual Studio。  
  
### <a name="to-publish-a-project-for-a-specific-locale"></a>發行特定地區設定的專案  
  
1.  若要建立 Visual Basic Windows 應用程式專案，在**檔案**功能表上，指向**新增**，然後按一下 **專案**。  
  
2.  在 **新的專案**對話方塊中，選取**Windows 應用程式**從**Visual Basic**節點。 將專案命名為*PublishLocales*。  
  
3.  按一下 Form1。 中**屬性** 視窗底下**設計**，變更**語言** 屬性從  **（預設）** 到**英文**. 變更**文字**表單的屬性**MyForm**。  
  
     請注意，當地語系化資源 DLL 只有在需要時才會建立。 例如，在您指定新的地區設定之後，若變更表單的文字或其中一個控制項，就會建立。  
  
4.  發佈*PublishLocales*使用 Visual Studio IDE。  
  
     在 **方案總管**，選取*PublishLocales*。 在 **專案**功能表上，選取**屬性**。 在 專案設計工具上**發佈**頁面上，指定發行位置為**http://localhost/PublishLocales**，然後按一下 **立即發佈**。  
  
     當發行網頁出現時，將其關閉。 (在這個步驟中，您只需要發行專案，而不需要安裝專案)。  
  
5.  發佈*PublishLocales*再藉由叫用 Visual Studio 命令提示字元 視窗中的巨集。 若要檢視上的 命令提示字元 視窗中，**檢視**功能表上，指向**其他 Windows** ，然後按一下 **命令視窗**，或按**Ctrl** +**Alt**+**A**。 在 [命令提示字元] 視窗中，輸入`macros`; 自動完成會提供一份可用的巨集。 選取下列巨集，然後按 ENTER 鍵：  
  
     `Macros.MyMacros.PublishSpecificCulture.PublishProjectFirstProjectWithEnLocale`  
  
6.  當發行程序成功時，它會產生訊息，指出 「 已成功發行*PublishLocales\PublishLocales.vbproj*。 發行語言為 'en'」。按一下 **確定**訊息方塊中。 發行網頁出現時，按一下**安裝**。  
  
7.  查看*C:\Inetpub\wwwroot\PublishLocales\en*。 您應該會看到已安裝的檔案，例如資訊清單中， *setup.exe*，和發行網頁檔案，除了當地語系化資源 DLL。 (根據預設 ClickOnce 將附加 *.deploy*延伸模組在 Exe 和 Dll; 您可以在部署後移除此延伸模組。)  
  
## <a name="see-also"></a>另請參閱  
 [發行 ClickOnce 應用程式](../deployment/publishing-clickonce-applications.md)   
 [巨集的開發環境](/previous-versions/visualstudio/visual-studio-2010/fb30sxt3(v=vs.100))   
 [巨集總管 視窗](/previous-versions/visualstudio/visual-studio-2010/wwkx67sw(v=vs.100))   
 [如何： 編輯，並以程式設計方式建立巨集](/previous-versions/visualstudio/visual-studio-2010/k91y6132(v=vs.100))