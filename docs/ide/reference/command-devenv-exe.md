---
title: -Command (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2ee6f1166a543cc3dc85dfb62d19d1c5b194a16
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948162"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
在啟動 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 整合式開發環境 (IDE) 之後，執行指定的命令。

## <a name="syntax"></a>語法

```cmd
devenv /command CommandName
```

## <a name="arguments"></a>引數
 `CommandName` 必要項。 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 命令的完整名稱或其別名，以雙引號括住。 如需命令和別名語法的詳細資訊，請參閱 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)。

## <a name="remarks"></a>備註
 啟動完成後，IDE 會執行具名命令。 如果您使用此參數，IDE 在啟動時就不會顯示 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 起始頁。

 如果增益集公開某個命令，則可從命令列中使用此參數啟動增益集。 如需詳細資訊，請參閱[如何：使用增益集管理員來控制增益集](https://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb)。

## <a name="example"></a>範例
 此範例會啟動 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 並自動執行巨集 Open Favorite Files。

```cmd
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"
```

## <a name="see-also"></a>請參閱

- [Devenv 命令列參數](../../ide/reference/devenv-command-line-switches.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)