---
title: 在Customer Journey Analytics中設定Google Analytics報告
description: null
translation-type: tm+mt
source-git-commit: c07d32eef579432bf92f94cbbe4e99188b2de74c
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---


# 在Customer Journey Analytics中設定Google Analytics報告

設定Google雲端儲存連接器，

設定Google標籤管理器

BigQuery匯出結構(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. 將GA工作階段轉換為Big Query中的事件
1. 將Google Analytics事件匯出至Google雲端儲存空間
1. 將GCS事件匯入Adobe Experience Platform並對應至XDM架構

## 先決條件

* 訪問Adobe Experience Platform
* 存取通用Google Analytics(Google Analytics360版)或Google Analytics4(免費版本或Google Analytics360版)
* 存取Customer Journey Analytics

## 1.將Google Analytics資料連接至Adobe Experience Platform

如何將Google Analytics資料匯入Adobe Experience Platform，取決於您使用的Google Analytics版本：

| 若您使用... | 您也需要這個授權…… | 然後…… |
| --- | --- | --- |
| **通用Google Analytics** | Google Analytics360 | 執行以下說明的步驟1 - x |
| **Google Analytics4** | 免費的GA版本或Google Analytics360 | 不需要下列說明中的步驟x。 |

以下說明以通用Google Analytics為基礎。

1. 將您的Google Analytics資料連接至BigQuery，並
請參閱[這些說明](https://support.google.com/analytics/answer/3416092?hl=en)。
1. （僅限Universal Analytics客戶）將Google Analytics工作階段轉換為BigQuery中的事件。 這使得資料與Adobe Experience Platform相容。 請參閱[這些說明](https://support.google.com/analytics/answer/3437618?hl=en)。

   詳細資訊：在BigQuery中，您的GA資料將顯示為表格：

   ![](assets/ga-bigquery.png)
您需要建立SQL查詢，將Universal Analytics資料轉換為符合Experience Platform的格式。
   * 檢視此影片以取得指示。

1. 將JSON格式的Google Analytics事件匯出至Google Cloud儲存區，並儲存至儲存貯體。
請參閱[這些說明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。
1. 將Google雲端儲存空間的資料匯入Experience Platform。 （取得Trevor投影片10影片）。

