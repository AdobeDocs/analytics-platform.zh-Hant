---
title: 與您的 Adobe Analytics 資料比較
description: 了解如何將您的 Adobe Analytics 資料與 Customer Journey Analytics 中的資料進行比較
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 查詢服務;查詢服務;SQL 語法
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: ht
source-wordcount: '831'
ht-degree: 100%

---

# 與您的 Adobe Analytics 資料比較

您的組織採用 Customer Journey Analytics 時，您可能會注意到 Adobe Analytics 和 Customer Journey Analytics 之間的資料存在一些差異。這是正常的現象，發生原因有很多種。Customer Journey Analytics 的設計可讓您改善 AA 中資料的部分限制。但可能會發生未預期/意外的不一致情況。本文章旨在協助您診斷並解決這些差異，讓您和團隊能夠使用 Customer Journey Analytics 而不會受到資料完整性疑慮所阻礙。

假設您透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)將 Adobe Analytics 資料擷取至 Adobe Experience Platform，然後使用該資料集建立了 Customer Journey Analytics 連線。

![資料透過資料連接器從 Adobe Analytics 流向 Adobe Experience Platform，並透過 CJA 連線流向 Customer Journey Analytics。](assets/compare.png)

接著您建立資料檢視，然後之後報告這筆在 Customer Journey Analytics 上的資料時，您注意到 Adobe Analytics 中的報告結果不一致。

以下為將您的原始 Adobe Analytics 資料與 Customer Journey Analytics 中的資料進行比較的部分步驟。

## 先決條件

* 確認 Adobe Experience Platform 中的 Analytics 資料集包含您正在調查之日期範圍的資料。

* 確認您在 Analytics 中選擇的報告套裝符合擷取到 Adobe Experience Platform 的報告套裝。

## 步驟 1：執行 Adobe Analytics 中的發生次數量度

「[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)」量度顯示點擊次數，其中會設定或保留指定的維度。

1. 在「Analytics > [!UICONTROL 工作區]」中，請將您要作為維度報告的日期範圍拖曳到「[!UICONTROL 自由]表格」。

1. 「[!UICONTROL 發生次數]」量度會自動套用到該日期範圍。

1. 請儲存此專案，以便於在比較時使用。

## 步驟 2：將結果與 Customer Journey Analytics 中[!UICONTROL 依時間戳記區分的記錄總數]進行比較

現在請將 Analytics 中的「[!UICONTROL 發生次數]」與 Customer Journey Analytics 中依時間戳記區分的記錄總數進行比較。

依時間戳記區分的記錄總數應符合發生次數，前提是 Analytics 來源連接器並未捨棄任何記錄 - 請參閱下節。

>[!NOTE]
>
>這僅適用於一般中值資料集，而非拼接資料集 (透過[拼接](/help/stitching/overview.md))。請注意，用於 Customer Journey Analytics 的人員 ID 計量是進行比較工作的關鍵。在 Adobe Analytics 中複寫可能不是每次都那麼容易，尤其是已開啟「拼接」時。

1. 在 Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=zh-Hant)中，執行以下[!UICONTROL 依時間戳記區分的記錄總數]查詢：

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

1. 在 [Analytics 資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)中，從原始資料中找出 Analytics 來源連接器是否可能已篩選掉某些列。

   [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)可能在轉換成 XDM 結構描述期間篩選掉某些列。整列不適用於轉換的原因有好幾種。如果下列任一 Analytics 欄位有這些值，將會篩選掉整列。

   | Analytics 欄位 | 導致某一列被捨棄的值 |
   | --- | --- |
   | Opt_out | y、Y |
   | In_data_only | Not 0 |
   | Exclude_hit | Not 0 |
   | Bot_id | Not 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   如需 hit\_source 的詳細資訊，請參閱：[資料欄參考](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)。 如需 page\_event 的詳細資訊，請參閱：[頁面事件查閱](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=zh-Hant)。

1. 如果連接器已篩選列，請將這幾列減去[!UICONTROL 發生次數]量度。得到的數字應符合在 Adobe Experience Platform 資料集中的事件數。

## 為什麼從 Adobe Experience Platform 擷取期間可能會篩選或略過記錄

Customer Journey Analytics [連線](/help/connections/create-connection.md)可讓您根據資料集內的通用人員 ID 帶入並聯結多筆資料集。在後端，我們會套用重複資料刪除：根據時間戳記在外部完整聯結或聯合事件資料集，然後根據人員 ID 在內部聯結輪廓和查詢資料集。

以下是從 Adobe Experience Platform 時可能略過記錄的部分原因。

* **遺失時間戳記** – 如果事件資料集遺失時間戳記，則會在擷取期間完全忽略或略過這些記錄。

* **遺失人員 ID** – 遺失人員 ID (來自於事件資料集和/或輪廓/查詢資料集) 會導致這些記錄遭到忽略或略過。原因是無聯結記錄的通用 ID 或相符的索引鍵。

* **無效或大筆人員 ID** – 如是無效 ID，系統無法在資料集間找到可以聯結的有效通用 ID。在某些情況下，人員 ID 欄會包含無效的人員 ID，例如「未定義」或「00000000」。在事件中每月出現超過 100 萬次的人員 ID (數字與字母的任何組合) 無法歸因於任何特定使用者或人員。 它將歸類為無效。這些記錄無法將擷取資料擷取至系統中，並導致容易出錯的擷取和報告。 
