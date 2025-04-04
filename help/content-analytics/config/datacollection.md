---
title: Content Analytics資料彙集
description: 概略說明如何在Content Analytics中收集資料
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: d4803af9b71ec245f6c4b20e92a4a4c99f235f00
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 1%

---

# Content Analytics資料彙集

{{release-limited-testing}}

本文詳細說明內容分析如何收集資料


## 定義

本文內容中使用下列定義：

* **體驗**：體驗定義為整個網頁上的文字內容。 對於資料收集，Content Analytics會根據頁面URL記錄體驗ID。 稍後，頁面上的文字會透過擷取服務擷取。
* **體驗ID**：相關URL （基底URL加上驅動頁面內容的任何引數）與[體驗版本](manual.md#versioning)的唯一組合。
   * 您在[組態](configuration.md)中指定與任何指定完整URL相關的引數。
   * 您可以定義使用的[版本識別碼](manual.md#versioning)。
* **資產**：影像。 Content Analytics會記錄資產URL。
* **資產識別碼**：資產的URL。
* **相關URL**：基底URL加上驅動頁面內容的任何引數。


## 功能

Content Analytics資料庫會在下列情況下收集資料：

* Content Analytics包含在頁面上載入的標籤程式庫中。
* 頁面URL是在[Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中設定，屬於包含的標籤程式庫的一部分。


## Content Analytics事件

Content Analytics事件包含：

* 標準欄位
   * 時間戳記
   * 身分識別
* 體驗檢視（如果有的話，以及如果已設定的話）
* 體驗點按次數（如果有的話，如果已設定）
* 資產檢視（如果有的話，如果已設定）
* 資產點選次數（如果有的話，如果已設定）


Content Analytics事件會依序收集：

1. [錄製的檢視或按一下](#recorded-view-or-click)。
1. [一般或特定（行為）事件](#regular-or-specific-behaviorial-event)。

Content Analytics確實會以這種方式收集資料來反映該順序，而不是收集檢視或點按，以與該檢視或點按之後立即收集事件分開。 這種收集內容分析資料的方式也會減少收集的資料量。 資料集合。

### 錄製的檢視或按一下

出現下列情況時，會記錄資產檢視：

* 並未根據Content Analytics擴充功能設定排除資產。
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


### 一般或特定（行為）事件

在Content Analytics上下文中引發一般或特定（行為）事件的觸發因素包括：

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

Content Analytics資料是根據特定的Experience Platform結構描述，在Content Analytics的資料集中收集。 可公開使用的參考結構描述：

* [數位資產結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [數位體驗結構描述](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [體驗事件內容結構描述](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
