---
title: 資料擷取概觀
description: 了解您能夠將資料內嵌至 Customer Journey Analytics 的不同方式
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 96%

---

# 資料擷取概觀

Customer Journey Analytics 提供多種資料內嵌選項：有些選項能移動傳統 Adobe Analytics 資料，有些則能使用內嵌至 Adobe Experience Platform 的資料。

>[!IMPORTANT]
>
>在所有情況下，您想要在 Customer Journey Analytics 中&#x200B;_使用_&#x200B;的資料實際上是&#x200B;_擷取_&#x200B;自 Adobe Experience Platform。


請參閱前面[概觀](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)中所示的高階 Customer Journey Analytics：

![Customer Journey Analytics](./assets/cja-architecture.png)

上述架構中的資料集可能來自各種來源：

- 批次資料、

- 串流資料、

- 來自目前 Adobe Analytics 部署的資料、

- 使用 Adobe Experience Platform Web/Mobile SDK 追蹤您的網站/行動應用程式的資料，或

- 來自 Adobe 為其提供來源連接器之第三方資料提供者的資料。

您可以擁有許多這樣的資料集。

本文件的本節提供各種案例的快速入門指南。

## 從傳統 Adobe Analytics 擷取和使用資料

您已部署 Adobe Analytics，且想要將此資料內嵌在 Adobe Experience Platform 中，並以 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[從傳統 Adobe Analytics 中擷取和使用資料](./analytics.md)。

## 透過 Adobe Experience Platform Web SDK 和 Edge Network 擷取和使用資料

您想要使用Adobe技術分析您的網站，可能從其他解決方案移轉，或開始追蹤您的人員行為。 您需要遵循 Adobe 的最佳實作方式 (使用 Adobe Experience Platform SDK 和 Edge Network) 來擷取資料。接著，您就可以在 Customer Journey Analytics 中將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

如需詳細資訊，請參閱[透過 Adobe Experience Platform Web SDK 和 Edge Network 擷取和使用資料](./aepwebsdk.md)。

## 擷取和使用批次資料

您有相關的批次資料可提供詳細資訊，可協助您更了解客戶行為並分析客戶互動。此類批次資料的範例是來自 CRM 系統、忠誠度應用程式或其他解決方案 (Adobe 目前未提供來源連接器) 的 CSV、JSON 或 Parquet 格式的一般檔案。將此批次資料擷取至 Adobe Experience Platform，可讓您透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[擷取和使用批次資料](./batch.md)。

## 擷取和使用串流資料

您有 CRM 系統、ERP 系統等相關資料來源，或任何其他提供詳細資訊的來源，可協助您更了解客戶行為並分析客戶互動。該資料來源可透過 HTTP 或公用雲端串流基礎架構進行通訊，但 Adobe 目前未提供來源連接器。即時將此串流資料擷取至 Adobe Experience Platform，可讓您透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[擷取和使用串流資料](./streaming.md)。

## 使用來源連接器擷取和使用資料

來源連接器支援的來源中有資料可用。來源連接器是可配置的設定，可讓您將資料從 Adobe、第一方和第三方應用程式內嵌至 Adobe Experience Platform。如需可用來源連接器的概觀，請參閱[來源連接器概觀](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)。使用來源連接器，您可輕鬆將資料自來源擷取至 Adobe Experience Platform，接著透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[使用來源連接器擷取和使用資料](./sources.md)。
