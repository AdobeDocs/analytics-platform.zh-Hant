---
title: 使用Analytics資料連接器將行銷管道匯入CJA
description: 使用正確的Analytics資料連接器設定，將行銷管道處理規則匯入Adobe Experience Platform。
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# 使用Analytics資料連接器將行銷管道匯入CJA

如果您的組織使用[Analytics資料連接器](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sources/connectors/adobe-applications/analytics.html)將報表套裝資料匯入CJA，您可以在CJA中設定連線，以報告行銷管道維度。

## 必要條件

* 報表套裝資料必須已使用[Analytics資料連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html)匯入Adobe Experience Platform。
* 必須已設定行銷渠道處理規則。 請參閱傳統Analytics元件指南中的[行銷管道的處理規則](https://docs.adobe.com/content/help/zh-Hant/analytics/components/marketing-channels/c-rules.html)。

## 行銷渠道結構元素

在所要的報表套裝上使用Analytics資料連接器後，就會為您建立XDM架構。 此結構包含所有Analytics維度和量度作為原始資料。 此原始資料不包含歸因或永續性。 每個點擊會透過行銷渠道處理規則執行，並記錄其符合的第一個規則。 在CJA中建立資料檢視時，您可以指定歸因和永續性。

1. [建立以](/help/connections/create-connection.md) Analytics資料連接器為基礎的資料集所包含的連線。
2. [建立包含下](/help/data-views/create-dataview.md) 列維度的資料檢視：
   * **`channel.typeAtSource`**:相當於行銷 [管道](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) 維度。
   * **`channel._id`**:相當於行銷 [渠道詳情](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. 為每個維度提供所需的歸因模型和持續性。 如果您想要同時使用首次和上次接觸維度，請多次拖曳每個行銷渠道維度至元件區域。 為每個維度提供所需的歸因模型和持續性。 Adobe也建議為每個維度指定顯示名稱，以方便在工作區中使用。
4. 建立資料檢視。

您的行銷渠道維度現在可用於分析工作區。

## 處理與架構的差異

>[!IMPORTANT]
>
>報表套裝資料和平台資料之間有幾項基本資料差異。 Adobe強烈建議您調整報表套裝的行銷管道處理規則，以協助在平台中正確收集資料。


由於首次接觸和上次接觸渠道維度實質上是相同維度，且具有不同的歸因模型，因此您可以在[建立資料檢視](/help/data-views/create-dataview.md)時重新建立類似維度。 您可以根據相同的架構元素建立多個維度，為它們提供不同的歸因模型和持續性。

## Differences between

