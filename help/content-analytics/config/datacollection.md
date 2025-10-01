---
title: Content Analytics 資料收集
description: Content Analytics 資料收集方式概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 79%

---

# Content Analytics 資料收集

本文詳細說明 Content Analytics 如何進行資料收集

## 定義

本文中使用到以下定義：

* **體驗**：體驗定義為整個網頁上的文字內容。對於資料收集，Content Analytics 會記錄以頁面 URL 為基礎的體驗 ID。隨後，透過獲取服務擷取頁面上的文字。
* **體驗 ID**：相關 URL (基底 URL 加上任何推動頁面內容的參數) 和[體驗版本](manual.md#versioning)的獨特組合。
   * 您可以指定，做為[設定](configuration.md)的一部分，對於任何特定的完整 URL，哪些參數是相關的。
   * 您需定義出一個[版本識別碼](manual.md#versioning)來使用，藉以正確收集您的體驗變更。
* **資產**：一個影像。Content Analytics 會記錄資產 URL。
* **資產 ID**：資產的 URL。
* **相關 URL**：基底 URL 加上任何推動頁面內容的參數。


## 功能

Content Analytics 需要 Experience Platform Edge Network Web SDK 來收集內容事件資料。該事件資料收集會透過Experience Platform Edge Network (網頁SDK、伺服器API)或Analytics來源聯結器(例如使用AppMeasurement)之類的機制，與行為事件資料的（現有）資料收集結合。

Content Analytics 資料庫在以下情況下收集資料：

* Content Analytics 包含在頁面上載入的標記資料庫中。
* 頁面 URL 在 [Content Analytics 擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中進行設定，其為所包含之標記資料庫的一部分。


## Content Analytics 事件

Content Analytics 事件包括：

* 標準欄位
   * 時間戳記
   * 身分識別
* 體驗視圖 (若有，並且已設定)
* 體驗點按 (若有，並且已設定)
* 資產視圖 (若有，並且已設定)
* 資產點按 (若有，並且已設定)

Content Analytics 事件會依以下序列收集：

1. [記錄的視圖或點按](#recorded-view-or-click)。
1. [傳送Content Analytics事件的觸發程式](#trigger-to-send-a-content-analytics-event)。

Content Analytics 確實以此方式收集資料，藉以反映該序列，而非將收集視圖或點按，與收集該視圖或點按之後立即發生的事件分開。這種收集Content Analytics資料的方式也會減少收集的資料量。

### 記錄的視圖或點按。

以下情況下會記錄資產視圖：

* 資產尚未根據 Content Analytics 擴充功能設定而排除。
* 資產已達到 75% 的視圖範圍。
* 資產尚未針對此頁面進行記錄。

以下情況下會記錄資產點按：

* 資產被檢視。
* 資產尚未根據 Content Analytics 擴充功能設定而排除。
* 直接點按資產 (其為一個連結)，而前往另一個頁面。

以下情況下會記錄體驗視圖：

* 體驗在 Content Analytics 設定中啟用。

以下情況下會記錄體驗點按：

* 針對啟用體驗之頁面上的連結進行的任何點按。


### 觸發以傳送Content Analytics事件

為了減少離開頁面的呼叫數，Content Analytics會收集資訊，但不會立即傳送該資訊。 系統會收集內容互動資訊，並僅在發生下列其中一項觸發時傳送包含該資訊的事件：

* Web SDK 或 AppMeasurements 傳送事件。
* 可見度轉變為隱藏，例如：
   * 頁面卸載
   * 切換索引標籤
   * 將瀏覽器縮到最小
   * 關閉瀏覽器
   * 鎖定畫面
* URL 發生變化，導致相關 URL 被修改。
* 已記錄並準備就緒可以傳送的資產視圖數量超過 32。

>[!NOTE]
>
>其他Content Analytics事件極可能會影響任何以工作階段或頁面中的事件數量為基礎的跳出率定義。
>


## 結構描述

Content Analytics 資料會根據特定的 Content Analytics 結構描述收集於 Experience Platform 的資料集中。參照結構描述為公開可用的：

* [數位資產結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [數位體驗結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [體驗事件內容結構描述](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
