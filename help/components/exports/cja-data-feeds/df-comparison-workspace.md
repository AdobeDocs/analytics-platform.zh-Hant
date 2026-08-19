---
description: 瞭解如何比較Customer Journey Analytics和Adobe Analytics中的資料摘要功能
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: 比較Customer Journey Analytics和Adobe Analytics中的資料摘要功能
feature: Components
hide: true
source-git-commit: 7fe885e928c495a2518038645ec841229d1f1852
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 0%

---

# 瞭解資料摘要和Analysis Workspace之間的資料差異

{{release-limited-testing}}

資料摘要匯出中的資料並不一定與您在Analysis Workspace中看到的資料完全相符。 本頁資訊說明部分主要原因。

## 回顧日期範圍（資料摘要）與報表日期範圍(Analysis Workspace)的比較

資料摘要中的回顧日期範圍會決定Customer Journey Analytics在尋找符合資料摘要傳送資格的事件時回顧的時間範圍。 如需有關回顧日期範圍的詳細資訊，包括範例，請參閱[瞭解回顧日期範圍](/help/components/exports/cja-data-feeds/create-feed.md#understand-the-lookback-date-range)。

在這個意義上，回顧日期範圍類似於Analysis Workspace中的報表日期範圍。 不過，兩者之間還是有主要差異。

| 主要差異 | 報表日期範圍(Analysis Workspace) | 回顧日期範圍（資料摘要） |
|---------|---------|----------|
| **資料界限**<br/>&#x200B;資料是否包含在報表或摘要中 | 彈性<p>如果事件受到下列任何因素的影響，仍可將其納入Workspace報表：</p><ul><li>**Dimension持續性**：使用工作階段、自訂時間或量度[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)時，持續性可能超過報告日期範圍。 與使用人員報告期間[有效期](/help/data-views/component-settings/persistence.md#expiration-settings)的報告日期範圍相同。 資料會經過彙總。</li><li>**區段資格**：依預設，區段可以超出報表日期範圍。<p>使用者建立區段時，可以選擇將區段限制在報告日期範圍內。<!--add link to new docs--></p></li><li>**工作階段計算**：工作階段可以超出報告日期範圍。 </li><li>**衍生欄位轉換**</li></ul> | 固定<p>不在回顧日期範圍內的事件絕不會納入資料摘要中，無論這些事件是否受到下列因素的影響：</p></p><ul><li>**Dimension持續性**：不論[到期設定](/help/data-views/component-settings/persistence.md#expiration-settings)為何，都不能持續存在超過回顧日期範圍。 資料不會彙總。</li><li>**區段資格**：一律限於回顧日期範圍。</li><li>**工作階段計算**：一律限於回顧日期範圍。</li><li>**衍生欄位轉換**：參考容器的任何衍生欄位函式都會在資料摘要匯出中使用回顧日期範圍。</li></ul><p>如需設定回顧日期範圍的詳細資訊，請參閱[建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed)。</p> |
| **報告期間**<br/>&#x200B;報告的時間範圍 | 與報告期間（您要報告的時間範圍）相同。 | 與您要報告的時間範圍不同。 <p>要報告的時間範圍是「頻率」視窗，可以是一小時或一天。</p> |

>[!BEGINSHADEBOX]

**範例**

以下範例說明報表日期範圍和回顧日期範圍之間的差異，如何造成Workspace報表與資料摘要傳送之間的資料差異。

事件A 85天前發生，且位於具有90天持續性設定的維度上（例如促銷活動點按歸因視窗）。 事件會包含在Analysis Workspace報表中，而非資料摘要傳送中。

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

  在視窗關閉後抵達的事件，可能不會納入匯出中。 這會受到您選擇的[回顧日期範圍](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace)所影響。

* **Analysis Workspace**：在報告時處理資料，因此無論事件是在何時收到，都會將其包含在報告中。

## 資料批次

有時資料會以跨越較長時段的批次提交。

資料摘要和Analysis Workspace對批次資料的運作方式不同，如下所示：

* **資料摘要**：根據原始時間戳記，將批次資料分散到每天或每小時。 例如，包含30天資料的批次會分散在匯出30天中，因此在任何單一匯出中都會只顯示很小的片段。

* **Analysis Workspace**：在批次完全處理完畢後立即顯示批次中的所有資料，無論批次中包含的時間範圍為何。

