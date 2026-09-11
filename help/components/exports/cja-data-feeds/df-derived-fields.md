---
title: 在資料摘要中使用衍生欄位
description: 瞭解如何在資料摘要中使用衍生欄位。
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# 在資料摘要中使用衍生欄位

{{release-limited-testing}}

您可以使用[衍生欄位](/help/data-views/derived-fields/derived-fields.md)對資料摘要資料執行資料轉換。

許多衍生的欄位函式會執行您也可使用SQL套用的轉換，例如取代值、組合欄位或轉換欄位的資料型別，因此您選擇的方法有時是偏好的問題。

## 衍生欄位與SQL

下表比較使用衍生欄位或SQL的優缺點。

| 方法 | 優點 | 缺點 |
| --- | --- | --- |
| **衍生欄位** | <ul><li>相同的邏輯會一致地套用在Analysis Workspace和您的資料摘要輸出中，因為衍生欄位連同標準維度和量度一起當作元件納入您的資料摘要結構描述中。</li><li>有些轉換，特別是依賴範圍設定或剖析URL的轉換，很難在SQL中複製。</li></ul> | 增加處理額外負荷，這會影響資料摘要傳遞效能。<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>不受適用於衍生欄位的函式和運運算元限制。</li><li>對資料摘要的傳送效能沒有影響。</li></ul> | <ul><li>邏輯在Analysis Workspace中不適用，因此您需要在該處分別複製邏輯。</li><li>有些轉換，尤其是依賴「範圍」設定或剖析URL的轉換，很難複製或不切實際。</li></ul> |

{style="table-layout:auto"}

## 衍生欄位函式

下表說明每個衍生欄位函式，不論它最適合衍生欄位還是SQL，以及在使用它之前要牢記的任何考量。

| 衍生欄位函式 | 使用SQL進行復寫困難 | 最適化（衍生欄位或SQL） | 考量事項 |
| --- | --- | --- | --- |
| [**案例當**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/>&#x200B;根據一或多個欄位的條件套用條件，然後根據符合的條件設定輸出值。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 如果涉及大量規則（例如行銷管道分類），這會特別有用。 |
| [**分類**](/help/data-views/derived-fields/derived-fields.md#classify)<br/>&#x200B;定義一組值，這些值在新衍生欄位中會由對應的值取代。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**串連**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/>&#x200B;使用定義的分隔字元（例如頁面名稱和行銷管道），將欄位值合併為單一新衍生欄位。 | 輕鬆調節 | 任一 | 映象將多個維度欄新增至自由表格的功能，該功能限製為完整表格匯出。 衍生欄位讓類似的輸出可在資料摘要中使用。 |
| [**日期數學**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/>&#x200B;傳回兩個日期或日期時間欄位（例如，預訂日期與簽到日期之間的天數）之間的差值，其範圍為事件、工作階段或人員。 | 困難 | 衍生欄位 | 在SQL中復寫很複雜。 此函式依存於範圍設定。 如需詳細資訊，請參閱[函式中的範圍設定如何影響資料摘要](#scope-settings)。 |
| [**重複資料刪除**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/>&#x200B;防止在人員或工作階段範圍中多次計算值（例如，刪除重複的預約確認ID）。 | 困難 | 衍生欄位 | 此函式依存於範圍設定。 如需詳細資訊，請參閱[函式中的範圍設定如何影響資料摘要](#scope-settings)。 |
| [**深度**](/help/data-views/derived-fields/derived-fields.md#depth)<br/>&#x200B;傳回欄位的深度，類似於標準的事件深度維度（例如內部搜尋深度）。 | 困難 | 衍生欄位 | 使用工作階段作為範圍，且無法設定。<!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> 仍在透過工程確認工作階段跨越摘要 — 傳遞邊界時，計數器的行為。 此函式依存於範圍設定。 如需詳細資訊，請參閱[函式中的範圍設定如何影響資料摘要](#scope-settings)。 |
| [**尋找並取代**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/>&#x200B;尋找選取欄位中的所有值，並以不同的值取代。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**查詢**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/>&#x200B;使用相符的索引鍵從查詢資料集中查詢值，並在新的衍生欄位中傳回該值。 | 輕鬆調節 | 任一 | 如果查閱表格已經存在，SQL就會運作。 |
| [**小寫**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/>&#x200B;將欄位的值轉換為小寫。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**Math**](/help/data-views/derived-fields/derived-fields.md#math)<br/>&#x200B;將基本的數學運運算元（加、減、乘、除或加冪）套用到數值欄位，依點選評估。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**合併欄位**](/help/data-views/derived-fields/derived-fields.md#merge)<br/>&#x200B;檢查兩個或多個欄位中的第一個是否有值；如果沒有，則使用下一個欄位，依此類推。 | 輕鬆調節 | 任一 | 無 |
| [**下一個或上一個**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/>&#x200B;解析造訪或事件表格欄位的下一個或上一個值，其範圍為人員或工作階段。 | 困難 | 衍生欄位 | 此函式依存於範圍設定。 如需詳細資訊，請參閱[函式中的範圍設定如何影響資料摘要](#scope-settings)。 |
| [**Regex取代**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/>&#x200B;使用規則運算式取代欄位中的值。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**分割**](/help/data-views/derived-fields/derived-fields.md#split)<br/>&#x200B;將欄位中的值分割成新的衍生欄位（例如，將分隔清單轉換為陣列）。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**摘要**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/>&#x200B;將彙總函式（例如sum、count或最常見）套用至欄位，其範圍為事件、工作階段或人員。 | 困難 | 衍生欄位 | 此函式依存於範圍設定。 如需詳細資訊，請參閱[函式中的範圍設定如何影響資料摘要](#scope-settings)。 |
| [**修剪**](/help/data-views/derived-fields/derived-fields.md#trim)<br/>&#x200B;從欄位值的開頭或結尾修剪空白字元、特殊字元或一組字元數。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/>&#x200B;變更欄位的資料型別，使其可用於其他轉換。 | 輕鬆調節 | 任一 | 在SQL中可重現，但使用衍生欄位可確保在Analysis Workspace和資料摘要輸出中一致地套用相同的邏輯。 |
| [**URL剖析**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/>&#x200B;剖析URL的各個部分，包括通訊協定、主機、路徑、查詢字串引數或雜湊值。 | 困難 | 衍生欄位 | SQL需要自訂字串剖析來擷取相同的元件。 |

{style="table-layout:auto"}

### 函式中的範圍設定如何影響資料摘要 {#scope-settings}

[!UICONTROL **日期數學**]、[!UICONTROL **重複資料刪除**]、[!UICONTROL **下一個或上一個**]&#x200B;以及&#x200B;[!UICONTROL **摘要**]&#x200B;都取決於「事件」、「工作階段」或「人員」的&#x200B;[!UICONTROL **範圍**]&#x200B;設定（可用的選項會因函式而異）。 [!UICONTROL **Depth**]&#x200B;沒有可設定的範圍欄位，但本身繫結至工作階段，類似於標準的Event Depth維度。 任何有範圍的欄位都會將相同的值寫入該範圍內的每一列，而該值取決於回顧日期範圍內的資料。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

由於回顧日期範圍會隨著每次資料摘要傳遞向前滑動，因此相同的欄位可能會在稍後傳遞時傳回不同的值，即使已發生的事件亦然。

風險隨範圍大小而增加：由於個人的歷史記錄在摘要執行內沒有自然時間界限，因此個人範圍比工作階段範圍承受的風險更大。

## 衍生欄位函式範本

[衍生欄位函式範本](/help/data-views/derived-fields/derived-fields.md#templates)可讓您快速建立特定使用案例的衍生欄位，例如建立行銷管道、偵測機器人，或從URL擷取UTM引數。 因為範本是從預先建立的規則鏈建立的，使用範本幾乎總是比在SQL中從頭開始重新產生相同的邏輯好。

如果範本包含依賴於「範圍」設定的函式，則範本會繼承該函式的範圍警告。 請參閱[函式中的範圍設定如何影響資料摘要](#scope-settings)。

