---
title: 準備偵錯 c + + 專案 |Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project templates, debugging
- Visual C++ projects, debugging
- debug builds, project settings
- debugging [C++]
ms.assetid: 912b4ba2-7719-43d5-b087-db33e3f9329a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: c39acdef217d2b858645073cb96da4952c91df5a
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/07/2018
ms.locfileid: "53066310"
---
# <a name="debugging-preparation-visual-c-project-types"></a>偵錯準備：Visual C++ 專案類型
本節說明如何對 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 專案範本所建立的基本專案類型進行偵錯。  
  
 請注意，這些專案類型建立 Dll 為輸出均已分組為[偵錯 DLL 專案](../debugger/debugging-dll-projects.md)因為它們共用通用的功能。  
  
##  <a name="BKMK_In_this_topic"></a>本主題內容  
 [建議的屬性設定](#BKMK_Recommended_Property_Settings)  
  
 [Win32 專案](#BKMK_Win32_Projects)  
  
- [偵錯 C 或 C++ Win32 應用程式](#BKMK_To_debug_a_C_or_C___Win32_application)  
  
- [手動設定偵錯組態](#BKMK_To_manually_set_a_Debug_configuration)  
  
  [Windows Forms 應用程式 (.NET)](#BKMK_Windows_Forms_Applications___NET_)  
  
##  <a name="BKMK_Recommended_Property_Settings"></a> 建議的屬性設定  
 在所有 Unmanaged 偵錯情況中，某些屬性必須以相同的方式設定。 下表顯示建議的屬性設定。 此處未列出的設定，可能會因不同的 Unmanaged 專案類型而異。 如需詳細資訊，請參閱[c + + 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)  
  
### <a name="configuration-properties-124-cc-124-optimization-node"></a>組態屬性&#124;C/c + +&#124;最佳化節點  
  
|屬性名稱|設定|  
|-------------------|-------------|  
|**Optimization**|設定為 [停用 (/0d)]。 最佳化程式碼較難偵錯，因為產生的指令不能直接對應到您的原始程式碼。 如果您發現程式含有僅出現在最佳化程式碼中的 Bug，您可以開啟這個設定，但是請記住，顯示在 [反組譯碼] 視窗裡的程式碼是由最佳化原始程式碼所產生，可能與您在原始程式碼視窗所看到的內容不相符。 其他功能 (例如逐步執行) 可能無法如預期般地執行。|  
  
### <a name="configuration-properties-124-linker-124-debugging-node"></a>組態屬性&#124;連結器&#124;偵錯 節點  
  
|屬性名稱|設定|  
|-------------------|-------------|  
|**產生偵錯資訊**|這個選項必須一律設定為 [是 (/DEBUG)]，才能產生偵錯時需要的偵錯符號和檔案。 當應用程式開始運作時，就可以將其設定為關閉。|  
  
 [本主題內容](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Win32_Projects"></a> Win32 專案  
 Win32 應用程式是以 C 或 C++ 撰寫的傳統 Windows 程式。 在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中可以直接偵錯這種類型的應用程式。  
  
 Win32 應用程式包括 MFC 應用程式和 ATL 專案。 它們會使用 Windows API，也可能會使用 MFC 或 ATL，但是不會使用 Common Language Runtime (CLR)。 但是，它們能呼叫使用 CLR 的 Managed 程式碼。  
  
 下列程序說明在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 內偵錯 Win32 專案的方法。 另一個偵錯 Win32 應用程式的方法，是在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 外部啟動應用程式，然後進行附加。 如需詳細資訊，請參閱 <<c0> [ 附加至執行的處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。  
  
###  <a name="BKMK_To_debug_a_C_or_C___Win32_application"></a> 偵錯 C 或 C++ Win32 應用程式  
  
1.  在 Visual Studio 中開啟專案。  
  
2.  在 [偵錯] 功能表上選擇 [啟動]。  
  
3.  使用所述的技巧進行偵錯[偵錯工具基本概念](../debugger/getting-started-with-the-debugger.md)。  
  
###  <a name="BKMK_To_manually_set_a_Debug_configuration"></a> 手動設定偵錯組態  
  
1. 在 [檢視] 功能表上按一下 [屬性頁]。  
  
2. 如果 [組態屬性] 節點尚未開啟，請按一下將它開啟  
  
3. 選取 [一般]，並將 [輸出] 列的值設定為 [偵錯]。  
  
4. 開啟 [C/C++] 節點，並選取 [一般]。  
  
    在 [偵錯] 列中，指定您希望編譯器產生的偵錯資訊類型。 您可能選擇的值包括 [程式資料庫 (/Zi)] 或 [編輯後繼續的程式資料庫 (/ZI)]。  
  
5. 選取 [最佳化]，並在 [最佳化] 列的下拉清單中，選取 [停用 (/0d)]。  
  
    最佳化程式碼較難偵錯，因為產生的指令不能直接對應到您的原始程式碼。 如果您發現程式含有僅出現在最佳化程式碼中的錯誤，您可以啟動這個設定，但是請記住，顯示在 [反組譯碼] 視窗裡的程式碼是由最佳化原始程式碼所產生，可能無法對應至您在原始程式碼視窗所看到的內容。 逐步執行之類的功能，可能無法正確顯示中斷點和執行點。  
  
6. 開啟 [連結器] 節點，並選擇 [偵錯]。 在第一個 [產生] 資料列的下拉清單中，選取 [是 (/DEBUG)]。 進行偵錯時，一律要設定這個選項。  
  
   如需詳細資訊，請參閱 <<c0> [ c + + 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)。  
  
   [本主題內容](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
##  <a name="BKMK_Windows_Forms_Applications___NET_"></a> Windows Forms 應用程式 (.NET)  
 [Windows Forms 應用程式 (.NET)] 範本可以建立 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] Windows Forms 應用程式。 如需詳細資訊，請參閱[＜How to：建立 Windows 應用程式專案](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/42wc9kk5(v=vs.100))。  
  
 在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中偵錯這種類型的應用程式，與偵錯 Managed Windows Forms 應用程式類似。  
  
 當您以專案範本建立 Windows Form 專案時，[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 會自動建立偵錯和發行組態所需要的設定。 如果有必要，您可以在 [\<專案名稱> 屬性頁] 對話方塊中變更這些設定。 如需詳細資訊，請參閱[偵錯和發行組態](../debugger/how-to-set-debug-and-release-configurations.md)。  
  
 如需詳細資訊，請參閱 < [c + + 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)。  
  
 偵錯 Windows Forms 應用程式的另一種方法，是在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 外啟動應用程式並且附加於其上。 如需詳細資訊，請參閱[附加至正在執行的程式或多個程式](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。  
  
 [本主題內容](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)  
  
## <a name="see-also"></a>請參閱  
 [偵錯工具基礎](../debugger/getting-started-with-the-debugger.md)   
 [C++ 偵錯組態的專案設定](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [附加至正在執行的程式或多個程式](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [偵錯和發行組態](../debugger/how-to-set-debug-and-release-configurations.md)   
 [如何：建立 Windows 應用程式專案](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/42wc9kk5(v=vs.100))