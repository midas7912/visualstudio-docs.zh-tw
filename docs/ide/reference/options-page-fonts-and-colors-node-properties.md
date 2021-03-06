---
title: 字型和色彩節點屬性、選項頁
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94a253d6e723cfa810ada9a7384fe1cda0826ac4
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50672259"
---
# <a name="options-page-fonts-and-colors-node-properties"></a>字型和色彩節點屬性、選項頁
本文件說明 [工具] 視窗的字型和色彩屬性，它是登錄顯示在 [選項] 對話方塊的 [環境] 類別的 [字型和色彩] 中。 這支援可變換色彩項目群組的動態本質，如果安裝或解除安裝 VSPackage 時可予以變更。

 下節顯示各視窗可使用的已登錄視窗類型和屬性範例。

## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>文字編輯器或印表機或對話方塊和工具視窗
 `DTE.Properties("FontsAndColors", "TextEditor")`

 -或-

 `DTE.Properties("FontsAndColors", "Printer")`

 -或-

 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`

|屬性項目名稱|值|描述|
| - |-----------|-----------------|
|FontFamily|Get/Set (字串)|要使用的字型名稱，例如「新細明體」。|
|FontCharacterSet|Get/Set (<xref:EnvDTE.vsFontCharSet>)|<xref:EnvDTE.vsFontCharSet> 值，指定要使用的字元集類型，例如希伯來文或俄文。|
|FontSize|Get/Set (短整數)|要使用的字型大小，以點為單位。 例如 10 或 12。|

## <a name="see-also"></a>請參閱

- [控制選項設定](https://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)
- [在選項頁中決定屬性項目的名稱](https://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)
- [環境節點屬性、選項頁面](../../ide/reference/options-page-environment-node-properties.md)
- [文字編輯器節點屬性、選項頁面](../../ide/reference/options-page-text-editor-node-properties.md)