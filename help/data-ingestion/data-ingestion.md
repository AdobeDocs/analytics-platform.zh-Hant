---
title: 資料擷取概觀
description: 了解您能夠將資料內嵌至 Customer Journey Analytics 的不同方式
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 85%

---

# 資料攝取概觀

在將資料匯入 Customer Journey Analytics 時有許多種選項。有些選項能移動傳統 Adobe Analytics 資料，有些則能使用內嵌至 Adobe Experience Platform 的資料。

>[!IMPORTANT]
>
>在所有情況下，您想要在 Customer Journey Analytics 中&#x200B;_使用_&#x200B;的資料實際上是&#x200B;_擷取_&#x200B;自 Adobe Experience Platform。


高層級 Customer Journey Analytics 架構如下所示：

![Customer Journey Analytics架構](/help/getting-started/assets/cja-overview.svg)

此架構說明了Customer Journey Analytics如何讓您：

* 在![連線](/help/assets/icons/Data.svg)中合併多個資料集[資料](/help/connections/overview.md)。
* 根據您在連線中定義的資料集可用欄位，在![資料檢視](/help/assets/icons/Dimensions.svg)中定義及設定維度![維度](/help/assets/icons/Event.svg)和量度[事件](/help/data-views/data-views.md)。
* 根據資料檢視的維度和量度，在![專案](/help/assets/icons/ViewTable.svg)中建置報告![ViewTable](/help/assets/icons/GraphTrend.svg)和視覺效果（例如行![行](/help/assets/icons/GraphAreaStacked.svg)和區域[區域](/help/analysis-workspace/home.md)）。

架構中的資料集可源自於各種來源：

* 批次資料、

* 串流資料、

* 來自目前 Adobe Analytics 部署的資料、

* 使用 Adobe Experience Platform Web/Mobile SDK 追蹤您網站/行動應用程式的資料，

* 使用 Adobe Experience Platform Edge Network Server API 追蹤桌面應用程式、遊戲機、機上盒或 IoT 裝置的資料，或

* 來自 Adobe 為其提供來源連接器之第三方資料提供者的資料。

您可以擁有許多這樣的資料集。

本文件的本節提供各種案例的快速入門指南。

## 攝取優先順序和延遲

您可以在 90 分鐘內 (SLT)，攝取 24 小時、48 小時或 7 天內的 Customer Journey Analytics 事件資料。

請注意，此功能的內容將根據貴公司購買的 SKU 封裝而有所不同。

* Priority Ingestion Basic：在 90 分鐘 (SLT) 內，處理 24 小時內的資料 (適用於 **CJA Foundation** 和 **CJA Select**)

* Priority Ingestion Intermediate：在 90 分鐘 (SLT) 內，處理 72 小時內的資料 (適用於 **CJA Prime**)

* Priority Ingestion Advanced：在 90 分鐘 (SLT) 內，處理 1 週內的資料 (適用於 **CJA Ultimate**)

## 從傳統 Adobe Analytics 擷取和使用資料

您已部署 Adobe Analytics，且想要將此資料內嵌在 Adobe Experience Platform 中，並以 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[從傳統 Adobe Analytics 中擷取和使用資料](./analytics.md)。


## 透過 Edge Network 攝取和使用資料

### 使用 Adobe Experience Platform Web SDK

您想要使用 Adobe 技術分析您的網站，可能是從另一個解決方案移轉，或開始追蹤您個人的行為。您需要遵循 Adobe 的最佳實作方式 (使用 Adobe Experience Platform SDK 和 Edge Network) 來擷取資料。接著，您就可以在 Customer Journey Analytics 中將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

請參閱[透過 Adobe Experience Platform Web SDK 攝取和使用資料](./aepwebsdk.md)，以了解更多資訊。

### 使用 Adobe Experience Platform Mobile SDK

您想要使用 Adobe 技術分析您的行動應用程式，可能是從另一個解決方案移轉，或從頭開始追蹤應用程式的使用者行為。您需要遵循 Adobe 的最佳實作方式 (使用 Adobe Experience Platform SDK 和 Edge Network) 來擷取資料。接著，您就可以在 Customer Journey Analytics 中將擷取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

請參閱[透過 Adobe Experience Platform Mobile SDK 攝取和使用資料](./aepmobilesdk.md)，以了解更多資訊。

### 使用 Adobe Experience Platform Edge Network Server API

您想使用 Adobe 技術分析您的桌面應用程式、在遊戲機上玩的遊戲、機上盒影片串流應用程式的使用情況或您的 IoT 裝置。可能是從另一個解決方案移轉，或從頭開始追蹤這些裝置的使用者行為。您想要遵循 Adobe 實作的最佳做法 (使用 Adobe Experience Platform Edge Network Server API 和 Edge Network) 來攝取資料。接著，您就可以在 Customer Journey Analytics 中將攝取的資料與來自其他管道和資料來源的資料搭配使用、結合及分析。

請參閱[透過 Adobe Experience Platform Edge Network Server API 攝取和使用資料](./serverapi.md)，以了解更多資訊。

## 擷取和使用批次資料

您有相關的批次資料可提供詳細資訊，可協助您更了解客戶行為並分析客戶互動。此類批次資料的範例是來自 CRM 系統、忠誠度應用程式或其他解決方案 (Adobe 目前未提供來源連接器) 的 CSV、JSON 或 Parquet 格式的一般檔案。將此批次資料擷取至 Adobe Experience Platform，可讓您透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[擷取和使用批次資料](./batch.md)。

## 擷取和使用串流資料

您有 CRM 系統、ERP 系統等相關資料來源，或任何其他提供詳細資訊的來源，可協助您更了解客戶行為並分析客戶互動。該資料來源可透過 HTTP 或公用雲端串流基礎架構進行通訊，但 Adobe 目前未提供來源連接器。即時將此串流資料擷取至 Adobe Experience Platform，可讓您透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[擷取和使用串流資料](./streaming.md)。

## 使用來源連接器擷取和使用資料

來源連接器支援的來源中有資料可用。來源連接器是可配置的設定，可讓您將資料從 Adobe、第一方和第三方應用程式內嵌至 Adobe Experience Platform。如需可用來源連接器的概觀，請參閱[來源連接器概觀](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)。使用來源連接器，您可輕鬆將資料自來源擷取至 Adobe Experience Platform，接著透過 Customer Journey Analytics 中其他管道和資料來源的資料來使用、合併及分析資料。

如需詳細資訊，請參閱[使用來源連接器擷取和使用資料](./sources.md)。

## 擷取及使用臨時資料

您有臨機操作資料，在Experience Platform中只需要單一資料集，不需要設定體驗資料模型(XDM)結構描述。 此情境稱為臨時結構描述。 臨時結構描述用於Experience Platform的各種資料擷取工作流程，包括擷取CSV檔案和建立特定型別的來源連線。

檢視[擷取及使用臨時資料](./adhoc.md)

>[!MORELIKETHIS]
>
>部落格：[深入了解 Adobe Customer Journey Analytics 中的資料處理和攝取](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091)

