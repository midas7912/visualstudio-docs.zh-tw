---
title: 負載測試記錄設定
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f280911be68616a1c2632195769547023832b061
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/07/2018
ms.locfileid: "53060034"
---
# <a name="modify-load-test-logging-settings"></a>修改負載測試記錄設定

已完成之負載測試的負載測試結果包含效能計數器樣本，以及記錄檔中定期從受測電腦收集而來的錯誤資訊。 您可以在負載測試回合進行期間收集大量效能計數器樣本。 收集的效能資料量會視回合的時間長度、取樣間隔、受測電腦數目，以及要收集的計數器數目而定。 若為大型負載測試，則收集的效能資料量可能很容易就達到數個 GB。因此，您可能考慮修改將資料儲存到記錄檔的頻率。 請參閱[測試控制器和測試代理程式](configure-test-agents-and-controllers-for-load-tests.md)。

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

「測試控制器」會在測試執行時，將所有收集的負載測試樣本資料多工緩衝處理至資料庫記錄。 像是計時詳細資料和錯誤詳細資料這類額外資料會在測試完成時載入至資料庫。

|工作|相關主題|
|-|-----------------------|
|**負載測試失敗時儲存記錄：** 您可以指定是否要在每次負載測試失敗時都儲存一次測試記錄。|-   [如何：指定測試失敗是否會儲存至測試記錄](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**設定記錄檔的檔案大小上限：** 您可以編輯與測試控制器服務建立關聯的 XML 組態檔，指定要用於記錄檔的檔案大小上限。|[如何：指定記錄檔的大小上限](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="see-also"></a>另請參閱

- [設定負載測試回合設定](../test/configure-load-test-run-settings.md)