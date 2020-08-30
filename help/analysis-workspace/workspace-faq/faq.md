---
description: 工作區常見問答集
title: 常見問題集和疑難排解工作區
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 87%

---


# 常見問題集

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

| 問題 | 回答 |
|--- |--- |
| 使用 Analysis Workspace 的必要條件為何？ | 使用分析工作區需要有效的客戶歷程分析實施。 請確定您的組織在使用該工具之前，已將資料傳送至Adobe Experience Platform。 |
| Analysis Workspace 的管理和存取需求為何？ | 請參閱[管理需求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 使用 Analysis Workspace 是否會影響資料收集？ | Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到工作區專案中，瞭解哪一種組合適合自己。如果您意外將無效的元件拖曳到工作區專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。您也可以按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案]>[!UICONTROL 新專案」]*，以空白顯示窗開始操作。 |
| 如何實施 Analysis Workspace？ | 不需要特別實施。「分析工作區」適用於所有客戶歷程分析公司。 但是，內容（例如專案元件）的標準權限會套用，而且適用於組織和共用專案。 請參閱[管理和存取需求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 如何最佳化 Analysis Workspace 的效能？ | 請參閱[效能最佳化](/help/analysis-workspace/workspace-faq/optimizing-performance.md)。 |

## 疑難排解

**我將量度拖曳到專案後，系統顯示「資料無效」。**

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。

**我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。**

如果您成功建立了工作區報表，但當中沒有任何資料，建議您檢查以下幾個事項：

* 仔細檢查報表套裝，確認報表中已填入資料。
* 如果您在報表中套用了區段，則可能是區段標準與任何資料皆不符。請嘗試移除區段或調整區段定義。
* 檢查右上角的日期範圍，確認已設為您預期的值。
* 導覽至您的網站，使用[除錯工具](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html)驗證資料正在收集中。