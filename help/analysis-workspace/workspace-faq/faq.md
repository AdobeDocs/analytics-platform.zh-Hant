---
description: Workspace 常見問答集
title: 常見問題與疑難排解工作區
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 56%

---


# 常見問題集

>[!NOTE] 您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

| 問題 | 回答 |
|--- |--- |
| 使用分析工作區的先決條件為何？ | 使用分析工作區需要有效的客戶歷程分析實施。 請確定您的組織在使用該工具之前，已將資料傳送至Adobe Experience Platform。 |
| Analysis Workspace 的管理和存取需求為何？ | 請參閱[管理需求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 使用分析工作區是否會影響資料收集？ | Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到 Workspace 專案中，了解哪一種組合適合自己。如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。您也可以按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案]>[!UICONTROL 新專案」]*，以空白顯示窗開始操作。 |
| 如何實施 Analysis Workspace？ | 不需要特別實施。「分析工作區」適用於所有客戶歷程分析公司。 但是，內容（例如專案元件）的標準權限會套用，而且適用於組織和共用專案。 請參閱[管理和存取需求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 如何最佳化 Analysis Workspace 的效能？ | 請參閱[效能最佳化](/help/analysis-workspace/workspace-faq/optimizing-performance.md)。 |

## 疑難排解

**我將量度拖曳到專案後，系統顯示「資料無效」。**

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。請改為並排放置量度。

**我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。**

如果您成功建立工作區報表，但沒有資料，您可以檢查以下幾項：

* 再次檢查報表套裝，並確認其已填入資料。
* 如果您在報表中套用區段，區段標準可能不符合任何資料。 請嘗試移除區段或調整區段定義。
* 檢查右上角的日期範圍，並確定它已設為您預期的值。
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.