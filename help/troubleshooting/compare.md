---
title: 比較 Analytics 來源連接器資料與 Adobe Analytics
description: 了解在 Adobe Analytics 和 Customer Journey Analytics 中檢視類似報告時的資料差異。
role: Developer, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 查詢服務;SQL 語法
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 100%

---

# 比較 Analytics 來源連接器資料與 Adobe Analytics

您的組織採用 Customer Journey Analytics 時，您可能會注意到 Adobe Analytics 和 Customer Journey Analytics 間的資料有一些差異。這些差異是正常的，且可能由多種原因造成。Customer Journey Analytics 的設計可讓您改善 Adobe Analytics 中資料的部分限制。這種彈性可能會導致 Customer Journey Analytics 解讀資料的方式有一些差異。透過本文章可了解 Customer Journey Analytics 和 Adobe Analytics 處理資料之方式的可能差異。

此頁面假設您透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)將 Adobe Analytics 資料擷取至 Adobe Experience Platform，然後在 Customer Journey Analytics 中建立[連線](/help/connections/overview.md)和[資料視圖](/help/data-views/data-views.md)。

![資料從 Adobe Analytics 流向 Adobe Experience Platform 是透過資料連接器，流向 Customer Journey Analytics 則是透過 CJA 連線。](assets/compare.png)

請考量以下可能使資料在報告平台之間有所差異的原因：

* **不同的資料集或報告套裝**：請確定 Adobe Analytics 中的報告套裝，以及來源連接器從中衍生資料的報告套裝是相同的。
* **行事曆設定**：Adobe Analytics 中的報告套裝包含您可以設定的時區和其他行事曆設定。同樣地，Customer Journey Analytics 中的資料視圖也有個別設定可供您控制。若希望內容相同，請確定產品之間的這些設定都相符。
* **其他資料集**：Customer Journey Analytics 具備可在單一連線內包含多個資料集的功能。這些差異包括其他事件資料集、輪廓資料集或查詢資料集。此功能是 Adobe Analytics 和 Customer Journey Analytics 之間的關鍵差異，可取得跨管道資料的洞察。
* **拼接資料集**：Adobe 具備可在兩個資料集之間分析人員 ID 的功能，進而產生包含拼接 ID 的新資料集。這些[拼接資料集](/help/stitching/overview.md)會包含 Adobe Analytics 報告套裝提供之內容以外的其他資料。
* **資料來源**：Customer Journey Analytics 不包含已上傳至 Adobe Analytics 報告套裝的任何[資料來源](https://experienceleague.adobe.com/zh-hant/docs/analytics/import/data-sources/overview)類型，包括摘要資料來源或交易 ID 資料來源。
* **維度和量度設定**：在資料視圖中，每個維度和量度都包含其自有的設定，而您的組織可以變更這些設定。這些變更會在報告執行時套用，因此會回溯套用。Adobe Analytics 中的維度和量度設定會變更資料的收集方式，使變更從該時間點起套用。如果您變更了其中任一產品的元件設定，這些設定可能會導致報告差異。若聚焦於特定維度，請確保 Adobe Analytics 和 Customer Journey Analytics 之間的歸因與持續性設定相符。

  >[!TIP]
  >
  >Adobe 強烈建議 Adobe Analytics 中的維度採用「[!UICONTROL 最近 (最後一個)]」配置。此配置設定可讓 Customer Journey Analytics 有更高的歸因彈性。

* **造訪定義**：除了個別的維度和量度設定外，資料視圖本身也包含會徹底變更訪客資料解讀方式的設定。例如，您可以將一個區段套用至整個資料視圖 (類似 Adobe Analytics 中的[虛擬報告套裝](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/virtual-report-suites/vrs-about))。您也可以變更造訪持續時間的定義，或針對任何所需的事件自動開始新的造訪。這些設定中的任何一項，都會對 Customer Journey Analytics 與 Adobe Analytics 之間的報告差異產生顯著影響。

## 檢查產品之間的記錄計數

如果上述所有設定的內容都很相近，而您想要至少驗證產品之間的記錄數量，可以採取以下步驟：

1. 在 Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home)中，執行以下依時間戳記區分的記錄總數查詢：

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. 在 Adobe Analytics [資料摘要](https://experienceleague.adobe.com/zh-hant/docs/analytics/export/analytics-data-feed/data-feed-overview)中，產生所需日期範圍的摘要檔案。計算每個檔案中的列數，藉此識別並排除以下列：

   * `exclude_hit` 不是 `0` (兩個產品均已從 Analysis Workspace 排除資料)
   * `hit_source` 是 `0`、`3`、`5`、`7`、`8`、`9` 或 `10` (資料來源和其他非點擊資料)
   * `page_event` 是 `53` 或 `63` (串流媒體保持連線點擊)

   符合上述任一條件的列會從 Analytics 來源連接器擷取工作流程中排除，因此計算資料摘要列數時也應加以排除。

1. 查詢服務中的記錄總數應與相同時段之資料摘要中的列數相符。
