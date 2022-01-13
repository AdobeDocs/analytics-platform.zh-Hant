---
title: 比較AA資料與CJA資料
description: 了解如何比較Adobe Analytics資料與Customer Journey Analytics中的資料
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 6f77dd9caef1ac8c838f825a48ace6cf533d28a9
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 4%

---

# 比較Adobe Analytics資料與CJA資料

假設您透過Analytics Source Connector將Adobe Analytics資料擷取至AEP，然後使用此資料集建立CJA連線。

![資料流](assets/compare.png)

接著，您建立了資料檢視，之後在CJA上報告此資料時，您發現Adobe Analytics中報告結果有差異。

以下是比較原始Adobe Analytics資料與目前處於Customer Journey Analytics中的Adobe Analytics資料的一些步驟。

## 先決條件

* 請確定AEP中的Analytics資料集包含您正在調查之日期範圍的資料。

* 請確定您在Analytics中選取的報表套裝符合已擷取至Adobe Experience Platform的報表套裝。

## 步驟1:在Adobe Analytics中執行發生次數量度

此 [發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en) 量度會顯示指定的維度經設定或持續存在的點擊次數。

1. 在Analytics >中 [!UICONTROL 工作區]，將您要以維度形式報告的日期範圍拖曳至 [!UICONTROL 自由格式] 表格。

1. 此 [!UICONTROL 發生次數] 量度會自動套用至該日期範圍。

1. 儲存此專案，以便在比較中使用。

## 步驟2:將結果與 [!UICONTROL 按時間戳記的記錄總數] 在CJA中

現在比較 [!UICONTROL 發生次數] 中的Analytics轉換為Total記錄(依Customer Journey Analytics中的時間戳記)。

如果Analytics來源連接器未捨棄任何記錄，則依時間戳記的記錄總數應與發生次數相符 — 請參閱下方的區段。

>[!NOTE]
>
>這僅適用於一般中間值資料集，不適用於匯整的資料集(透過 [跨管道分析](/help/connections/cca/overview.md))。 請注意，要讓比較工作順利進行，請務必考慮CJA中使用的人員ID。 在AA中復寫不一定容易，尤其是如果已開啟跨管道分析功能。

1. 在Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html)，請執行下列 [!UICONTROL 按時間戳記的記錄總數] 查詢：

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

1. 在 [Analytics資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)，從原始資料中識別Analytics來源連接器是否可能已捨棄某些列。

   此 [Analytics來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) 在轉換為XDM架構期間可能會拖放列。 整列可能有多種原因不適合轉換。 如果下列任何Analytics欄位都有這些值，則會捨棄整列。

   | Analytics欄位 | 導致其被刪除的值 |
   | --- | --- |
   | 退出(_O) | `y, Y` |
   | In_data_only | 非0 |
   | Exclude_hit | 非0 |
   | Bot_id | 非0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 5.363萬 |

1. 如果連接器拖放了列，請從 [!UICONTROL 發生次數] 量度。 產生的數量應與Adobe Experience Platform資料集中的事件數相符。

## 從AEP擷取期間為何可能會捨棄或略過記錄

CJA [連線](/help/connections/create-connection.md) 可讓您根據資料集上的通用人員ID，將多個資料集合併在一起。 在後端，我們會套用重複資料刪除：根據時間戳記，在事件資料集上完整加入或聯合，然後根據人員ID，在設定檔和查詢資料集上完成內聯。

以下是從AEP擷取資料時可能略過記錄的部分原因。

* **遺失時間戳記**  — 如果事件資料集中遺失時間戳記，則擷取期間會完全忽略或略過這些記錄。

* **缺少人員ID**  — 缺少人員ID（來自事件資料集和/或來自設定檔/查詢資料集）會導致忽略或略過這些記錄。 原因是沒有共同ID或相符的鍵值可加入記錄。

* **無效或大型人員ID**  — 如果ID無效，系統在要加入的資料集中找不到有效的通用ID。 在某些情況下，人員ID欄會包含無效的人員ID，例如「未定義」或「00000000」。 每月在事件中顯示超過100萬次的人員ID（包含任何數字和字母的組合）無法歸屬於任何特定的使用者或人員。 它會分類為無效。 這些記錄無法擷取至系統中，且會導致錯誤擷取和報告。
