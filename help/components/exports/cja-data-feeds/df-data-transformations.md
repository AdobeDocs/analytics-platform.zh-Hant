---
title: 為資料摘要套用資料轉換
description: 瞭解透過元件設定、衍生欄位或SQL轉換資料摘要資料的不同方式。
hide: true
feature: Components
source-git-commit: 6400a6bfcd65bee012beaf39aca873b2f225e45e
workflow-type: tm+mt
source-wordcount: '1594'
ht-degree: 5%
---
# 為資料摘要套用資料轉換

{{release-limited-testing}}

您可以使用下列任何一種方法來轉換資料摘要資料：

* [資料檢視元件設定](/help/data-views/component-settings/overview.md)

* [衍生欄位](/help/data-views/derived-fields/derived-fields.md)

* SQL

每種方法都有優缺點。 以下各節會比較一般和特定轉換之間的權衡。

## 比較一般資料轉換方法

下表比較各方法的一般優缺點。

| 方法 | 優點 | 缺點 |
| --- | --- | --- |
| **元件設定** | <ul><li>已在報告時套用，在傳遞資料摘要之前。</li><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</li><li>不會使用您帳戶中一個有限的衍生欄位。</li><li>您可以使用的元件設定數量沒有限制。</li></ul> | <ul><li>僅適用於每個元件支援的特定設定集。 不如使用衍生欄位建置自訂邏輯靈活。</li></ul> |
| **衍生欄位** | <ul><li>已在報告時套用，在傳遞資料摘要之前。</li><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</li><li>支援比任何單一元件設定（例如鏈結條件規則）更靈活的自訂邏輯。</li><li>有些轉換，特別是依賴範圍設定或剖析URL的轉換，很難在SQL中複製。</li></ul> | <ul><li>增加處理額外負荷，這會影響資料摘要傳遞效能。<!--Under a future usage-based pricing model, this could also add cost.--></li><li>使用您帳戶的其中一個有限衍生欄位。 如果元件設定可以執行相同的轉換，請改用。</li></ul> |
| **SQL** | <ul><li>不受適用於衍生欄位的函式和運運算元限制。</li><li>對資料摘要的傳送效能沒有影響。</li></ul> | <ul><li>已在您的資料摘要傳遞後套用。</li><li>邏輯不適用於Analysis Workspace，因此您需要在該處分別複製邏輯。</li><li>有些轉換很難複製或不切實際，尤其是依賴範圍設定、剖析URL或跨範圍刪除重複或保留值的轉換。</li></ul> |

{style="table-layout:auto"}

## 依轉換型別比較資料轉換方法

下表列出特定的資料轉換，顯示哪些方法（或方法）可以執行每個方法、在SQL中復寫會有多困難，以及建議使用哪種方法。<!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| 轉換 | 元件設定 | 衍生欄位 | SQL中的困難 | 建議的方法 | 考量事項 |
| --- | --- | --- | --- | --- | --- |
| **依條件套用條件邏輯或篩選值** | [包含排除值](/help/data-views/component-settings/include-exclude-values.md) | [案例時間](/help/data-views/derived-fields/derived-fields.md#casewhen) | 輕鬆使用字串<p>量度的中等到困難（需要結合`COUNT`的`CASE`陳述式）</p> | 元件設定<p>建議使用，因為它不會使用其中一個有限的衍生欄位。</p> | |
| 成功事件的&#x200B;**屬性評分** | [歸因](/help/data-views/component-settings/attribution.md) | 未提供 | 不適用 | 元件設定 | 僅適用於資料摘要中的維度。 量度沒有資料摘要行為需要復寫。 |
| **將數值儲存至範圍** | [值分組](/help/data-views/component-settings/value-bucketing.md) | 手動[案例時間](/help/data-views/derived-fields/derived-fields.md#casewhen) | 困難 | 元件設定<p>為方便使用而建議，因為它不會使用您有限的衍生欄位之一。</p> | 從元件設定（最簡單）增加到衍生欄位（一般，使用手動Case When）增加到SQL （最複雜）。 |
| **使用查閱樣式對應來分類值** | 未提供 | [分類](/help/data-views/derived-fields/derived-fields.md#classify) | 簡易/適中 | 衍生欄位 <p>建議使用，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | |
| **結合欄位值與分隔符號** | 未提供 | [串連](/help/data-views/derived-fields/derived-fields.md#concatenate) | 簡易/適中 | 衍生欄位<p>建議使用，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | 映象將多個維度欄新增至自由表格的功能，該功能限製為完整表格匯出。 衍生欄位讓類似的輸出可在資料摘要中使用。 |
| **轉換欄位的資料型別** | 未提供 | [型別廣播](/help/data-views/derived-fields/derived-fields.md#typecast) | 簡易/適中 | 衍生欄位<p>建議使用，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | |
| **計算量度發生次數（值與執行個體的比較）** | [行為](/help/data-views/component-settings/behavior.md) | 自訂數學因應措施 | 簡易/適中 | 元件設定<p>建議使用，因為：</p><ul><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中（使用SQL時則不可能）</li><li>它不會佔用您其中一個有限的衍生欄位。</li></ul> | |
| **在領域內刪除重複值** | [量度重複資料刪除](/help/data-views/component-settings/metric-deduplication.md) | [重複資料刪除](/help/data-views/derived-fields/derived-fields.md#dedup) | 困難 | 元件設定<p>建議使用，因為它不會使用其中一個有限的衍生欄位。</p> | 取決於範圍設定。 請參閱[範圍設定如何影響資料摘要](#scope-settings)。 |
| **決定工作階段中的欄位深度** | 未提供 | [深度](/help/data-views/derived-fields/derived-fields.md#depth) | 困難 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). How the counter behaves when a session spans a feed-delivery boundary is still being confirmed with engineering. --> <p>取決於範圍設定（使用工作階段作為範圍，且無法設定）。 請參閱[範圍設定如何影響資料摘要](#scope-settings)。</p> |
| **尋找並取代常值** | 未提供 | [尋找和取代](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | 簡易/適中 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | |
| **格式化顯示值** | [格式](/help/data-views/component-settings/format.md) | 未提供 | 困難 | 元件設定<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | <!-- Date-time formatting isn't yet reflected in data feed output — feeds currently show the standard timestamp regardless of this setting, though Adobe plans to support this for general availability. Whether numeric formats (decimal, currency, percent) on metrics affect data feed output is still being confirmed with the team.--> |
| **從摘要資料集將維度分組** | [摘要資料群組](/help/data-views/component-settings/summary-data-group.md) | 未提供 | 不可能 | 元件設定 | <!-- Whether this is "Not possible" hasn't been discussed with the team. Don't assume this affects data feed output until confirmed. --> |
| **處理空白（「無值」）欄位** | [沒有值選項](/help/data-views/component-settings/no-value-options.md) | 未提供 | 不可能 | 元件設定 | <!-- Whether this is "Not possible" — including whether a blank value is sent as null, and whether "Treat as a value" changes the underlying data — is still being reviewed with the team. --> |
| **從查詢資料集中查詢值** | 未提供 | [查詢](/help/data-views/derived-fields/derived-fields.md#lookup) | 簡易/適中<p>查閱表格必須已存在。</p> | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | |
| **小寫字串** | [行為](/help/data-views/component-settings/behavior.md) | [小寫](/help/data-views/derived-fields/derived-fields.md#lowercase) | 簡易/適中 | 元件設定<p>建議使用，因為：</p><ul><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中（使用SQL時則不可能）</li><li>它不會佔用您其中一個有限的衍生欄位。</li></ul> | |
| **將多個欄位合併為一個** | 未提供 | [合併欄位](/help/data-views/derived-fields/derived-fields.md#merge) | 簡易/適中 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | |
| **將URL剖析為元件** | [子字串](/help/data-views/component-settings/substring.md) （URL剖析方法） | [URL剖析](/help/data-views/derived-fields/derived-fields.md#urlparse) | 困難<p>需要自訂字串剖析來擷取相同的元件。</p> | 元件設定<p>建議使用，因為它不會使用其中一個有限的衍生欄位。</p> | <!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **對數值欄位執行基本數學** | 未提供 | [數學](/help/data-views/derived-fields/derived-fields.md#math) | 簡易/適中 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | |
| **跨事件儲存維度值** | [持續性](/help/data-views/component-settings/persistence.md) | 目前無法使用<!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | 困難 | 元件設定<p>為方便使用而建議，因為它不會使用您有限的衍生欄位之一。</p> | 與回顧日期範圍互動，方式與範圍相依衍生欄位函式相同。 請參閱[瞭解回顧日期範圍](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)。 |
| **使用規則運算式取代值** | [子字串](/help/data-views/component-settings/substring.md) （Regex方法） | [Regex取代](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 簡易/適中 | 元件設定<p>這三種方法會產生相同的結果，但偏好使用元件設定，因為：</p><ul><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中（使用SQL時則不可能）</li><li>它不會佔用您其中一個有限的衍生欄位。</li></ul> | |
| **解析工作階段中的下一個或上一個值** | 未提供 | [下一個或上一個](/help/data-views/derived-fields/derived-fields.md#next-previous) | 困難 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | 取決於範圍設定。 請參閱[範圍設定如何影響資料摘要](#scope-settings)。 |
| **傳回兩個日期之間的差異** | 未提供 | [日期數學](/help/data-views/derived-fields/derived-fields.md#datemath) | 困難 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | 取決於範圍設定。 請參閱[範圍設定如何影響資料摘要](#scope-settings)。 |
| **將量度的範圍設定為事件、設定檔或總計** | [範圍](/help/data-views/component-settings/scope.md) | 未提供 | | | <!--Not yet discussed with the team. Don't assume this affects data feed output until confirmed.--> |
| **分割分隔值** | [子字串](/help/data-views/component-settings/substring.md) （分隔符號或從左/右方法） | [分割](/help/data-views/derived-fields/derived-fields.md#split) | 簡易/適中 | 元件設定<p>建議使用，因為：</p><ul><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中（使用SQL時則不可能）</li><li>它不會佔用您其中一個有限的衍生欄位。</li></ul> | |
| **彙總或彙總範圍中的值** | 未提供 | [摘要](/help/data-views/derived-fields/derived-fields.md#summarize) | 困難 | 衍生欄位<p>為方便使用，建議您這麼做，因為相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中。</p> | 取決於範圍設定。 請參閱[範圍設定如何影響資料摘要](#scope-settings)。 |
| **從字串修剪字元** | [子字串](/help/data-views/component-settings/substring.md) （Trim方法） | [修剪](/help/data-views/derived-fields/derived-fields.md#trim) | 簡易/適中 | 元件設定<p>建議使用，因為：</p><ul><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中（使用SQL時則不可能）</li><li>它不會佔用您其中一個有限的衍生欄位。</li></ul> | |

{style="table-layout:auto"}

### 範圍設定對資料摘要有何影響 {#scope-settings}

「日期數學」、「重複資料刪除」、「下一個或上一個」以及「摘要」都取決於「事件」、「工作階段」或「人員」的&#x200B;[!UICONTROL **範圍**]&#x200B;設定（可用的選項會因功能而異）。 深度沒有可設定的「範圍」欄位，但本質上與工作階段繫結，類似於標準「事件深度」維度。 任何有範圍的欄位都會將相同的值寫入該範圍內的每一列，而該值取決於回顧日期範圍內的資料。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

由於[回顧日期範圍](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)會隨著每個資料摘要傳遞往前滑動，因此相同的欄位可能會在之後的傳遞中傳回不同的值，即使已發生的事件亦然。

風險隨範圍大小而增加：由於個人的歷史記錄在摘要執行內沒有自然時間界限，因此個人範圍比工作階段範圍承受的風險更大。

## 衍生欄位函式範本

[衍生欄位函式範本](/help/data-views/derived-fields/derived-fields.md#templates)可讓您快速建立特定使用案例的衍生欄位，例如建立行銷管道、偵測機器人，或從URL擷取UTM引數。 因為範本是由預先建立的規則鏈所建置，使用範本幾乎總是比在SQL中從頭開始重新產生相同的邏輯來得好，如同`Marketing Channel Template`。

如果範本包含依賴於「範圍」設定的函式，則範本會繼承該函式的範圍警告。 請參閱[範圍設定如何影響資料摘要](#scope-settings)。
