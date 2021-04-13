---
title: 如何將Google Analytics資料匯入Adobe Experience Platform進行Customer Journey Analytics分析
description: '說明如何運用Customer Journey Analytics(CJA)將您的Google Analytics和Firebase資料收錄到Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# 將Google Analytics資料收錄到Adobe Experience Platform

此使用案例著重於如何將您的Google Analytics資料以資料集的形式收錄至Adobe Experience Platform。 （這同時套用至歷史和即時資料。） 完成後，您可以合併兩個資料集，以跨裝置檢視您的使用者歷程。

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
| **通用Google Analytics** | Google Analytics360 | 執行以下說明的步驟1 - 5 |
| **Google Analytics4** | 免費的GA版本或Google Analytics360 | 執行以下說明的步驟1和3-5。 不需要步驟2。 |

## 1.將您的Google Analytics資料連接至BigQuery

請注意，以下說明是以通用Google Analytics為基礎。

請參閱[這些說明](https://support.google.com/analytics/answer/3416092?hl=en)。

## 2.將Google Analytics作業轉換為BigQuery中的事件

>[!IMPORTANT]
>
>此步驟僅適用於Universal Analytics客戶

GA資料會將每個記錄儲存在其使用者作業階段的資料中，而非個別事件。 轉換資料可讓資料與Adobe Experience Platform相容。

請參閱[這些說明](https://support.google.com/analytics/answer/3437618?hl=en)。

您需要建立SQL查詢，將Universal Analytics資料轉換為符合Experience Platform的格式。 檢視此影片以取得指示：

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3.將JSON格式的Google Analytics事件匯出至Google雲端儲存區，並儲存至儲存貯體

請參閱[這些說明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。

## 4.將Google雲端儲存空間的資料帶入Experience Platform

檢視此影片以取得指示：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5.將GCS事件匯入Adobe Experience Platform並對應至XDM架構

BigQuery匯出結構(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
