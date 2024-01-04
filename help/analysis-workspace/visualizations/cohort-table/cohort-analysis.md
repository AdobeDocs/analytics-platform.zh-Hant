---
title: 同類群組分析是什麼？
description: 瞭解 Analysis Workspace 中的同類群組分析
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 67%

---

# 什麼是[!UICONTROL 同類群組分析]？

*`cohort`* 是指一段指定時間內，共享相同特徵的一組人。[!UICONTROL 例如當您想知道一個同類群組與某個品牌的互動關係時，就很適合使用同類群組分析。]您可輕易看出趨勢中的變化，然後據以做出回應。(網路上有[!UICONTROL 同類群組分析]的解釋可供參考，例如 [Cohort Analysis 101](https://zh.wikipedia.org/wiki/Cohort_analysis)。)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和篩選器)，接著將同類群組報表與他人共用。 請參閱[監管與共用](/help/analysis-workspace/curate-share/curate.md)。

[!UICONTROL 同類群組分析]的用途範例：

* 推行專為刺激所需動作的促銷活動。
* 在客戶生命週期的正確時間點轉移行銷預算。
* 識別何時應終止試用或優惠方案，以獲取最大價值。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。

所有具有 [!UICONTROL Analysis Workspace] 存取權限的 Customer Journey Analytics 客戶，皆可使用[!UICONTROL 同類群組分析]。

[「同類群組分析」影片教學課程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=zh-Hant) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL 同類群組分析] 不支援無法篩選的量度（包括計算量度）、非整數量度（例如收入）或發生次數。 只有可在篩選器中使用的量度，才可用於 [!UICONTROL 同類群組分析]，且只能以1為單位遞增。

## 同類群組分析功能

下列功能可讓您對您正在建立的同類群組進行微調控制：

### [!UICONTROL 保留率表格]

A [!UICONTROL 保留] 同類群組報表傳回人員：每個資料儲存格顯示該同類群組中，在該時段內執行了動作的原始人數和百分比。 您可以包含最多 3 個量度和最多 10 個篩選器。

![顯示同類群組中人員的單位和百分比的演繹版同類群組報告。](assets/retention-report.png)

### [!UICONTROL 流失率表格]

A [!UICONTROL 流失] 同類群組與保留率表格相反，會顯示在一段時間內離開或從未符合約類群組回傳標準的人員。 您可以包含最多 3 個量度和最多 10 個篩選器。

![顯示不符合約類群組回傳標準之人員的單位和百分比的流失表。](assets/churn-report.png)

### [!UICONTROL 滾動式計算]

可讓您根據上一欄計算保留率或流失率，而非根據包含欄。

![同類群組保留報表，顯示根據上一欄資料進行的計算。](assets/cohort-rolling-calculation.png)

### [!UICONTROL 延時表格]

衡量包含事件發生前後的經過時間。此工具非常適合用來進行事前/事後分析。**[!UICONTROL 包含]**&#x200B;欄位於表格的中央，包含事件前後的時段會顯示於兩側。

![顯示事件之前和之後經過時間的同類群組報表。](assets/cohort-latency.png)

### [!UICONTROL 自訂維度同類群組]

根據選取的維度建立同類群組，而非根據以時間為主的同類群組 (預設)。使用[!UICONTROL 行銷管道]、[!UICONTROL 行銷活動]、[!UICONTROL 產品]、[!UICONTROL 頁面]、[!UICONTROL 地區]等 Customer Journey Analytics  維度，說明保留率在不同維度值的變化。

![同類群組報表顯示具有選定維度的自訂報表，而非預設的時間型同類群組。](assets/cohort-customizable-cohort-row.png)

如需如何設定和執行同類群組報表的指示，請前往[設定同類群組分析報表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
