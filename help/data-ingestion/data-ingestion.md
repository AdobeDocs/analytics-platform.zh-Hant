---
title: 資料擷取概觀
description: 了解您能夠將資料內嵌至 Customer Journey Analytics 的不同方式
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: dca1cc33058ba57815c3534ab21da86d5247531a
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 65%

---

# 資料擷取概觀

將資料擷取至Customer Journey Analytics時，有數個選項可供選擇。 有些選項能移動傳統 Adobe Analytics 資料，有些則能使用內嵌至 Adobe Experience Platform 的資料。

>[!IMPORTANT]
>
>在所有情況下，您想要在 Customer Journey Analytics 中&#x200B;_使用_&#x200B;的資料實際上是&#x200B;_擷取_&#x200B;自 Adobe Experience Platform。

請參閱前面[概觀](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)中所示的高階 Customer Journey Analytics：

本節中說明的![Customer Journey Analytics架構](./assets/cja-architecture.png)

上述架構中的資料集可能來自各種來源：

- 批次資料、

- 串流資料、

- 來自目前 Adobe Analytics 部署的資料、

- 資料來自於使用Adobe Experience Platform Web/Mobile SDK追蹤您的網站/行動應用程式，

- 使用Adobe Experience PlatformEdge Network伺服器API追蹤案頭應用程式、主機遊戲、機上盒或IoT裝置的資料，或

- 來自 Adobe 為其提供來源連接器之第三方資料提供者的資料。

您可以擁有許多這樣的資料集。

本文件的本節提供各種案例的快速入門指南。

## 擷取優先順序和延遲

無論資料是24小時、48小時還是7天前的資料，您都可以在90分鐘(SLT)內以Customer Journey Analytics擷取事件資料。

請注意，此功能的內容將根據貴公司購買的 SKU 封裝而有所不同。

- 優先擷取基本：90分鐘SLT處理內24小時前的資料（適用於&#x200B;**CJA Foundation**&#x200B;和&#x200B;**CJA Select**）

- 優先擷取中繼： 90分鐘SLT處理內72小時前的資料（適用於&#x200B;**CJA Prime**）

- 優先擷取進階： 90分鐘SLT處理內1週前的資料（適用於&#x200B;**CJA Ultimate**）

## 從傳統 Adobe Analytics 擷取和使用資料

您已部署 Adobe Analytics，且想要將此資料內嵌在 Adobe Experience Platform 中，並以 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[從傳統 Adobe Analytics 中擷取和使用資料](./analytics.md)。


## 透過Edge Network擷取及使用資料

### 使用Adobe Experience Platform Web SDK

您想要使用Adobe技術分析您的網站，可能從其他解決方案移轉，或開始追蹤您的人員行為。 您需要遵循 Adobe 的最佳實作方式 (使用 Adobe Experience Platform SDK 和 Edge Network) 來擷取資料。接著，您就可以在 Customer Journey Analytics 中將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

如需詳細資訊，請參閱[透過Adobe Experience Platform Web SDK擷取及使用資料](./aepwebsdk.md)。

### 使用Adobe Experience Platform Mobile SDK

您想要使用Adobe技術分析行動應用程式，可能從其他解決方案移轉，或是開始從頭開始追蹤使用者在應用程式中的行為。 您需要遵循 Adobe 的最佳實作方式 (使用 Adobe Experience Platform SDK 和 Edge Network) 來擷取資料。接著，您就可以在 Customer Journey Analytics 中將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

如需詳細資訊，請參閱[透過Adobe Experience Platform Mobile SDK擷取及使用資料](./aepmobilesdk.md)。

### 使用Adobe Experience PlatformEdge Network伺服器API

您想要分析您的案頭應用程式、在遊戲機上玩的遊戲、在機上盒或透過Adobe技術的IoT裝置上使用視訊串流應用程式。 可能從其他解決方案移轉，或從頭開始追蹤使用者在這些裝置上的行為。 您想要遵循Adobe的最佳實作方法，也就是使用Adobe Experience PlatformEdge Network伺服器API和Edge Network來擷取資料。 接著，您就可以在 Customer Journey Analytics 中將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

如需詳細資訊，請參閱[透過Adobe Experience PlatformEdge Network伺服器API擷取及使用資料](./serverapi.md)。

## 擷取和使用批次資料

您有相關的批次資料可提供詳細資訊，可協助您更了解客戶行為並分析客戶互動。此類批次資料的範例是來自 CRM 系統、忠誠度應用程式或其他解決方案 (Adobe 目前未提供來源連接器) 的 CSV、JSON 或 Parquet 格式的一般檔案。將此批次資料擷取至 Adobe Experience Platform，可讓您透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[擷取和使用批次資料](./batch.md)。

## 擷取和使用串流資料

您有 CRM 系統、ERP 系統等相關資料來源，或任何其他提供詳細資訊的來源，可協助您更了解客戶行為並分析客戶互動。該資料來源可透過 HTTP 或公用雲端串流基礎架構進行通訊，但 Adobe 目前未提供來源連接器。即時將此串流資料擷取至 Adobe Experience Platform，可讓您透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[擷取和使用串流資料](./streaming.md)。

## 使用來源連接器擷取和使用資料

來源連接器支援的來源中有資料可用。來源連接器是可配置的設定，可讓您將資料從 Adobe、第一方和第三方應用程式內嵌至 Adobe Experience Platform。如需可用來源連接器的概觀，請參閱[來源連接器概觀](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)。使用來源連接器，您可輕鬆將資料自來源擷取至 Adobe Experience Platform，接著透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[使用來源連接器擷取和使用資料](./sources.md)。
