---
title: '&lt;compatibleFrameworks&gt;項目 （ClickOnce 部署） |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44329fc4c2ec5e9f2f8352d69ea487f23cbe3c5a
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077681"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt;項目 （ClickOnce 部署）
識別安裝及執行此應用程式所需的 .NET Framework 版本。  
  
> [!NOTE]
>  [*MageUI.exe* ](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)不支援`compatibleFrameworks`憑證，使用已簽署項目儲存應用程式資訊清單時[ *MageUI.exe*](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)。 相反地，您必須使用[ *Mage.exe*](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)。  
  
## <a name="syntax"></a>語法  
  
```xml  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>項目和屬性  
 `compatibleFrameworks`項目時，需要部署資訊清單目標[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]所提供的執行階段[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]或更新版本。 `compatibleFrameworks`元素包含一或多個`framework`項目會指定此應用程式可以執行所在的.NET Framework 版本。 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]執行階段將執行應用程式在第一個可用`framework`這份清單中。  
  
 下表列出屬性，`compatibleFrameworks`項目支援。  
  
|屬性|描述|  
|---------------|-----------------|  
|`S` `upportUrl`|選擇性。 指定的 URL，可以下載相容的慣用的.NET Framework 版本的位置。|  
  
## <a name="framework"></a>架構  
 必要。 下表列出的屬性，`framework`項目支援。  
  
|屬性|描述|  
|---------------|-----------------|  
|`targetVersion`|必要。 指定的目標.NET Framework 的版本號碼。|  
|`profile`|必要。 指定的目標.NET Framework 的設定檔。|  
|`supportedRuntime`|必要。 指定執行階段相關聯的目標.NET Framework 的版本號碼。|  
  
## <a name="remarks"></a>備註  
  
## <a name="example"></a>範例  
 下列程式碼範例所示`compatibleFrameworks`中的項目[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]部署資訊清單。 可以執行此部署[!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]。 它也可以執行[!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)]因為它的超集[!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]。  
  
```xml  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>另請參閱  
 [ClickOnce 部署資訊清單](../deployment/clickonce-deployment-manifest.md)