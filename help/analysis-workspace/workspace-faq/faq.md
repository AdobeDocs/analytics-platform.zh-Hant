---
description: 工作區常見問題和故障排除提示。
title: 常見問題集
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 78%

---

# 常見問題集

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[了解更多...](/help/getting-started/cja-aa.md)

| 問題 | 回答 |
|--- |--- |
| **使用 Analysis Workspace 的先決條件為何？** | 使用Analysis Workspace需要一項工作Customer Journey Analytics。 使用該工具之前，請確保您的組織正在向Adobe Experience Platform發送資料。 |
| **Analysis Workspace 的管理和存取需求為何？** | 請參閱[管理需求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| **使用 Analysis Workspace 是否會影響資料收集？** | Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到 Workspace 專案中，了解哪一種組合適合自己。如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。您也可以按一下左上方選單中的&#x200B;*[!UICONTROL 「專案] > [!UICONTROL 新專案」]*，以空白顯示窗開始操作。 |
| **如何實施Analysis Workspace?** | 不需要特別實作。Analysis Workspace可供所有公司Customer Journey Analytics。 但是，對內容（如項目元件）的標準權限將應用，並用於建立和共用項目。 請參閱[管理和存取需求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| **如何最佳化 Analysis Workspace 的效能？** | 請參閱[效能最佳化](/help/analysis-workspace/workspace-faq/optimizing-performance.md)。 |

## 疑難排解

**我將量度拖曳到專案後，系統顯示「資料無效」。**

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。

**我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。**

如果您成功建立了 Workspace 報表，但當中沒有任何資料，建議您檢查以下幾個事項：

* 如果在報表中應用了篩選器，則篩選條件可能與任何資料都不匹配。 嘗試刪除篩選器或調整篩選器定義。
* 檢查右上角的日期範圍，確認已設為您預期的值。
* 導覽至您的網站，使用[除錯工具](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hant)驗證資料正在收集中。
