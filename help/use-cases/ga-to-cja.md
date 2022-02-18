---
title: 將 Google Analytics 資料擷取至 Adobe Experience Platform
description: '說明如何利用 Customer Journey Analytics (CJA) 將您的 Google Analytics 資料擷取至 Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '1178'
ht-degree: 100%

---


# 將 Google Analytics 資料擷取至 Adobe Experience Platform

此使用案例聚焦於將您的 Google Analytics 資料當做資料集擷取至 Adobe Experience Platform。 我們會說明如何擷取歷史資料和即時資料。 在完成後，您可以在 Customer Journey Analytics 中合併兩個資料集，以獲得您的使用者旅程的跨裝置檢視。

Experience Platform 中的資料集是由兩個東西所組成：結構描述和資料集中的實際記錄。 結構描述 (我們稱之為 Experience Data Model 或簡稱 XDM) 就像資料集的欄位一樣，也像是描述資料本身的藍圖或規則。 在此平台中，Adobe 提供兩種結構描述：

* 可以將您的 Google Analytics 資料自動與其對應的現成結構描述 (稱為體驗事件結構描述)
* 您可以建立並將 Google Analytics 資料輕鬆地與其對應的自訂結構描述

Adobe 資料模型的其中一個最強大的層面就是可讓您將所有客戶互動資料標準化到一個通用結構描述中，好讓您可以更輕鬆地在 CJA 中將資料拼接在一起。

## 先決條件

為了完成這些工作，您需要下列存取權和權限：

* Adobe Experience Platform 的存取權
* Universal Google Analytics (Google Analytics 360 版本) 或是 Google Analytics 4 (免費版本或 Google Analytics 360 版本) 的存取權
* Customer Journey Analytics 的存取權以及其[管理員權限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant#admin-access-permissions)。

如何將 Google Analytics 資料帶入 Adobe Experience Platform 取決於您使用的 Google Analytics 版本：

| 若您使用... | 您也需要的授權... | 以及需執行... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | 依照下列指示執行步驟 1-3 |
| **Google Analytics 4** | Free GA 版本或 Google Analytics 360 | 依照下列指示執行步驟 1 和 3。 不需要執行步驟 2。 |

## 擷取歷史 (回填) 資料

### 1. 將您的 Google Analytics 資料連線至 BigQuery

如需詳細資訊，請參考[這些指示](https://support.google.com/analytics/answer/3416092?hl=en)。 請注意，這些指示是根據 Universal Google Analytics。

### 2. 將 Google Analytics 工作階段轉換為 BigQuery 中的事件，並匯出到 Google 雲端儲存空間

>[!IMPORTANT]
>
>此步驟僅適用於 Universal Analytics 客戶

GA 資料會將其資料中的每一筆記錄儲存為使用者的工作階段，而非個別事件。 您需要建立 SQL 查詢，以便將 Universal Analytics 資料轉換為與 Experience Platform 相容的格式。 您會在 GA 結構描述中將「unnest」函數套用到「hits」欄位。 以下是您可以使用的 SQL 範例：

```
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
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

當查詢完成後，請將完整結果儲存在 BigQuery 表格中。

請參考[這些指示](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)，其中包含有關 SQL 查詢的指示。

以下影片也會說明下一個步驟，也就是以 JSON 格式將 Google Analytics 事件匯出到 Google 雲端儲存空間。 只需按一下「**匯出 > 匯出到 GCS**」。 在那裡，資料已準備好可以被拉進 Adobe Experience Platform 中。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. 將資料從 Google 雲端儲存空間匯入到 Experience Platform 並對應到 XDM 結構描述

在 Experience Platform 中，選取「**[!UICONTROL 來源]**」，並找到「**[!UICONTROL Google 雲端儲存空間]**」選項。 在那裡，您只需尋找您已從 BigQuery 儲存的資料集。

請記住以下事項：

* 務必選取 JSON 格式。
* 您可以選取現有資料集，或是建立新資料集 (建議做法)。
* 請務必針對 Google Analytics 歷史資料和 Google Analytics 即時串流資料選取相同的結構描述，即便這兩者位在不同資料集中。 您之後可以在 [CJA 連線](/help/connections/combined-dataset.md)中合併資料集。

如需指示，請觀看這段影片：

>[!VIDEO](https://video.tv.adobe.com/v/332676)

您可以將 GA 事件資料對應到您之前建立的現有資料集中，或是使用您選擇的任何 XDM 結構描述建立新資料集。 當您選取結構描述後，Experience Platform 會套用機器學習，自動地將 Google Analytics 資料中的每個欄位預先對應到您的 [XDM 結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant#ui)。

![](assets/schema-map.png)

變更對應非常容易，您甚至可以從 Google Analytics 資料建立衍生欄位或計算欄位。 當您完成將欄位對應到 XDM 結構描述中的作業後，您可以將這項匯入排程為定期進行，並在擷取過程中套用錯誤驗證。 這樣可確保您已匯入的資料不會有任何問題。

**「Timestamp」計算欄位**

對於 Google Analytics 資料中的 `timestamp` 結構描述欄位，您必須在 Experience Platform 結構描述 UI 中建立特殊計算欄位。 按一下「**[!UICONTROL 新增計算欄位]**」，並將`timestamp`字串包裝在`date`函式中，如下所示：

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

然後，您需要將此計算欄位儲存到結構描述中的時間戳記資料結構內：

![](assets/timestamp.png)

**「_id」計算欄位**

`_id` 結構描述欄位中必須有值 - CJA 不在乎該值為何。 您可以只新增「1」到欄位中：

![](assets/_id.png)

## 擷取 Google Analytics 即時串流資料

您也可以從 Google 代碼管理工具將即時串流事件直接擷取到 Adobe Experience Platform。

### 1. 新增自訂變數

在登入 Google 代碼管理工具帳戶後，您需要新增一些與 Adobe 相關的自訂常數變數。 您或許在 Google 代碼管理工具中已經有變數正要傳送到 Google Analytics，例如客戶電子郵件、客戶名稱、語言及客戶登入狀態。 您需要定義 5 個新的自訂變數：

* Adobe Experience Cloud 組織 ID
* DCS 串流端點
* Experience Platform 資料集 ID
* 結構描述參考
* 頁面時間戳記

取得這些值可確保所有 Google Analytics 資料都會傳送到正確的資料集，並擁有正確的結構描述。 如果您不知道您的 Experience Cloud 組織或我們剛才提及的其他變數，您的 Adobe 客戶經理可以幫助您追查該資料。

在定義這些自訂變數後，您可以設定觸發條件，以便將您已傳送至 Google Analytics 的所有資料也傳送到 Experience Platform。

### 2. 在 Google 代碼管理工具中設定觸發條件

在此範例中，我們已定義「建立帳戶」觸發條件：`pageUrl equals account-creation`。 您可以在此觸發條件中新增一些資訊，以確保當使用者驗證成功而且載入帳戶建立頁面時，資料會傳送給 Google Analytics 和 AEP。

您也可以參考「[資料擷取與 Google 代碼管理工具](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=zh-Hant#module9)」。

如需指示，請觀看這段影片：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## 在 CJA 中建立與 Google Analytics 資料集的連線

當 Adobe Experience Platform 開始收到 Google Analytics 即時資料，而且您已回填來自 BigQuery 的 Google Analytics 歷史資料後，就表示您已準備好可以跳入 CJA 並[建立您的第一個連線](/help/connections/create-connection.md)。 此連線將會使用通用「客戶 ID」將 GA 資料與您的其他所有客戶資料拼接在一起。

## 後續步驟

* 根據包含 Google Analytics 資料的連線建立[資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hant#cja-dataviews)。

* 在工作區](/help/use-cases/ga-to-cja-reporting.md)中執行一些令人驚異的[分析。