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
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# 瞭解資料摘要和Analysis Workspace之間的資料差異

{{release-limited-testing}}

資料摘要匯出中的資料並不一定與您在Analysis Workspace中看到的資料完全相符。 本頁資訊說明部分主要原因。

## 處理期間（資料摘要）與報告期間(Analysis Workspace)的比較 {#processing-window}

每個資料摘要傳送都會使用滾動式30天處理期間。 處理視窗會提供分類資料摘要傳送中的事件所需的歷史內容。 如需有關處理視窗的詳細資訊，包括範例，請參閱[瞭解處理視窗](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window)。

從這個角度來看，處理期間類似於Analysis Workspace中的報告期間（您為報告選擇的日期範圍）。 不過，兩者之間還是有主要差異。

| 主要差異 | 報告期間(Analysis Workspace) | 處理視窗（資料摘要） |
|---------|---------|----------|
| **資料界限**<br/>&#x200B;資料是否包含在報表或摘要中 | 彈性<p>如果事件受到下列任一因素的影響，則仍可將其納入Workspace報表：</p><ul><li>**Dimension持續性**：使用工作階段、自訂時間或量度[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，可以持續超過報告期間。 與使用人員報告期間[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)的報告期間相同。 資料會經過彙總。</li><li>**區段資格**：依預設，區段可延伸超過報告期間。<p>使用者建立區段時，可以選擇將區段限制在報告期間。<!--add link to new docs--></p></li><li>**工作階段計算**：工作階段可以超出報告期間。 </li><li>**衍生欄位轉換**</li></ul> | 固定<p>落在處理期間之外的事件通常不會影響資料摘要。 處理視窗會套用至下列因素：</p><ul><li>**Dimension持續性**：使用自訂時間[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，可持續存在超過處理期間（最長90天），與Workspace中相同。 使用人員報告期間[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，無法持續存在超過處理期間。 資料不會彙總。</li><li>**區段資格**：一律限於處理期間。</li><li>**工作階段計算**：一律限於處理期間。</li><li>**衍生欄位轉換**：參考容器的任何衍生欄位函式都會在資料摘要匯出中使用處理視窗。</li></ul> |
| **報告的時間範圍**<br/>&#x200B;哪些事件包含在報告或摘要中 | 與報告期間相同。 | 與處理期間不同。 <p>要報告的時間範圍是頻率視窗，可以是處理視窗結尾的一小時或一天。</p> |

>[!BEGINSHADEBOX]

**範例**

以下範例說明報表時段與處理時段之間的差異，如何造成Workspace報表與資料摘要傳送之間的資料差異。

45天前符合某區段資格的使用者具有人員容器，且今天有事件。 具有30天報告時段的Workspace報表包含使用者事件，因為區段預設會超出報告時段。 今天的資料摘要傳送不包含事件，因為區段資格僅限30天的處理期間。

<!-- update the following graphic -->

![工作區與資料摘要之間的資料差異](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## 拼接重播

每次執行拼接重播時，都會回溯更新歷史身分資料。

資料摘要和Analysis Workspace對銜接重播的處理方式不同，如下所示：

* **資料摘要**：僅反映匯出時拼接的身分。 系統不會將重播結果回溯套用至匯出的檔案。

* **Analysis Workspace**：顯示最新的彙整資料，每次執行重播時都會回溯更新。 每次重播後，歷史資料都會變更，因此Workspace一律會反映最新的身分解析度。

## 延遲送達事件

在資料摘要中，事件可能會在資料摘要匯出視窗關閉後到達。

資料摘要和Analysis Workspace對於過去事件的運作方式不同，如下所示：

* **資料摘要**：根據收到事件的時間，匯出固定時間範圍內的資料。

  在視窗關閉後抵達的事件，可能不會納入匯出中。 這會受到您選擇的[處理延遲](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay)所影響。

* **Analysis Workspace**：在報告時處理資料，因此無論事件是在何時收到，都會將其包含在報告中。

## 資料批次

有時資料會以跨越較長時段的批次提交。

資料摘要和Analysis Workspace對批次資料的運作方式不同，如下所示：

* **資料摘要**：根據原始時間戳記，將批次資料分散到每天或每小時。 例如，包含30天資料的批次會分散在匯出30天中，因此在任何單一匯出中都會只顯示很小的片段。

* **Analysis Workspace**：在批次完全處理完畢後立即顯示批次中的所有資料，無論批次中包含的時間範圍為何。

