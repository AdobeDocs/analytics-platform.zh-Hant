---
title: 同類群組表格概觀
description: 瞭解如何深入瞭解您的對象資料，並透過同類群組分析將這些資料分成相關的群組。 在Analysis Workspace中使用同類群組分析。
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 91%

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
>abstract="根據事件的完成情形將使用者分組，然後分析他們在一段時間內的持續參與度及流失情況。指定其他設定，例如顆粒度、同類群組分析類型以及是否使用滾動計算。您可以設定進階選項，根據所選維度建立延遲表格或自訂維度同類群組。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中的同類群組表格。_<br/>_請參閱本文中 ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_&#x200B;**Adobe Analytics**&#x200B;版本的[同類群組表格](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)_。_

>[!ENDSHADEBOX]


*同類群組*&#x200B;是指一段指定時間內，共用相同特徵的一組人。例如，當您想要了解同類群組與某個品牌的互動關係時，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同類群組表格]** 視覺效果非常實用。您可輕易看出趨勢中的變化，然後據以做出回應。(網路上有[!UICONTROL 同類群組分析]的解釋可供參考，例如 [Cohort Analysis 101](https://zh.wikipedia.org/wiki/Cohort_analysis)。)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和區段)，接著將同類群組報表與他人共用。請參閱[監管與共用](/help/analysis-workspace/curate-share/curate.md)。

[!UICONTROL 同類群組表格]的用途範例：

* Launch促銷活動專為刺激所需動作而設計。
* 在客戶生命週期的正確時間轉移行銷預算。
* 識別何時終止試用版或產品建議，以價值最大化。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。

所有具有 [!UICONTROL Analysis Workspace] 存取權限的 Customer Journey Analytics 客戶，皆可使用[!UICONTROL 同類群組表格]。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的同類群組分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}的示範影片。

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL 同類群組分析]不支援無法設為區段的量度 (包括計算量度)、非整數量度 (例如營收)，或者發生次數。唯有可在區段中使用的量度才能用於[!UICONTROL 同類群組分析]，且這些量度一次只能遞增 1。

Customer Journey Analytics 中的同類群組表格支援雙精型 (或任何數值型) 的量度。例如，Purchase.Value (雙精度) 可用於包含/回報量度。此外，透過 Analytics 來源連接器傳遞至 Adobe Experience Platform 的所有量度皆為雙精度。

## 同類群組表格功能

下列區段說明同類群組分析功能，可對您正在建立的同類群組進行微調控制。

有關建立同類群組和執行[!UICONTROL 同類群組分析]報告的更多資訊，請參閱[設定同類群組表格](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### 保留率表格

[!UICONTROL 保留率]同類群組表格回傳人數：每個資料儲存格顯示此同類群組中，在該時段內執行動作的原始人數和百分比。您可以納入最多 3 個量度和最多 10 個區段。

![保留率同類群組報告顯示同類群組中的人員單位和百分比。](assets/retention-report.png)

### 流失率表格

[!UICONTROL 流失率]同類群組表格和保留率表格相反，會顯示在特定時間內離開或從未符合同類群組回傳條件的人員。您可以納入最多 3 個量度和最多 10 個區段。

![流失率表格顯示不符合同類群組回傳標準的人員單位和百分比。](assets/churn-report.png)

### 滾動式計算

您可以根據前一欄而非將欄納入來計算保留率或流失率，稱為滾動式計算。

![同類群組保留率報告顯示根據資料前一欄的計算。](assets/retention-report-rolling.png)

### 延遲表

延遲表格測量包括事件發生前後經過的時間。測量延遲是進行事前/事後分析的絕佳工具。**[!UICONTROL 包含]**&#x200B;欄位於表格的中央，包含事件前後的時段會顯示於兩側。

![同類群組報告顯示事件前後經過的時間。](assets/retention-report-latency.png)

### 自訂維度同類群組

您可以根據選取的維度建立同類群組，而非根據以時間為基礎的同類群組 (預設)。使用以下維度，例如[!UICONTROL 城市地理]、[!UICONTROL 行銷管道]、[!UICONTROL 行銷活動]、[!UICONTROL 產品]、[!UICONTROL 頁面]、[!UICONTROL 地區]，或任何其他維度來顯示保留率如何變更。根據這些維度不同的值。

![同類群組報告顯示使用選取維度的自訂報告，而非預設以時間為基礎的同類群組。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[設定同類群組表格](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

