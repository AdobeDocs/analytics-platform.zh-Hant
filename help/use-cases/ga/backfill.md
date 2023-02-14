---
title: 將 Google Analytics 將歷史資料擷取至 Adobe Experience Platform
description: 說明如何使用 Customer Journey Analytics (CJA) 將您的 Google Analytics 資料擷取至 Adobe Experience Platform。
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: eceea9ef96701f66cceed5bcb50f92588df6e507
workflow-type: ht
source-wordcount: '620'
ht-degree: 100%

---


# 將 Google Analytics 將歷史資料擷取至 Adobe Experience Platform

此頁面著重於將您的 Google Analytics 歷史資料擷取到 Adobe Experience Platform 做為資料集，讓您參照在 Customer Journey Analytics 之內「資料檢視」中的資料集。 您可以結合此頁面的步驟與[設定一個 Google Analytics 實作](streaming.md)，這會產生反覆出現的資料集。 結合此歷史資料集與最新實作的資料集，以便在 Customer Journey Analytics 中取得現在與回填資料的無縫接軌檢視。

## 先決條件

為了完成這些工作，您需要下列存取權和權限：

* 存取 Adobe Experience Platform
* 存取 Google Analytics (GA 標準版或 GA 360)
* [管理員存取](/help/admin/cja-access-control.md) Customer Journey Analytics

## 設定 BigQuery Export

Universal Analytics 屬性中的資料結構異於 Google Analytics 4 屬性中的資料結構。 根據您想要匯出資料的屬性類型設定 BigQuery Export：

* [設定用於 Universal Analytics 屬性的 BigQuery Export ](https://support.google.com/analytics/answer/3416092)
* [設定用於 Google Analytics 4 屬性的 BigQuery Export ](https://support.google.com/analytics/answer/9823238)

### 用於 Universal Analytics 屬性的其他要求

>[!NOTE]
>
>此節僅適用於 Universal Analytics 屬性。 如果您從 GA4 屬性匯出，您可以前往[將資料匯出至 Google Cloud Platform](#export-gcp)。

Universal Analytics 屬性會將其資料中的每一筆記錄儲存為使用者的工作階段，而非個別事件。 SQL 查詢將 Universal Analytics 資料轉換為與 Adobe Experience Platform 相容的格式是必要的。 將 `UNNEST` 函式套用到 `hits` GA 結構描述中的欄位，並儲存為 BigQuery 表格。

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

## 將資料匯出至 Google Cloud Platform {#export-gcp}

在 Google Cloud Platform 中前往&#x200B;**「匯出」 > 「匯出至 GCS」**。 在資料進入 Google Cloud Storage 時，就已準備好可以被拉進 Adobe Experience Platform 中。

## 將資料從 Google Cloud Storage 匯入到 Experience Platform

1. 在 Adobe Experience Platform 中選擇左邊的&#x200B;**[!UICONTROL 「來源」]**。
1. 在「目錄」下方找出 **[!UICONTROL Google Cloud Storage]** 選項。 按一下「**[!UICONTROL 新增資料]**」。

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>如果您計畫同時匯入歷史與即時串流 Google Analytics 資料，這二個資料集請務必使用相同的結構描述。您可以使用[整合的資料集](/help/connections/combined-dataset.md)在 CJA 中合併資料集。

您可以將 GA 事件資料對應到您之前建立的現有資料集中，或是使用您選擇的任何 XDM 結構描述建立新的資料集。 當您選取結構描述後，Experience Platform 會套用機器學習，自動地將 Google Analytics 資料中的每個欄位預先對應到您的 [XDM 結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui)。

![結構描述對應](../assets/schema-map.png)

當您完成將欄位對應到 XDM 結構描述中的作業後，您可以將這項匯入排程為定期進行，並在擷取過程中套用錯誤驗證。 此驗證可確保您已匯入的資料不會有任何問題。

## 必填的 XDM 欄位

在 Platform 中特定的 XDM 欄位需要正確的格式才能正確地處理資料。

* **`timestamp`**：在 Experience Platform 結構描述 UI 中建立一個特別的計算欄位。 按一下「**[!UICONTROL 新增計算欄位]**」，並讓 `date` 函數中的 `timestamp` 字串換行：

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   將此計算欄位儲存到結構描述中的時間戳記資料結構內：

   ![時間戳記](../assets/timestamp.png)

* **`_id`** 此欄位內必須有值 - CJA 不在乎該值為何。 您可以新增「1」到欄位中：

   ![ID](../assets/_id.png)

## 後續步驟

* 如果您有想要串流至 Adobe Experience Platform 的最新資料，請參閱 [為 Google Analytics 資料設定串流](streaming.md)。
* 如果您想要開始製作關於回填資料的報告，請參閱 [建立連線](/help/connections/create-connection.md)。
