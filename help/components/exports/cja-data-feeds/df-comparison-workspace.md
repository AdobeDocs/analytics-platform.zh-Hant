---
description: 瞭解如何比較Customer Journey Analytics和Adobe Analytics中的資料摘要功能
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: 比較Customer Journey Analytics和Adobe Analytics中的資料摘要功能
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# 瞭解資料摘要和Analysis Workspace之間的資料差異

{{release-limited-testing}}

資料摘要匯出中的資料並不一定與您在Analysis Workspace中看到的資料完全相符。 本頁資訊說明部分主要原因。

這些差異部分來自Workspace行為，單獨在Workspace報表中很難看到，因為Workspace資料是彙總的。 資料摘要會提供事件層級的資料，因此當您比較資料摘要輸出與Workspace報表時，這些行為會變得明顯。

## 處理期間（資料摘要）與報告期間(Analysis Workspace)的比較 {#processing-window}

每個資料摘要傳送都會使用滾動式30天處理期間。 處理視窗會提供分類資料摘要傳送中的事件所需的歷史內容。 如需有關處理視窗的詳細資訊，包括範例，請參閱[瞭解處理視窗](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window)。

從這個角度來看，處理期間類似於Analysis Workspace中的報告期間（您為報告選擇的日期範圍）。 不過，兩者之間還是有主要差異。

| 主要差異 | 報告期間(Analysis Workspace) | 處理視窗（資料摘要） |
|---------|---------|----------|
| **報告的時間範圍**<br/>&#x200B;哪些事件包含在報告或摘要中 | 從報表期間開始的日曆月第一天開始，並在報表期間結束時結束。<p>例如，報表期間為10月6日至11月5日的報表也包含10月1日至10月5日的事件。 由於Workspace資料會經過彙總，因此很難注意到這些額外事件。</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | 與處理期間不同。 <p>要報告的時間範圍是頻率視窗，可以是處理視窗結尾的一小時或一天。</p> |
| **資料界限**<br/>&#x200B;視窗外的資料是否包含在報表或摘要中，或是否會影響報表或摘要 | 彈性<p>報表時段開始的日曆月第一天事件，即使落於報表時段之前，也會納入Workspace報表中。 如需詳細資訊，請參閱上述&#x200B;**報告的時間範圍**。</p><p>在報告期間之外的事件也會透過下列任何因素影響Workspace報告中的資料：</p><ul><li>**Dimension持續性**：使用工作階段、自訂時間或量度[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，可以持續超過報告期間。</li><li>**區段資格**：依預設，區段可延伸超過報告期間。<p>使用者建立區段時，可以選擇將區段限制在報告期間。 即使到那時，區段資格也會考量報表時段開始的日曆月第一天的事件。</p></li><li>**工作階段計算**：工作階段可以超出報告期間。 </li><li>**衍生欄位轉換**：參考容器的任何衍生欄位函式都會使用報告視窗。<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | 固定<p>只有頻率視窗中的事件會包含在資料摘要中。 如需詳細資訊，請參閱上述&#x200B;**報告的時間範圍**。</p><p>落於頻率視窗之外、但位於處理視窗中的事件可能會影響資料摘要中的資料。 落在處理期間之前的事件通常無法處理。 處理視窗會限制下列因素：</p><ul><li>**Dimension持續性**：使用工作階段、人員報告時段或量度[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，無法持續存在超過處理時段。 與Workspace不同，回顧期間不會延長至當月的第一天。 使用自訂時間[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，在處理期間（最長90天）之後仍可持續存在，與Workspace中相同。 在Workspace和資料摘要中，自訂時間回顧不會延伸至該月的第一天。<p>**注意：**&#x200B;目前，自訂時間過期時間也僅限於處理期間。 即將支援超出處理期間的自訂時間。</p></li><li>**區段資格**：一律限於處理期間。 與Workspace不同，不會延續至當月的第一天。</li><li>**工作階段計算**：一律限於處理期間。</li><li>**衍生欄位轉換**：參考容器的任何衍生欄位函式都會在資料摘要匯出中使用處理視窗。</li></ul> |

>[!BEGINSHADEBOX]

**範例**

以下範例說明報表時段與處理時段之間的差異，如何造成Workspace報表與資料摘要傳送之間的資料差異。

* **於**&#x200B;報告的時間範圍：使用者在10月1日有一個事件設定維度值，以及更多在10月之後的事件。 Workspace報表的報告期間從10月6日開始，其中包含10月1日事件，因為Workspace包含該月第一天的事件。 10月1日設定的值也可保留至報告期間的使用者事件。 具有從10月6日開始處理視窗的資料摘要傳送不會考慮10月1日事件，因此其設定的值不會持續至傳送中的使用者事件。

* **區段資格**： 45天前具有人員容器且今天有事件的使用者符合區段資格。 具有30天報告時段的Workspace報表包含使用者事件，因為區段預設會超出報告時段。 今天的資料摘要傳送不包含事件，因為區段資格僅限30天的處理期間。

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## 拼接重播

每次執行拼接重播時，都會回溯更新歷史身分資料。

資料摘要和Analysis Workspace對銜接重播的處理方式不同，如下所示：

* **資料摘要**：僅反映匯出時拼接的身分。 系統不會將重播結果回溯套用至匯出的檔案。

* **Analysis Workspace**：顯示最新的彙整資料，每次執行重播時都會回溯更新。 每次重播後，歷史資料都會變更，因此Workspace一律會反映最新的身分解析度。

## 延遲送達事件

在資料摘要中，事件可能會在資料摘要匯出視窗關閉後到達。

資料摘要和Analysis Workspace對於過去事件的運作方式不同，如下所示：

* **資料摘要**：根據事件時間戳記，匯出固定時間範圍內（每個傳遞的小時或一天）的資料。

  在處理每個傳遞前，Customer Journey Analytics會等待您選擇的[處理延遲](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay)。 在處理延遲期間到達的事件會包含在傳送中。 處理開始後抵達的事件，不會納入資料摘要檔案中。

* **Analysis Workspace**：在報告時處理資料，因此無論事件是在何時收到，都會將其包含在報告中。

## 資料批次

有時資料會以跨越較長時段的批次提交。

資料摘要和Analysis Workspace對批次資料的運作方式不同，如下所示：

* **資料摘要**：根據原始時間戳記，將批次資料分散到每天或每小時。 例如，包含30天資料的批次會分散在匯出30天中，因此在任何單一匯出中都會只顯示很小的片段。

* **Analysis Workspace**：在批次完全處理完畢後立即顯示批次中的所有資料，無論批次中包含的時間範圍為何。

