---
title: 同類群組分析是什麼？
description: 瞭解分析工作區中的同類群組分析
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 45%

---


# What is [!UICONTROL Cohort Analysis]?

>[!NOTE]
>
>您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

*`cohort`* 是指一段指定時間內，共享相同特徵的一組人。[!UICONTROL 例如當您想知道一個同類群組與某個品牌的互動關係時，就很適合使用同類群組分析。]您可輕易看出趨勢中的變化，然後據以做出回應。(Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和區段)，接著將同類群組報表與他人共用。請參閱[組織與共用](/help/analysis-workspace/curate-share/curate.md)。

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* 推行專為刺激所需動作的促銷活動。
* 在客戶生命週期的正確時間點轉移行銷預算。
* 識別何時結束試用版或優惠，以發揮最大價值。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。
* View a [!UICONTROL Cohort Analysis] report within a Guided Analysis report.

[!UICONTROL 世代分析] (Choort Analysis)適用於所有擁有分析工作區存取權的Adobe Analytics [!UICONTROL 客戶]。

[在 YouTube 觀看「同類群組分析」](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)(4:36)

>[!IMPORTANT]
>
>[!UICONTROL 同類群組分析]
>
>不支援非篩選量度（包括計算量度）、非整數量度（例如收入）或發生次數。 只有可用於區段的量度可用於
>[!UICONTROL 同類群組分析]，而且每次只能增加1。

## 同類群組分析功能

下列功能可讓您對您正在建立的群組進行微調控制：

### [!UICONTROL 保留率表格]

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. 您可以包含最多 3 個量度和最多 10 個區段。

![](assets/retention-report.png)

### [!UICONTROL 流失率表格]

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. 您可以包含最多 3 個量度和最多 10 個區段。

![](assets/churn-report.png)

### [!UICONTROL 滾動式計算]

可讓您根據上一欄計算保留率或流失率，而非根據包含欄。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 延時表格]

衡量包含事件發生前後的經過時間。此工具非常適合用來進行事前/事後分析。The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL 自訂維度同類群組]

根據選取的維度建立同類群組，而非根據以時間為主的同類群組 (預設)。Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

如需如何設定及執行同類群組報表的指示，請前往「設 [定同類群組分析」報表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

