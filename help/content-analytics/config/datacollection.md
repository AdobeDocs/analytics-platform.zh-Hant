---
title: Content Analytics資料彙集
description: 瞭解如何在Content Analytics中收集資料。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
TQID: https://experienceleague.adobe.com/B2j6BrXAHMu-3LKI61LbK01i-UdpMlELsqYSfAWYDCo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1093
ht-degree: 52%

---


# Content Analytics 資料收集

本文詳細說明 Content Analytics 如何進行資料收集

## 定義

本文中使用到以下定義：

* **體驗**：
   * 對於&#x200B;**Web**&#x200B;管道，體驗定義為整個網頁上的文字內容。 對於資料收集，Content Analytics會根據頁面URL記錄體驗ID。 隨後，透過獲取服務擷取頁面上的文字。
   * 對於&#x200B;**行動裝置**&#x200B;頻道，已在行動應用程式中使用Adobe Experience Platform Mobile SDK的Content Analytics擴充功能定義和追蹤體驗。
* **體驗ID**：
   * 對於Web Channel，體驗ID是相關URL （基底URL加上驅動頁面內容的任何引數）和[體驗版本](manual.md#versioning)的唯一組合。
      * 您可以指定，做為[設定](configuration.md)的一部分，對於任何特定的完整 URL，哪些參數是相關的。
      * 您需定義出一個[版本識別碼](manual.md#versioning)來使用，藉以正確收集您的體驗變更。
   * 對於&#x200B;**行動裝置**&#x200B;頻道，體驗ID是使用`registerExperience` API呼叫的傳回值。
* **資產**：一個影像。 Content Analytics 會記錄資產 URL。
* **資產 ID**：資產的 URL。
* **相關 URL**：基底 URL 加上任何推動頁面內容的參數。


## 功能

Content Analytics需要Experience Platform Edge Network Web SDK （適用於網頁管道）和Experience Platform Edge Network Mobile SDK （適用於行動管道）來收集內容事件資料。 此事件資料會使用Experience Platform Edge Network （Web SDK、Mobile SDK或伺服器API）或Analytics來源聯結器（例如Adobe AppMeasurement），與現有行為資料結合。

Content Analytics 資料庫在以下情況下收集資料：

* Content Analytics包含在頁面上載入或用於行動應用程式的標籤資料庫中。
* 頁面URL和資產URL設定於[Content Analytics Web擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"} （包含標籤程式庫的一部分）。
* 資產URL、資產位置或體驗位置未排除在[Content Analytics行動擴充功能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)中。


## Content Analytics 事件

本節詳細說明網頁Content Analytics事件的細節。 如需行動Content Analytics事件的詳細資訊，請參閱[體驗追蹤](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/)。
Content Analytics 事件包括：

* 標準欄位
   * 時間戳記
   * 身分識別
* 體驗視圖 (若有，並且已設定)
* 體驗點按 (若有，並且已設定)
* 資產視圖 (若有，並且已設定)
* 資產點按 (若有，並且已設定)

Content Analytics 事件會依以下序列收集：

1. [錄製的檢視或按一下](#recorded-view-or-click)。
1. 用於傳送Content Analytics事件[&#128279;](#trigger-to-send-a-content-analytics-event)的觸發器。

Content Analytics 依此反映順序的方式確實收集資料，而不是將檢視或點按與其隨後的事件分開收集。 用這樣的方式收集 Content Analytics 資料也會減少所收集的資料量。

### 記錄的視圖或點按。

以下情況下會記錄資產視圖：

* 資產尚未根據 Content Analytics 擴充功能設定而排除。
* 資產已達到 75% 的視圖範圍。
* 資產尚未針對此頁面進行記錄。

以下情況下會記錄資產點按：

* 資產被檢視。
* 資產尚未根據 Content Analytics 擴充功能設定而排除。
* 直接按一下資產（連結）會前往另一個頁面。

以下情況下會記錄體驗視圖：

* 體驗在 Content Analytics 設定中啟用。

以下情況下會記錄體驗點按：

* 點選任何已啟用的連結就會觸發體驗。


### 傳送 Content Analytics 事件的觸發程序

為了減少從頁面傳送的網路要求數，Content Analytics會收集資訊，但不會立即傳送該資訊。 系統會收集內容互動資訊，且只會在發生下列其中一項觸發程序時傳送包含前述資訊的事件：

* 網頁SDK或Adobe AppMeasurement會傳送事件。
* 可見度轉變為隱藏，例如：
   * 頁面卸載
   * 切換索引標籤
   * 將瀏覽器縮到最小
   * 關閉瀏覽器
   * 鎖定畫面
* URL 發生變化，導致相關 URL 被修改。
* 已記錄且準備好傳送的資產檢視超過32次。

>[!NOTE]
>
>其他 Content Analytics 事件很可能會影響以工作階段或頁面中事件數量為基礎的任何跳出率定義。
>

## 身分識別

本節說明Content Analytics如何處理身分識別。

### Web

Content Analytics會透過下列方式處理Web Channel的身分識別：

* ECID 會自動填入至 Content Analytics 結構描述的 `identityMap` 部分。
* 如果您需要 `identityMap` 中其他身分識別值，則需在 Web SDK 擴充功能的 `onBeforeEventSend` 回呼中設定這些值。
* 因為此結構描述為系統所擁有，故不支援欄位式拚接。 因此，您無法新增其他欄位至結構描述來支援欄位式拼接


若要確保Content Analytics身分資料和Web SDK資料身分資料在欄位層級正確連結，請在事件傳送[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"}回呼之前修改Web SDK 。

1. 導覽至包含 Adobe Experience Platform Web SDK 擴充功能和 Adobe Content Analytics 擴充功能的&#x200B;**[!UICONTROL 標記]**&#x200B;屬性。
1. 選取「![插頭](/help/assets/icons/Plug.svg)**[!UICONTROL 擴充功能]**」。
1. 選取「**[!UICONTROL Adobe Experience Platform Web SDK]**」擴充功能。
1. 選取「**[!UICONTROL 設定]**」。
1. 在「**[!UICONTROL SDK 執行個體]**」區段中，向下捲動至「**[!UICONTROL 資料彙集]** - **[!UICONTROL On before event send 回呼]**」。

   ![On before event send 回呼](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. 選取「**[!UICONTROL &lt;/> 提供 on before event send 回呼程式碼]**」。
1. 新增下列程式碼：

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![On before event send 回呼](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. 選取「**[!UICONTROL 儲存]**」來儲存程式碼。
1. 選取「**[!UICONTROL 儲存]**」來儲存擴充功能。
1. [發佈](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/publish/overview)標記屬性的更新。


### Mobile

如需如何在行動應用程式中使用身分的詳細資訊，請參閱[Experience Cloud ID服務擴充功能的身分](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/)和[Edge Network行動擴充功能的身分](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)。

一旦行動應用程式中的身分變更，目前的Content Analytics資料[批次](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings)就會重設，以開始新身分的Content Analytics資料全新集合。

## 結構描述

Experience Platform會根據特定的Content Analytics結構描述，在資料集中收集Content Analytics資料。 參照結構描述為公開可用的：

* [數位資產結構](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [數位體驗結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [體驗事件內容結構描述](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
