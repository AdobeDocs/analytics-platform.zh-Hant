---
title: 將串流Google Analytics資料設定至Adobe Experience Platform
description: 了解如何設定實作，將Google資料層傳送至Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# 將串流Google Analytics資料設定至Adobe Experience Platform

本頁著重於如何將即時Google Analytics資料內嵌至Adobe Experience Platform，讓您在Customer Journey Analytics的「資料檢視」中參照該資料集。 您可以結合本頁的步驟與 [將Google Analytics歷史資料內嵌至Adobe Experience Platform](backfill.md)，會產生包含歷史資料的資料集。 結合串流資料集和回填資料集，即可順暢檢視過去和以Customer Journey Analytics呈現資料。

設定資料收集涉及下列步驟：

1. 實作 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant). 請參閱 [快速入門手冊](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) 來啟動及執行基本實作。
1. 安裝 [Google資料層擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). 此擴充功能可替代安裝Web SDK擴充功能，尤其是針對Google資料層。
1. [建立資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) Adobe Experience Platform資料收集。 設定Datastream以傳送資料至Adobe Experience Platform。 您目前必須將每個Google資料層物件對應至此處的適用XDM欄位。 Adobe計畫在未來簡化此對應工作流程。

在網站上實作和發佈所需的標籤後，您就可以繼續 [建立連線](/help/connections/create-connection.md)，然後 [建立資料檢視](/help/data-views/create-dataview.md).
