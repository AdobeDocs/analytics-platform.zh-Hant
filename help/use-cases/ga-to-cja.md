---
title: 如何將Google Analytics資料匯入Adobe Experience Platform進行Customer Journey Analytics分析
description: '說明如何運用Customer Journey Analytics(CJA)將您的Google Analytics和Firebase資料收錄到Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: cc212d8b1e0a229fd246f6678a8dc8e5bbadce79
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 1%

---


# 將Google Analytics資料收錄到Adobe Experience Platform

此使用案例著重於如何將您的Google Analytics資料以資料集的形式收錄至Adobe Experience Platform。 我們將說明如何同時收錄歷史和即時資料。 完成後，您可以將兩個資料集合在Customer Journey Analytics中，以跨裝置檢視使用者歷程。

Experience Platform中的資料集由兩部分組成：模式和資料集中的實際記錄。 架構（簡稱「體驗資料模型」或XDM）就像資料集的欄，就像描述資料本身的藍圖或規則。 在平台中，Adobe提供2種模式：

* 立即可用的架構，您可將Google Analytics資料自動對應至（稱為「體驗事件」架構）
* 您可以建立並輕鬆將Google Analytics資料對應至

Adobe資料模型最強大的一個方面是，它可讓您將所有客戶互動資料標準化為一個共同架構——這可讓您在CJA中將資料整合在一起變得更輕鬆。

## 先決條件

要完成這些任務，您需要以下訪問權和權限：

* 訪問Adobe Experience Platform
* 存取通用Google Analytics(Google Analytics360版)或Google Analytics4(免費版本或Google Analytics360版)
* 存取Customer Journey Analytics及其[管理權限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant#admin-access-permissions)。

如何將Google Analytics資料匯入Adobe Experience Platform，取決於您使用的Google Analytics版本：

| 若您使用... | 您也需要這個授權…… | 然後…… |
| --- | --- | --- |
| **通用分析** | Google Analytics360 | 執行以下說明的步驟1 - 5 |
| **Google Analytics4** | 免費的GA版本或Google Analytics360 | 執行以下說明的步驟1和3-5。 不需要步驟2。 |

## 收錄歷史資料

### 1.將您的Google Analytics資料連接至BigQuery

請注意，以下說明是以通用Google Analytics為基礎。 它們適用於歷史資料。 如需即時串流資料的相關指示，請至「將即時串流資料匯入AEP」。

請參閱[這些說明](https://support.google.com/analytics/answer/3416092?hl=en)。

### 2.將Google Analytics作業轉換為BigQuery中的事件

>[!IMPORTANT]
>
>此步驟僅適用於Universal Analytics客戶

GA資料會將每個記錄儲存在其使用者作業階段的資料中，而非個別事件。 您需要建立SQL查詢，將Universal Analytics資料轉換為符合Experience Platform的格式。 您可將&quot;unnest&quot;函式套用至GA架構的&quot;hits&quot;欄位。 以下是您可以使用的SQL示例：

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimetimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

查詢完成後，將完整結果保存到BigQuery表中。

請參閱[這些說明](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)。

或者，觀賞此影片：

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3.將JSON格式的Google Analytics事件匯出至Google雲端儲存區，並儲存至儲存貯體

接著，您將以JSON格式將Google Analytics事件匯入Google雲端儲存空間。 然後你把它帶進Experience Platform。

請參閱[這些說明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。

### 4.將Google雲端儲存空間的資料帶入Experience Platform

在Experience Platform中，選擇&#x200B;**[!UICONTROL Sources]**&#x200B;並找到&#x200B;**[!UICONTROL Google雲端儲存區]**&#x200B;選項。 從那裡，您只需要找到從Big Query中儲存的資料集。

檢視此影片以取得指示：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5.將GCS事件匯入Adobe Experience Platform並對應至XDM架構

接著，您可以將GA事件資料映射至先前建立的現有資料集，或使用您選擇的XDM架構建立新資料集。 在您選擇了方案後，Experience Platform將應用機器學習自動將Google Analytics資料中的每個欄位映射到您自己的方案。

映射非常容易更改，您甚至可以從Google Analytics資料建立派生或計算欄位。 將欄位映射到XDM架構後，您可以定期安排此導入，並在提取過程中應用錯誤驗證。 這可確保您匯入的資料不會有任何問題。

## 收錄即時串流Google Analytics資料

您也可以從Google Tag Manager直接擷取即時串流事件至Adobe Experience Platform。

### 新增自訂變數

登入Google標籤管理員帳戶後，您需要新增與Adobe組織ID和資料集ID相關的自訂常數變數。 您可能已在Google標籤管理器中有變數會傳送至Google Analytics，例如客戶電子郵件、客戶名稱、語言和客戶登入狀態。 您需要定義5個新的自訂變數：

* Adobe Experience Cloud組織ID
* DCS串流端點
* Experience Platform資料集ID
* 架構參考
* 頁面時間戳記。

取得這些值可確保所有Google Analytics資料都會傳送至正確的資料集，並擁有正確的架構。 如果您不知道您的Experience Cloud組織或我們剛才提到的任何其他變數，您的Adobe客戶經理可協助您追蹤。

在您定義這些自訂變數後，我們可以設定觸發器，將您已傳送的所有資料傳送至Google Analytics至Experience Platform。

### 在Google標籤管理器中設定觸發器

在此範例中，已定義&quot;Account Creation&quot;觸發器，其中`pageUrl equals account-creation`。 借由將一些資訊新增至此觸發器，您可以確保當使用者成功驗證並載入帳戶建立頁面時，資料會同時傳送至Google Analytics和AEP。

如需指示，請檢視此影片：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

### 後續步驟

一旦Adobe Experience Platform開始接收即時Google Analytics資料，並且您從BigQuery回填歷史Google Analytics資料，您就可以跳到CJA並

1. [建立您的第](/help/connections/create-connection.md) 一個連接，使用通用的「客戶ID」將GA資料與所有其他客戶資料結合。
1. 在工作區中進行一些令人驚艷的分析，例如……

*此主題應停止，還是我們需要詳細說明連接的位置？*
