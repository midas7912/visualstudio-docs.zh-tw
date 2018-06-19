---
ms.topic: include
ms.openlocfilehash: 78de57178350d4317896c41a455efbeeb553c58d
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031152"
---
## <a name="install-the-connected-environment-cli"></a>安裝已連線的環境 CLI
已連線的環境需要基本的本機電腦設定。 您開發環境的大部分組態會儲存在雲端中，可與其他使用者共用。

### <a name="install-on-mac"></a>安裝在 Mac 上
下載並安裝已連線的環境 CLI：
```cmd
curl -L https://aka.ms/get-vsce-mac | bash
```

### <a name="install-on-windows"></a>安裝在 Windows 上
1. 下載並執行[已連線的環境 CLI 安裝程式](https://aka.ms/get-vsce-windows)。 

### <a name="install-on-linux"></a>安裝在 Linux 上
即將推出…

## <a name="get-kubernetes-debugging-for-vs-code"></a>讓 Kubernetes 偵錯 VS 程式碼
雖然您可以使用已連線的環境 CLI 當作獨立的工具，但使用 VS Code 的 .NET Core 和 Node.js 開發人員仍可使用如 Kubernetes 偵錯的豐富功能。

1. 如果沒有，請安裝 [VS Code](https://code.visualstudio.com/Download)。
1. 下載 [VS 已連線的環境延伸模組](https://aka.ms/get-vsce-code)。
1. 安裝延伸模組： 

```cmd
code --install-extension path-to-downloaded-extension/vsce-0.1.1.vsix
```