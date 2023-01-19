---
title: 資料擷取概述
description: 了解您能使用哪些方式將資料內嵌至 Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 5de8c0daaa7eea0a9ab993d256e2b0a14f37301e
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 7%

---


# 資料擷取概述

Customer Journey Analytics 提供多種資料內嵌選項：其中部分假設您想要移動傳統Adobe Analytics資料，部分則假設您使用直接擷取至Adobe Experience Platform的資料。

>[!IMPORTANT]
>
>在所有情況下，您要 _use_ Customer Journey Analytics _攝入_ 在Adobe Experience Platform。


請參閱前面所示的高階Customer Journey Analytics架構， [概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en):

![客戶歷程分析](./assets/cja-architecture.png)

上述架構中的資料集可能來自多種來源：批次資料、串流資料、來自目前Adobe Analytics部署的資料、來自使用Adobe Experience Platform Web/Mobile SDK追蹤您網站/行動應用程式的資料，或來自第三方資料提供者(Adobe為其提供來源連接器)的資料。 你可以有很多這樣的資料集。

本檔案的本節提供多種案例的快速入門手冊。

## 從傳統Adobe Analytics擷取和使用資料

您已部署Adobe Analytics，且想要將此資料內嵌在Adobe Experience Platform中，並透過Customer Journey Analytics中其他管道和資料來源的資料來使用、結合及分析資料。

請參閱 [從傳統Adobe Analytics擷取和使用資料](./analytics.md) 以取得更多資訊。

## 透過Adobe Experience Platform Web SDK和邊緣網路擷取和使用資料

您想要使用Adobe技術分析網站，可能是從其他解決方案移轉，或開始追蹤訪客的行為。 您想要遵循Adobe的最佳實務實務(使用Adobe Experience Platform SDK和邊緣網路)來內嵌資料。 接著，您就可以在Customer Journey Analytics中，將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

請參閱 [透過Adobe Experience Platform Web SDK和邊緣網路擷取和使用資料](./aepwebsdk.md) 以取得更多資訊。

## 擷取及使用批次資料

您有相關的批次資料可提供詳細資訊，以協助您更清楚了解客戶行為並分析客戶互動。 此類批次資料的範例是來自CRM系統、忠誠度應用程式或其他解決方案(Adobe目前未提供來源連接器)的CSV、JSON或Parquet格式的平面檔案。 將此批次資料擷取至Adobe Experience Platform，可讓您透過Customer Journey Analytics中其他管道和資料來源的資料來使用、結合及分析資料。

請參閱 [擷取及使用批次資料](./batch.md) 以取得更多資訊。

## 擷取和使用串流資料

您有CRM系統、ERP系統或任何其他來源等相關資料來源，這些來源提供詳細資訊，可協助您更清楚了解客戶行為並分析客戶互動。 該資料來源可透過HTTP或公用雲端串流基礎架構進行通訊，但Adobe目前未提供來源連接器。 即時將此串流資料擷取至Adobe Experience Platform，可讓您以Customer Journey Analytics方式使用、結合及分析其他管道和資料來源的資料。

請參閱 [擷取和使用串流資料](./streaming.md) 以取得更多資訊。

## 使用來源連接器擷取和使用資料

源連接器支援的源中有資料可用。 來源連接器是可設定的設定，可讓您將資料從Adobe、第一方和第三方應用程式內嵌至Adobe Experience Platform。 請參閱 [來源連接器概觀](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant) 以取得可用來源連接器的概觀。 使用來源連接器，您可輕鬆將來源的資料內嵌至Adobe Experience Platform，接著以Customer Journey Analytics方式使用、結合及分析其他管道和資料來源的資料。

請參閱 [使用來源連接器擷取和使用資料](./sources.md) 以取得更多資訊。

