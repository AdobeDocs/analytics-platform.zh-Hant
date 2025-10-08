---
title: 比較Analytics Source Connector資料與Adobe Analytics
description: 瞭解在Adobe Analytics和Customer Journey Analytics中檢視類似報表時的資料差異。
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 查詢服務;查詢服務;SQL 語法
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 4%

---

# 比較Analytics Source Connector資料與Adobe Analytics

隨著您的組織採用Customer Journey Analytics，可能會注意到Adobe Analytics與Customer Journey Analytics之間的資料差異。 這些差異是正常的，可能會因為數個原因而發生。 Customer Journey Analytics的設計可讓您改善Adobe Analytics中資料的部分限制。 這種靈活性可能會導致Customer Journey Analytics在解譯資料的方式上產生一些差異。 請閱讀本文章，瞭解Customer Journey Analytics和Adobe Analytics處理資料的方式可能有所不同。

本頁假設您使用[Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-hant)將Adobe Analytics資料擷取到Adobe Experience Platform，然後在Customer Journey Analytics中建立[連線](/help/connections/overview.md)和[資料檢視](/help/data-views/data-views.md)。

![資料透過資料連接器從 Adobe Analytics 流向 Adobe Experience Platform，並透過 CJA 連線流向 Customer Journey Analytics。](assets/compare.png)

請考量下列可能是資料在報表平台之間有所差異的原因：

* **不同的資料集或報表套裝**：請確定Adobe Analytics中的報表套裝與Source Connector衍生資料的來源報表套裝是相同的。
* **行事曆設定**： Adobe Analytics中的報表套裝包含您可設定的時區和其他行事曆設定。 同樣地，Customer Journey Analytics中的資料檢視也有個別設定可供您控制。 如果需要同位，請確定這些設定在產品之間相符。
* **其他資料集**： Customer Journey Analytics提供可在單一連線中包含多個資料集的功能。 這些差異包括其他事件資料集、設定檔資料集或查詢資料集。 此功能是Adobe Analytics與Customer Journey Analytics之間的關鍵差異，可讓insight處理跨管道資料。
* **拼接資料集**： Adobe提供可在兩個資料集之間分析人員ID的功能，進而產生包含拼接ID的新資料集。 這些[拼接資料集](/help/stitching/overview.md)包含Adobe Analytics報表套裝提供的資料以外的其他資料。
* **資料來源**： Customer Journey Analytics不包含任何已上傳至Adobe Analytics報表套裝的[資料來源](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/overview)型別，包括摘要資料來源或交易ID資料來源。
* **Dimension和量度設定**：在資料檢視中，每個維度和量度都包含其自己的設定，您的組織可以加以變更。 這些變更會在執行報表時套用，因此會回溯套用。 Dimension和Adobe Analytics中的量度設定會變更資料的收集方式，而讓這些變更從此時間點開始套用。 如果您變更了任一產品的元件設定，這些設定可能會產生報表差異。 如果聚焦於特定維度，請確保Adobe Analytics和Customer Journey Analytics之間的歸因和持續性設定相符。

  >[!TIP]
  >
  >Adobe強烈建議Adobe Analytics中的維度使用&#39;[!UICONTROL 最近（最後一個）]&#39;的配置。 此配置設定可讓Customer Journey Analytics提供更大的歸因靈活性。

* **造訪定義**：除了個別維度和量度設定外，資料檢視本身也包含從根本上改變訪客資料解譯方式的設定。 例如，您可以將區段套用至整個資料檢視(類似Adobe Analytics中的[虛擬報告套裝](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-about))。 您也可以變更造訪持續時間的定義，或是在任何需要的事件上自動開始新的造訪。 這些設定中的任何一個都會對Customer Journey Analytics和Adobe Analytics之間的報表差異產生顯著影響。

## 檢查產品之間的記錄計數

如果上述所有設定看起來都類似，而且您至少想要驗證產品之間的記錄數，您可以使用以下步驟：

1. 在Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home)中，執行以下依時間戳記區分的記錄總數查詢：

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

1. 在Adobe Analytics [資料摘要](https://experienceleague.adobe.com/zh-hant/docs/analytics/export/analytics-data-feed/data-feed-overview)中，產生所需日期範圍的摘要檔案。 計算每個檔案中的列數，識別並排除下列列：

   * `exclude_hit`不是`0` (兩個產品中均從Analysis Workspace排除的資料)
   * `hit_source`是`0`、`3`、`5`、`7`、`8`、`9`或`10` （資料來源和其他非點選資料）
   * `page_event`是`53`或`63` （串流媒體保持連線點選）

   符合上述任一條件的列會從Analytics Source Connector擷取工作流程中排除，因此計算資料摘要列時也應排除。

1. 查詢服務中的記錄總數應與相同時段內資料摘要中的列數相符。
