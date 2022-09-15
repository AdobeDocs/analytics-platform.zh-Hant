---
title: 在 Adobe Experience Platform 設定串流的 Google Analytics 資料
description: 了解如何設定您的實作，以傳送 Google 資料階層至 Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---

# 在 Adobe Experience Platform 設定串流的 Google Analytics 資料

此頁面著重於將您的即時 Google Analytics 資料擷取到 Adobe Experience Platform，讓您參照在 Customer Journey Analytics 之內「資料檢視」中的資料集。 您可以結合此頁面的步驟與[將 Google Analytics 歷史資料擷取至 Adobe Experience Platform](backfill.md)，這會產生包含歷史資料的資料集。結合串流的資料集與回填的資料集，以便在 Customer Journey Analytics 中取得過去與現在資料的無縫接軌檢視。

設定涉及以下步驟的資料彙集：

1. 實作 [ Adobe Experience Platform 的標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)。 請參閱 [快速入門指南](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) 以了解基本實作並執行。
1. 安裝 [Google Data Layer 延伸產品](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html)。 本延伸產品取代安裝 Web SDK 延伸產品，是特別針對 Google 資料階層所搭配的。
1. [在 Adobe Experience Platform Data Collection 中](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) 建立 Datastream。 設定 Datastream 以傳送資料至 Adobe Experience Platform。 您目前必須將每個 Google 資料階層物件對應到此處相關的 XDM 欄位。 Adobe 計畫在未來簡化此對應工作流程。

在您的網站上實作與發布想要的標籤之後，您可以繼續[建立連線](/help/connections/create-connection.md)，然後[建立資料檢視](/help/data-views/create-dataview.md)。
