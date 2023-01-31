---
title: Customer Journey Analytics 資料內嵌選項
description: 了解您能使用哪些方式將資料內嵌至 Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: ht
source-wordcount: '784'
ht-degree: 100%

---

# Customer Journey Analytics 資料內嵌選項

Customer Journey Analytics 提供多種資料內嵌選項：有些選項能移動傳統 Adobe Analytics 資料，有些則能直接從 Adobe Experience Platform 內嵌資料。此參考資料提供了高層級步驟以供遵循，並附帶連結，提供更詳細的資訊。

## 從傳統 Adobe Analytics 內嵌資料

此工作流程利用 Adobe Analytics 來源連接器，視您使用 DTM 或 Launch 作為 Tag Manager 而會有所不同。

### 透過 Adobe Experience Platform (之前稱之為 [!UICONTROL Launch]) 中的標記

1. [建立資料層](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=zh-Hant) (如果尚未建立)。資料層是網站上 JavaScript 物件的架構，包含實作的所有變數值，可讓您在實作中更進一步精細控制，並讓維護工作更簡單輕鬆。
1. 使用 [Adobe Experience Platform 標記](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=zh-Hant)在您的網站上實作程式碼，以彙集資料 (如尚未完成)。此標記管理解決方案可讓您部署 Analytics 程式碼以及其他標記需求。 標記提供和其他解決方案及產品的整合，並讓您部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。
1. 在 Adobe Experience Platform 中建立 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。此來源連接器會採用稱為[體驗資料模型 (XDM) 系統](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant)的標準化架構，將您的 Analytics 資料擷取至 Experience Platform。請參閱[在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hant) 建立一個或多個連線和資料檢視，以利您掌握跨管道的報告內容。

## 透過 Adobe Experience Platform Web SDK 和 Edge Network 擷取資料

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 是用戶端的 JavaScript 程式庫，可讓 Adobe Experience Cloud 客戶透過 Adobe Experience Platform Edge Network 與 Experience Cloud 中的各種服務互動。

1. [在標記 ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) 中設定 AEP Web SDK 擴充功能，以透過 Adobe Experience Platform Edge Network，從網頁屬性傳送資料至 Adobe Experience Cloud。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個[連線](/help/connections/create-connection.md)和[資料檢視](/help/data-views/data-views.md)，以利您掌握跨管道的報表內容。

## 使用批次擷取和串流擷取來擷取資料

Adobe Experience Platform 將來自多個來源的資料彙集在一起，以協助行銷人員進一步瞭解客戶的行為。Adobe Experience Platform 資料擷取代表平台從這些來源擷取資料的多種方法，以及該資料如何保存在資料湖中，以供下游平台服務使用。

### 批次擷取

1. 設定[批次擷取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html#batch)，讓您將資料以批次檔案的形式擷取至 Adobe Experience Platform。所擷取的資料可以是 CRM 系統中平面檔案 (例如 parquet 檔案) 的設定檔資料，或是符合 Experience Data Model (XDM) 登錄檔中已知結構的資料。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個[連線](/help/connections/create-connection.md)和[資料檢視](/help/data-views/data-views.md)，以利您掌握跨管道的報表內容。

### 串流擷取

1. 設定[串流擷取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html#streaming)可讓您即時從用戶端和伺服器端裝置傳送資料至 Experience Platform。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個[連線](/help/connections/create-connection.md)和[資料檢視](/help/data-views/data-views.md)，以利您掌握跨管道的報表內容。

## 將 Google Analytics 資料匯入，在 Customer Journey Analytics 中進行分析

請參閱本教學課程，瞭解如何[使用 Customer Journey Analytics 分析 Google Analytics 資料](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=zh-Hant)，以取得詳細步驟。

## 使用大量資料插入 API 將資料匯入 Analytics，然後透過 Experience Platform 中的 Adobe Source Connector 進行擷取

1. [使用大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 將伺服器端集合資料提交至 Adobe Analytics。它可讓您提交包含事件資料的 CSV 格式檔案。
1. [建立 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)，將此消費者資料匯入 Adobe Experience Platform。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hant) 建立一或多個[連線](/help/connections/create-connection.md)和[資料檢視](/help/data-views/data-views.md)，以利您掌握跨管道的報表內容。
