---
title: 將Google Analytics歷史資料內嵌至Adobe Experience Platform
description: 說明如何使用Customer Journey Analytics(CJA)將Google Analytics資料內嵌至Adobe Experience Platform。
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# 將Google Analytics歷史資料內嵌至Adobe Experience Platform

本頁著重於如何將Google Analytics歷史資料內嵌至Adobe Experience Platform資料集，讓您在Customer Journey Analytics內的「資料檢視」中參照該資料集。 您可以結合本頁的步驟與 [設定即時Google Analytics實作](streaming.md)，會產生循環資料集。 將此歷史資料集與目前實作的資料集結合，即可順暢檢視Customer Journey Analytics中目前和回填的資料。

## 先決條件

為了完成這些工作，您需要下列存取權和權限：

* 存取 Adobe Experience Platform
* 存取Google Analytics（GA Standard或GA 360）
* [管理員存取](/help/getting-started/cja-access-control.md) Customer Journey Analytics

## 設定BigQuery匯出

Universal Analytics屬性中的資料結構與Google Analytics4屬性中的資料結構不同。 根據要從中導出資料的屬性類型設定BigQuery導出：

* [為通用分析屬性設定BigQuery匯出](https://support.google.com/analytics/answer/3416092)
* [為Google Analytics4屬性設定BigQuery匯出](https://support.google.com/analytics/answer/9823238)

### 通用分析屬性的其他需求

>[!NOTE]
>
>本節內容僅適用於Universal Analytics屬性。 如果從GA4屬性導出，則可以繼續 [將資料匯出至Google Cloud Platform](#export-gcp).

通用分析屬性會將每個記錄儲存在其使用者工作階段的資料中，而非個別事件。 需要SQL查詢，將Universal Analytics資料轉換為與Adobe Experience Platform相容的格式。 套用 `UNNEST` 函式 `hits` 欄位，並將其儲存為BigQuery表格。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## 將資料匯出至Google Cloud Platform {#export-gcp}

在Google Cloud Platform中，導覽至 **導出>導出到GCS**. 資料放入Google雲端儲存體後，即可將其提取至Adobe Experience Platform。

## 將資料從Google雲端儲存空間匯入Experience Platform

1. 在Adobe Experience Platform中，選取 **[!UICONTROL 來源]** 左邊。
1. 在目錄下，找到 **[!UICONTROL Google雲端儲存空間]** 選項。 按一下 **[!UICONTROL 新增資料]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>如果您打算同時匯入歷史和即時串流Google Analytics資料，請務必對這兩個資料集使用相同的結構。 您可以使用 [合併的資料集](/help/connections/combined-dataset.md).

您可以將GA事件資料對應至先前建立的現有資料集，或使用您選擇的XDM結構建立資料集。 當您選取結構描述後，Experience Platform 會套用機器學習，自動地將 Google Analytics 資料中的每個欄位預先對應到您的 [XDM 結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui)。

![結構圖](../assets/schema-map.png)

將欄位對應至XDM架構後，您可以重複排程此匯入，並在擷取程式期間套用錯誤驗證。 此驗證可確保您匯入的資料沒有任何問題。

## 必要的XDM欄位

Platform中的某些XDM欄位需要正確的格式，才能正確處理資料。

* **`timestamp`**:在Experience Platform結構UI中建立特殊的計算欄位。 按一下 **[!UICONTROL 新增計算欄位]** 並包住 `timestamp` 字串 `date` 函式：

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   將計算欄位儲存至架構中的時間戳記資料結構：

   ![時間戳記](../assets/timestamp.png)

* **`_id`**:此欄位中必須有值 — CJA不在乎值。 您可以新增「1」至欄位：

   ![ID](../assets/_id.png)

## 後續步驟

* 如果您有要串流至Adobe Experience Platform的目前資料，請參閱 [設定Google Analytics資料的串流](streaming.md).
* 如果您想要開始針對回填資料製作報表，請參閱 [建立連線](/help/connections/create-connection.md).
