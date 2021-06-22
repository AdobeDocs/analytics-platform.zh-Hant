---
title: 將Google Analytics資料內嵌至Adobe Experience Platform
description: '說明如何運用Customer Journey Analytics(CJA)將Google Analytics資料內嵌至Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
source-git-commit: 316819116e9b47110763479af4e8504a2bffaff3
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 7%

---


# 將Google Analytics資料內嵌至Adobe Experience Platform

此使用案例著重於如何將Google Analytics資料以資料集的形式內嵌至Adobe Experience Platform。 我們會說明如何擷取歷史和即時資料。 完成後，您可以將兩個資料集合併成Customer Journey Analytics，以跨裝置檢視使用者的歷程。

Experience Platform中的資料集由兩部分組成：結構和資料集中的實際記錄。 結構（簡稱為「體驗資料模型」或XDM）類似資料集的欄，也類似於描述資料本身的Blueprint或規則。 在Platform中，Adobe提供2種結構描述：

* 可自動將Google Analytics資料對應至的現成可用結構（稱為體驗事件結構）
* 您可以建立並輕鬆將Google Analytics資料對應至的自訂結構

Adobe資料模型最強大的一個方面，是可讓您將所有客戶互動資料標準化為一個通用結構 — 這可讓您在CJA中將資料匯整在一起更輕鬆。

## 先決條件

若要完成這些工作，您需要下列存取權和權限：

* Adobe Experience Platform 的存取權
* Universal Google Analytics (Google Analytics 360 版本) 或是 Google Analytics 4 (免費版本或 Google Analytics 360 版本) 的存取權
* Customer Journey Analytics 的存取權 及其[管理權限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant#admin-access-permissions)。

如何將 Google Analytics 資料帶入 Adobe Experience Platform 取決於您使用的 Google Analytics 版本：

| 若您使用... | 您也需要的授權... | 以及需執行... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | 執行以下說明的步驟1-3 |
| **Google Analytics 4** | Free GA 版本或 Google Analytics 360 | 執行以下說明的步驟1和步驟3。 不需要步驟2。 |

## 內嵌歷史（回填）資料

### 1.將Google Analytics資料連接到BigQuery

有關詳細資訊，請參閱[這些說明](https://support.google.com/analytics/answer/3416092?hl=en)。 請注意，這些指示是以通用Google Analytics為基礎。

### 2.將Google Analytics工作階段轉換為BigQuery中的事件，並匯出至Google雲端儲存空間

>[!IMPORTANT]
>
>此步驟僅適用於Universal Analytics客戶

GA資料會將每個記錄儲存在其使用者工作階段的資料中，而非個別事件。 您需要建立SQL查詢，將通用Analytics資料轉換為符合Experience Platform的格式。 您將「取消巢狀內嵌」函式套用至GA架構的「點擊」欄位。 以下是您可以使用的SQL範例：

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

查詢完成後，將完成的結果保存到BigQuery表中。

請參閱[這些指示](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)，其中包括有關SQL查詢的指示。

下列影片也說明下一步，即將Google Analytics事件以JSON格式匯出至Google雲端儲存空間。 只需按一下「**導出>導出到GCS**」即可。 資料一旦準備就緒，即可提取至Adobe Experience Platform。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3.將資料從Google雲端儲存區匯入Experience Platform，並對應至XDM結構

在Experience Platform中，選擇&#x200B;**[!UICONTROL Sources]**&#x200B;並查找&#x200B;**[!UICONTROL Google雲儲存]**&#x200B;選項。 從那裡，您只需要找到從BigQuery儲存的資料集即可。

請記住：

* 請務必選取JSON格式。
* 您可以選取現有資料集或建立新資料集（建議）。
* 請務必為歷史Google Analytics資料和即時串流Google Analytics資料選取相同的結構，即使它們位於不同的資料集中亦然。 您隨後可以合併[CJA連線](/help/connections/combined-dataset.md)中的資料集。

如需指示，請觀看此影片：

>[!VIDEO](https://video.tv.adobe.com/v/332676)

您可以將GA事件資料對應至先前建立的現有資料集，或使用您選擇的XDM結構建立新資料集。 選取結構後，Experience Platform會套用機器學習，以自動將Google Analytics資料中的每個欄位預先對應至您的[XDM結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui)。

![](assets/schema-map.png)

映射非常容易更改，您甚至可以從Google Analytics資料建立派生欄位或計算欄位。 將欄位對應至XDM架構後，您可以重複排程此匯入，並在擷取程式期間套用錯誤驗證。 這可確保您匯入的資料沒有任何問題。

**「時間戳記」計算欄位**

對於Google Analytics資料中的`timestamp`架構欄位，您必須在Experience Platform架構UI中建立特殊的計算欄位。 按一下「**[!UICONTROL 新增計算欄位]**」，並將`timestamp`字串包裝在`date`函式中，如下所示：

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

然後，您需要將此計算欄位儲存至架構中的時間戳記資料結構：

![](assets/timestamp.png)

**「_id」計算欄位**

`_id`結構欄位中必須有值 — CJA不在乎值。 您只需新增「1」至欄位即可：

![](assets/_id.png)

## 內嵌即時串流Google Analytics資料

您也可以直接將即時串流事件從Google Tag Manager擷取到Adobe Experience Platform。

### 1.新增自訂變數

登入Google Tag Manager帳戶後，您需要新增一些與Adobe相關的自訂常數變數。 您可能已在Google Tag Manager中有要傳送至Google Analytic的變數，例如客戶電子郵件、客戶名稱、語言和客戶登入狀態。 您需要定義5個新的自訂變數：

* Adobe Experience Cloud組織ID
* DCS串流端點
* Experience Platform資料集ID
* 結構參考
* 頁面時間戳記

取得這些值可確保所有Google Analytics資料都傳送至正確的資料集，且具有正確的結構。 如果您不知道您的Experience Cloud組織或我們剛才提到的任何其他變數，您的Adobe客戶經理可協助您追蹤。

定義這些自訂變數後，我們就可以設定觸發器，將您已傳送的所有資料傳送至Google Analytics至Experience Platform。

### 2.在Google Tag Manager中設定觸發程式

在此範例中，已定義「帳戶建立」觸發器，其中`pageUrl equals account-creation`。 將一些資訊新增至此觸發器後，您即可確保當使用者成功驗證且帳戶建立頁面載入時，資料會同時傳送至Google Analytics和AEP。

您也可以參閱[資料擷取和Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9)。

如需指示，請觀看此影片：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## 在CJA中建立與Google Analytics資料集的連線

一旦Adobe Experience Platform開始接收即時Google Analytics資料，且您已回填來自BigQuery的歷史Google Analytics資料，您就可以跳至CJA，並[建立您的第一個連線](/help/connections/create-connection.md)。 此連線會使用通用的「客戶ID」，將GA資料與所有其他客戶資料匯整在一起。

## 後續步驟

* 根據包含Google Analytics資料的連線，建立[資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews)。

* 在工作區](/help/use-cases/ga-to-cja-reporting.md)中執行一些令人驚異的[分析。