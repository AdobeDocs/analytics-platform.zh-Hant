---
title: 比較跨Adobe Analytics和CJA報告功能的資料處理
description: 瞭解不同報告功能在資料處理方面的差異
exl-id: 9d20ef55-2caf-43f8-86e4-c66a490c6892
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 22%

---

# 比較跨Adobe Analytics和CJA報告功能的資料處理

瞭解不同報告功能在資料處理方面的差異有助於瞭解哪些指標在哪些位置可用，以及它們可能存在差異的原因。

例如，由於在資料處理時定義了Adobe Analytics中作為度量的&quot;訪問&quot;，而在報告時計算了CJA中作為度量的&quot;會話&quot;，因此，這兩個度量可能根據CJA資料視圖內用於會話定義的規則不同。

此外，在由分析源連接器建立的資料集中，訪問和會話均不可用作度量，因此需要在查詢邏輯中定義會話以進行比較。

## 術語 {#terms}

下表定義了適用於Adobe Analytics和CJA的不同類型處理邏輯的術語：

| 詞語 | 定義 | 附註 |
| --- | --- | --- |
| 處理時間邏輯 | 在處理資料時執行的邏輯，然後儲存用於報告和分析目的。 | 這一邏輯被&quot;烘焙&quot;到歷史資料中，通常不容易改變。 |
| 報告時間邏輯 | 運行報告時執行的邏輯。 | 此邏輯可以以非破壞性方式應用於報告運行時的未來資料和歷史資料。 |
| 命中級邏輯 | 在逐行級別應用的邏輯。 | 示例：處理規則、VISTA、某些營銷渠道規則。 |
| 訪問級邏輯 | 在訪問級別應用邏輯。 | 示例：訪問和會話定義。 |
| 訪問者級邏輯 | 在訪問者級別應用邏輯。 | 示例：跨設備/跨通道訪問者縫合。 |
| 段（篩選器）邏輯 | 評估命中/訪問/訪問者（事件/會話/人員）段（過濾器）規則。 | 示例：買紅鞋的人。 |
| 計算量度 | 評估客戶建立的自定義度量，該度量可以基於包括段和篩選器的複雜公式。 | 示例：買紅鞋的人數 |
| 歸因邏輯 | 計算屬性的邏輯。 | 示例：eVar持久性。 |

{style=&quot;table-layout:auto&quot;}

隨著時間的推移，Adobe Analytics和現在的Customer Journey Analytics通過允許在報告運行時執行訪問和訪問者級資料邏輯而提高了靈活性。

## 資料處理類型 {#types}

為Adobe Analytics和CJA執行的資料處理步驟以及這些步驟的時間安排因分析功能到分析功能而異。 下表提供了每個分析功能的資料處理類型以及應用資料處理時的資料處理類型摘要。

| 分析功能 | 在處理時應用 | 在報告時應用 | 不可用 | 附註 |
| --- | --- | --- | --- | --- |
| [核心AA](https://experienceleague.adobe.com/docs/analytics.html?lang=zh-Hant) 報告<br/>(不包括具有報告時處理的Attribution IQ或虛擬報告套件) | <ul><li>[處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hant)</li><li>[VISTA 規則](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>命中級 [營銷渠道規則](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=zh-Hant)</li><li>訪問級市場營銷渠道規則（請參閱注釋）</li><li>訪問定義</li><li>歸因邏輯</li></ul> | <ul><li>段邏輯</li><li>計算量度</li></ul> | <ul><li>跨設備分析（請參閱注釋）</li></ul> | <ul><li>CDA要求使用虛擬報告套件並進行報告時間處理。</li><li>「訪問級營銷渠道規則」包括以下內容： **是訪問的第一頁**。 **覆蓋上次觸摸通道**, **市場營銷渠道到期**。 (請參閱 [文檔](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant)。)</li></ul> |
| 核心AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>處理規則</li><li>VISTA 規則</li><li>目標級市場營銷渠道規則</li><li>訪問級市場營銷渠道規則</li><li>訪問定義</li><li>歸因邏輯</li></ul> | <ul><li>段邏輯</li></ul> | <ul><li>計算量度</li><li>跨裝置分析</li></ul> |  |
| 核心AA [資料源](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>處理規則</li><li>VISTA 規則</li><li>目標級市場營銷渠道規則</li><li>訪問級市場營銷渠道規則</li><li>訪問定義（visitnum欄位）</li><li>屬性邏輯（在後列中）</li></ul> |  | <ul><li>段邏輯</li><li>計算量度</li><li>跨裝置分析</li></ul> | <ul><li>資料源中某些與市場營銷渠道相關的列的ID映射不包括在資料源中。 (請參閱 [資料源文檔](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)。)</li></ul> |
| 核心AA [直播](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 處理規則</li><li>VISTA 規則</li><ul> |  | <ul><li>目標級市場營銷渠道規則</li><li>訪問級市場營銷渠道規則</li><li>訪問邏輯</li><li>歸因邏輯</li><li>段邏輯</li><li>計算量度</li><li>跨裝置分析</li></ul> |  |
| 核心AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hant) | <ul><li>處理規則</li><li>VISTA 規則</li><li>訪問定義（請參閱注釋）</li><li>跨設備分析（請參閱注釋）</li></ul> | <ul><li>主機級市場營銷渠道規則（請參閱附註）</li><li>訪問級市場營銷渠道規則（參閱附註）屬性邏輯</li><li>段邏輯</li><li>計算量度</li></ul> |  | <ul><li>CDA要求使用虛擬報告套件並進行報告時間處理。</li><li>Core Analytics中的Attribution IQ使用在報告時完全派生的營銷渠道（即派生的中值）。</li><li>Attribution IQ使用處理時間訪問定義，但在報告時間處理VRS中使用時除外。</li></ul> |
| 核心AA虛擬報告套件 [報告時間處理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant) (VRS RTP) | <ul><li>處理規則</li><li>VISTA 規則</li><li>[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hant)</li></ul> | <ul><li>訪問定義</li><li>歸因邏輯</li><li>段邏輯</li><li>計算量度</li><li>其他VRS RTP設定</li></ul> | <ul><li>目標級市場營銷渠道規則</li><li>訪問級市場營銷渠道規則</li></ul> | <ul><li>請參見VRS RTP [文檔](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en)。</li></ul> |
| [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)AEP資料湖中的基於資料集 | <ul><li>處理規則</li><li>VISTA 規則</li><li>目標級市場營銷渠道規則</li><li>基於欄位的縫合（請參閱注釋）</li></ul> |  | <ul><li>[訪問級市場營銷渠道規則](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>訪問邏輯</li><li>歸因邏輯</li><li>過濾邏輯</li></ul> | <ul><li>必須應用您自己的篩選器邏輯和計算的度量</li><li>基於欄位的縫合除了由分析源連接器建立的縫合資料集之外，還建立單獨的縫合資料集。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en) 報告 | <ul><li>處理規則</li><li>VISTA 規則</li><li>命中級 [營銷渠道規則](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[連線設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant)</li><li>基於欄位的縫合（請參閱注釋）</li></ul> | <ul><li>會話定義</li><li>[資料檢視設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hant)</li><li>歸因邏輯</li><li>計算量度</li><li>過濾邏輯</li></ul> | <ul><li>訪問級市場營銷渠道規則</li></ul> | <ul><li>必須使用縫合資料集才能利用基於欄位的縫合。</li></ul> |

{style=&quot;table-layout:auto&quot;&quot;
