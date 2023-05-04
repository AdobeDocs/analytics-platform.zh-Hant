---
title: 比較 Adobe Analytics 和 CJA 報告功能的資料處理
description: 了解各種報告功能的資料處理差異
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: d075f3d2b4436c668010e09c6d1ac3191edac241
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 75%

---

# 比較Adobe Analytics和Customer Journey Analytics的資料處理方式。

您通常需要先處理資料，才能讓資料對報表有用。 您可以在歷程的數個階段處理該資料，這些階段涵蓋從收集資料到產生報表或視覺效果。

在Adobe Analytics中，大部分的資料處理都是在收集資料後立即進行。 支援此功能包括VISTA規則、處理規則、行銷管道處理規則 **收集時間處理**.
然後會儲存資料，您就可以在報告時套用其他處理。 例如，劃分維度、套用分段或選取不同的歸因模型。 此 **報表時間處理** 是在飛行。

在Adobe Analytics中，報表時間處理通常代表的處理量比收集時間所發生的少。

![Adobe Analytics收集時間處理](../assets/aa-processing.png)

相反地，Customer Journey Analytics(CJA)的設計目的，是在組織和儲存資料之前，需要最少的前期收集時間處理。 CJA的基礎架構更適合在報表時處理儲存的資料，不僅可在工作區中提供其強大的報表時間處理功能，更重要的是，可透過 [元件](/help/data-views/component-settings/overview.md) 和 [衍生欄位](/help/data-views/derived-fields/derived-fields.md) 在資料檢視中。

![CJA報表時間處理](../assets/cja-processing.png)

了解各種報告功能的資料處理差異，有助於了解哪些量度可用於哪裡，以及其不同的原因。

例如，由於 Adobe Analytics 中的「造訪」量度是在資料處理時定義的，而 CJA 中的「工作階段」是在報告時計算的，根據 CJA 資料檢視中用於工作階段定義的規則，這兩個量度就可能有所不同。

此外，在 Analytics 來源連接器建立的資料集中，造訪和工作階段量度均不可用，因此需要您在查詢邏輯中定義工作階段才能進行比較。

## 術語 {#terms}

下表定義套用至 Adobe Analytics 和 CJA 之不同處理邏輯類型的術語：

| 詞語 | 定義 | 附註 |
| --- | --- | --- |
| 收集時間處理 | 在收集和處理資料時執行的邏輯，然後儲存以供報告和分析之用。 | 這個邏輯被「寫入」歷史資料，通常不容易改變。 |
| 報表時間處理 | 執行報告時執行的邏輯。 | 此邏輯可以在報告執行階段，以非破壞性方式套用至未來和歷史資料。 |
| 點擊層級邏輯 | 在逐列層級套用的邏輯。 | 範例：處理規則、VISTA、某些行銷頻道規則。 |
| 造訪層級邏輯 | 在造訪層級套用的邏輯。 | 範例：造訪和工作階段定義。 |
| 訪客層級邏輯 | 在訪客層級套用的邏輯。 | 範例：跨裝置/跨頻道訪客聯繫。 |
| 區段 (篩選器) 邏輯 | 評估點擊/造訪/訪客 (事件/工作階段/人員) 區段 (篩選器) 規則。 | 範例：買紅鞋子的人。 |
| 計算量度 | 評估客戶建立的自訂量度，這些量度可以根據複雜的公式，包括區段和篩選器。 | 範例：買紅鞋子的人數。 |
| 歸因邏輯 | 計算歸因的邏輯。 | 範例：eVar 持續性。 |
| 元件設定 | 將自訂套用至量度或維度，例如歸因、行為、格式等 | 範例：值分段以根據範圍組合數值 |
| 自訂欄位 | 邏輯會套用至結構或標準欄位，作為定義資料檢視中元件的一部分。 | 範例：建立新的行銷管道維度 |

{style="table-layout:auto"}

長期下來，Adobe Analytics 和現在的 Customer Journey Analytics 允許在報告執行階段執行造訪和訪客層級的資料邏輯，因此提高了靈活性。

## 資料處理的類型 {#types}

Adobe 和 CJA 執行的資料處理步驟以及這些步驟的使用時機，因 Analytics 功能而異。下表概述每個 Analytics 功能的資料處理類型，以及套用資料處理的時機。

| 功能 | 在處理時套用 | 在報告時套用 | 未提供 | 附註 |
| --- | --- | --- | --- | --- |
| [核心 AA](https://experienceleague.adobe.com/docs/analytics.html?lang=zh-Hant) 報告<br/>(不包括 Attribution IQ 或具有報告時間處理功能的虛擬報告套裝) | <ul><li>[處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hant)</li><li>[VISTA 規則](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=zh-Hant)</li><li>點擊層級[行銷頻道規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=zh-Hant)</li><li>造訪層級行銷頻道規則 (請見附註)</li><li>造訪定義</li><li>歸因邏輯</li></ul> | <ul><li>區段邏輯</li><li>計算量度</li></ul> | <ul><li>跨裝置分析 (請見附註)</li></ul> | <ul><li>CDA 需要使用或具有報告時間處理功能的虛擬報告套裝。</li><li>「造訪層級行銷頻道規則」包括以下項目：**是第一個造訪的頁面**、**覆寫最近一次接觸頻道**&#x200B;和&#x200B;**行銷頻道到期**。(請參閱[文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant))。</li></ul> |
| 核心 AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=zh-Hant) | <ul><li>處理規則</li><li>VISTA 規則</li><li>點擊層級行銷頻道規則</li><li>造訪層級行銷頻道規則</li><li>造訪定義</li><li>歸因邏輯</li></ul> | <ul><li>區段邏輯</li></ul> | <ul><li>計算量度</li><li>跨裝置分析</li></ul> |  |
| 核心 AA [資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=zh-Hant) | <ul><li>處理規則</li><li>VISTA 規則</li><li>點擊層級行銷頻道規則</li><li>造訪層級行銷頻道規則</li><li>造訪定義 (visitnum 欄位)</li><li>歸因邏輯 (在後置欄中)</li></ul> |  | <ul><li>區段邏輯</li><li>計算量度</li><li>跨裝置分析</li></ul> | <ul><li>資料摘要中某些與行銷頻道相關欄的 ID 對應不包含在資料摘要中。(請參閱[資料摘要文件](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant))。</li></ul> |
| 核心 AA [直播串流](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 處理規則</li><li>VISTA 規則</li><ul> |  | <ul><li>點擊層級行銷頻道規則</li><li>造訪層級行銷頻道規則</li><li>造訪邏輯</li><li>歸因邏輯</li><li>區段邏輯</li><li>計算量度</li><li>跨裝置分析</li></ul> |  |
| 核心 AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hant) | <ul><li>處理規則</li><li>VISTA 規則</li><li>造訪定義 (請見附註)</li><li>跨裝置分析 (請見附註)</li></ul> | <ul><li>點擊層級行銷頻道規則 (請見附註))</li><li>造訪層級行銷頻道規則 (請見附註) 歸因邏輯</li><li>區段邏輯</li><li>計算量度</li></ul> |  | <ul><li>CDA 需要使用或具有報告時間處理功能的虛擬報告套裝。</li><li>核心 Analytics 中的 Attribution IQ 使用在報告時完全衍生的行銷頻道 (即衍生的中間值)。</li><li>Attribution IQ 使用處理時間造訪定義，除非用於報告時間處理 VRS 中。</li></ul> |
| 具有[報告時間處理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant) 的核心 AA 虛擬報告套裝 (VRS RTP) | <ul><li>處理規則</li><li>VISTA 規則</li><li>[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hant)</li></ul> | <ul><li>造訪定義</li><li>歸因邏輯</li><li>區段邏輯</li><li>計算量度</li><li>其他 VRS RTP 設定</li></ul> | <ul><li>點擊層級行銷頻道規則</li><li>造訪層級行銷頻道規則</li></ul> | <ul><li>請參閱 VRS RTP [文件](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant)。</li></ul> |
| AEP 資料湖中的 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)型資料集 | <ul><li>處理規則</li><li>VISTA 規則</li><li>點擊層級行銷頻道規則</li><li>欄位式拚接 (請見附註)</li></ul> |  | <ul><li>[造訪層級行銷頻道規則](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant)</li><li>造訪邏輯</li><li>歸因邏輯</li><li>篩選器邏輯</li></ul> | <ul><li>必須套用您自己的篩選器邏輯和計算量度</li><li>除了由 Analytics 來源連接器建立的資料集之外，欄位式拚接還會建立一個單獨的拼接資料集。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hant) 報告 | <ul><li>作為Adobe Experience Platform資料收集的一部分實作</li></ul> | <ul><li>工作階段定義</li><li>[資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hant)設定<li>歸因邏輯</li><li>計算量度</li><li>篩選器邏輯</li></ul> | <ul><li>造訪層級行銷頻道規則</li></ul> | <ul><li>必須使用匯整的資料集，才能善用跨管道分析。</li></ul> |

{style="table-layout:auto"}
