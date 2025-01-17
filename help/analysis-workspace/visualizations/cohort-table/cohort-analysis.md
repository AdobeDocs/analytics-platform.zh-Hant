---
title: 同類群組表格概觀
description: 瞭解如何在Analysis Workspace中使用同類群組表格進行同類群組分析
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 353993c14103906553d87738ed3f7fc0926e123c
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 30%

---

# 同類群組表格概觀 {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="同類群組表格"
>abstract="建立同類群組視覺效果，根據事件的完成情形將使用者分組，並分析一段時間內的持續參與度和流失情況。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="同類群組表格"
>abstract="根據事件的完成情形將使用者分組，然後分析他們在一段時間內的持續參與度及流失情況。<br/><br/>**參數&#x200B;**<br/>**包含條件**：這些元件用以定義初始訪客同類群組。<br/>**回訪條件**：這些元件用以判斷訪客是否已回訪。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*本文會以&#x200B;**Customer Journey Analytics**記錄同類群組表格。<br/>檢視此文章的&#x200B;**Adobe Analytics**版本的[同類群組表格](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)。*

>[!ENDSHADEBOX]


*同類群組*&#x200B;是指一段指定時間內，共用相同特徵的一組人。 例如，當您想要瞭解同類群組與品牌的互動關係時，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同類群組表格]**&#x200B;視覺效果就很實用。 您可輕易看出趨勢中的變化，然後據以做出回應。(網路上有[!UICONTROL 同類群組分析]的解釋可供參考，例如 [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis)。)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和篩選器)，接著將同類群組報表與他人共用。 請參閱[監管與共用](/help/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同類群組表格]可以做的事情範例：

* 推行專為刺激所需動作的促銷活動。
* 在客戶生命週期的正確時間點轉移行銷預算。
* 識別何時結束試用或優惠方案，以最大化價值。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。

[!UICONTROL 同類群組表格]適用於具有[!UICONTROL Analysis Workspace]存取許可權的所有Customer Journey Analytics客戶。

+++ 觀看同類群組表格的影片示範。

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>[!UICONTROL 同類群組分析]不支援無法篩選的量度（包括計算量度）、非整數量度（例如收入）或發生次數。 只有可以在篩選器中使用的量度才能用於[!UICONTROL 同類群組分析]，而且這些量度一次只能增加1。

Customer Journey Analytics中的同類群組表格支援雙向（或任何數值型）量度。 例如，Purchase.Value (a double)可作為包含/傳回量度使用。 此外，所有透過Analytics Source Connector傳入Adobe Experience Platform的量度也是兩倍。

## 同類群組表格功能

以下幾節將說明同類群組分析功能，這些功能可讓您對您正在建立的同類群組進行微調控制。

如需建立同類群組及執行[!UICONTROL 同類群組分析]報表的詳細資訊，請參閱[設定同類群組表格](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### [!UICONTROL 保留率]資料表

[!UICONTROL 保留率]同類群組表格會傳回人員：每個資料儲存格顯示該同類群組中，在該時段內執行了動作的原始人數和百分比。 您可以包含最多 3 個量度和最多 10 個篩選器。

![顯示同類群組中人員的單位和百分比的演繹版同類群組報告。](assets/retention-report.png)

### [!UICONTROL 流失率]資料表

[!UICONTROL 流失率]同類群組表格與保留率表格相反，會顯示在一段時間內離開或從未符合約類群組回傳條件的人員。 您可以包含最多 3 個量度和最多 10 個篩選器。

![顯示不符合約類群組回傳條件之人員的單位與百分比的流失率表格。](assets/churn-report.png)

### [!UICONTROL 滾動式計算]

您可以根據上一欄計算保留率或流失率，而非根據「包含」欄（即滾動式計算）。

![同類群組保留率報表顯示根據上一欄資料進行的計算。](assets/retention-report-rolling.png)

### [!UICONTROL 延遲]資料表

延時表格會衡量包含事件發生前後的經過時間。 測量延遲是進行事前和事後分析的絕佳工具。 **[!UICONTROL 包含]**&#x200B;欄位於表格的中央，包含事件前後的時段會顯示於兩側。

![顯示事件前後經過時間的同類群組報告。](assets/retention-report-latency.png)

### [!UICONTROL 自訂維度]同類群組

您可以根據選取的維度建立同類群組，而非根據以時間為主的同類群組（預設）。 使用如[!UICONTROL 城市地理]、[!UICONTROL 行銷管道]、[!UICONTROL 行銷活動]、[!UICONTROL 產品]、[!UICONTROL 頁面]、[!UICONTROL 地區]等維度，或任何其他維度，來顯示保留率有何變更。 根據這些維度的不同值。

![顯示自訂報表的同類群組報表，其中包含已選取的維度，而非預設的時間型同類群組。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[設定同類群組表格](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

