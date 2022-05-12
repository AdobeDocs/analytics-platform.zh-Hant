---
title: 將您的 AA 資料與 CJA 資料進行比較
description: 了解如何將您的 Adobe Analytics 資料與 Customer Journey Analytics 中的資料進行比較
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '782'
ht-degree: 100%

---

# 將您的 Adobe Analytics 資料與 CJA 資料進行比較

隨著您的組織採用 CJA，您可能會注意到 Adobe Analytics 與 CJA 之間的資料差異。這是正常的現象，發生原因有很多種。CJA 的設計可讓您改善 AA 中資料的部分限制。但會發生未預期/意外的不一致情況。本文章旨在協助您診斷並解決這些差異，以便於您和您的團隊可以使用 CJA，不會受到資料完整性疑慮所阻礙。

假設您透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)將 Adobe Analytics 資料擷取到 AEP，然後使用此資料集建立 CJA 連線。

![資料流](assets/compare.png)

接著您建立資料檢視，然後在日後報告這筆在 CJA 上的資料時，您注意到 Adobe Analytics 中的報告結果不一致。

以下為將您的原始 Adobe Analytics 資料與 Customer Journey Analytics 中的資料進行比較的部分步驟。

## 先決條件

* 確認 AEP 中的 Analytics 資料集包含正在調查的日期範圍的資料。

* 確認您在 Analytics 中選擇的報告套裝符合擷取到 Adobe Experience Platform 的報告套裝。

## 步驟 1：執行 Adobe Analytics 中的發生次數量度

「[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html)」量度顯示點擊次數，其中會設定或保留指定的維度。

1. 在「Analytics > [!UICONTROL 工作區]」中，請將您要作為維度報告的日期範圍拖曳到「[!UICONTROL 自由]表格」。

1. 「[!UICONTROL 發生次數]」量度會自動套用到該日期範圍。

1. 請儲存此專案，以便於在比較時使用。

## 步驟 2：將結果與 CJA 中[!UICONTROL 依時間戳記區分的記錄總數]進行比較

現在請將 Analytics 中的「[!UICONTROL 發生次數]」與 Customer Journey Analytics 中依時間戳記區分的記錄總數進行比較。

依時間戳記區分的記錄總數應符合發生次數，前提是 Analytics 來源連接器並未捨棄任何記錄 - 請參閱下節。

>[!NOTE]
>
>這僅適用於一般中值資料集，而非拼接資料集 (透過[跨管道分析](/help/connections/cca/overview.md))。請注意用於 CJA 的人員 ID 計量是進行比較工作的關鍵。在 AA 中複寫可能不是每次都那麼容易，尤其是已開啟跨管道分析時。

1. 在 Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html)中，執行以下[!UICONTROL 依時間戳記區分的記錄總數]查詢：

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. 在 [Analytics 資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html)中，從原始資料中找出 Analytics 來源連接器是否可能已捨棄某些列。

   [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)可能在轉換成 XDM 結構描述期間捨棄多列。整列不適用於轉換的原因有好幾種。如果下列任一 Analytics 欄位有這些值，將會捨棄整列。

   | Analytics 欄位 | 導致其被捨棄的值 |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | Not 0 |
   | Exclude_hit | Not 0 |
   | Bot_id | Not 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53,63 |

1. 如果連接器捨棄多列，請將這幾列減去[!UICONTROL 發生次數]量度。得到的數字應符合在 Adobe Experience Platform 資料集中的事件數。

## 為何可能會在從 AEP 擷取期間捨棄或略過記錄

CJA [連線](/help/connections/create-connection.md)可讓您根據資料集內的通用人員 ID 帶入並聯結多筆資料集。在後端，我們會套用重複資料刪除：根據時間戳記完全外部聯結或聯集事件資料集，然後根據人員 ID 內部聯結個人資料和查詢資料集。

以下是在從 AEP 擷取資料時可能略過記錄的部分原因。

* **遺失時間戳記** – 如果事件資料集遺失時間戳記，則會在擷取期間完全忽略或略過這些記錄。

* **遺失人員 ID** – 遺失人員 ID (來自於事件資料集和/或個人檔案/查詢資料集) 會導致這些記錄遭到忽略或略過。原因是無聯結記錄的通用 ID 或相符的索引鍵。

* **無效或大筆人員 ID** – 如是無效 ID，系統無法在資料集間找到可以聯結的有效通用 ID。在某些情況下，人員 ID 欄會有無效的人員 ID，例如「未定義」或「00000000」。在事件中每月出現超過 100 萬次的人員 ID (數字與字母的任何組合) 無法歸因於任何特定使用者或人員。 它將歸類為無效。這些記錄無法將擷取資料擷取至系統中，並導致容易出錯的擷取和報告。 
