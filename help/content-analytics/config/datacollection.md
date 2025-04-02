---
title: Content Analytics資料彙集
description: 概略說明如何在Content Analytics中收集資料
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Content Analytics資料彙集

本文詳細說明內容分析如何收集資料


## 定義

本文內容中使用下列定義：

* **體驗**：體驗定義為整個網頁上的文字內容。 對於資料收集，Content Analytics會記錄該體驗ID。 Content Analytics不會在頁面上記錄文字。
* **資產**：影像。 Content Analytics會記錄資產URL。
* **相關URL**：基底URL加上驅動頁面內容的任何引數。
* **體驗ID**：相關URL和體驗版本的唯一組合。
   * 您在[組態](configuration.md)中指定與任何指定完整URL相關的引數。
   * 您可以定義使用的[版本識別碼](manual.md#versioning)。 對於資料彙集，不考慮版本。 只會收集相關的url。

## 功能

Content Analytics資料庫會在下列情況下收集資料：

* Content Analytics包含在頁面上載入的標籤程式庫中。
* 頁面URL是在[Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中設定，屬於包含的標籤程式庫的一部分。


### Content Analytics事件

Content Analytics事件包含：

* 標準欄位
   * 時間戳記
   * 身分識別
* 體驗檢視（如果有的話，以及如果已設定的話）
* 體驗點按次數（如果有的話，如果已設定）
* 資產檢視（如果有的話，如果已設定）
* 資產點選次數（如果有的話，如果已設定）

#### 已記錄的檢視或點按

出現下列情況時，會記錄資產檢視：

* 並未根據ACA擴充功能設定排除資產。
* 資產檢視率為75%。
* 尚未針對此頁面記錄該資產。

出現下列情況時，會記錄資產點按：

* 已檢視資產。
* 並未根據ACA擴充功能設定排除資產。
* 直接按一下資產（連結）即可進入另一個頁面。

在下列情況下會記錄體驗檢視：

* 體驗會在Content Analytics設定中啟用。

發生下列情況時，會記錄一次體驗點按：

* 在啟用體驗的頁面上的連結上，只要按一下，就會出現。


#### 已傳送事件

Content Analytics事件會在下列兩個情況發生時傳送：

* 傳送內容，此狀況發生於：

   * 資產檢視或點按會被記錄。
   * 將會記錄體驗檢視或點按。

* 會觸發傳送事件的觸發程式，觸發程式發生於：

   * Web SDK或AppMeasurement會傳送事件。
   * 可視性會變更為隱藏，例如：
      * 頁面取消載入
      * 切換標籤
      * 將瀏覽器最小化
      * 關閉瀏覽器
      * 鎖定畫面
   * URL變更，導致相關的URL被修改。
   * 資產檢視超過批次限制32。


## 結構描述

Content Analytics資料是根據特定的Experience Platform結構描述，在Content Analytics的資料集中收集。 參考結構描述可供公開使用，並用於Content Analytics的預設實施。

* [數位資產結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [數位體驗結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [體驗事件內容結構描述](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
