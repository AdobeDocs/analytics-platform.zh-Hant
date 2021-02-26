---
title: Customer Journey Analytics 資料內嵌選項
description: 了解您能使用哪些方式將資料內嵌至 Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 8a3a868ff4e2fbbcdf83ff7769382c6a92f78ec2
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 100%

---


# Customer Journey Analytics 資料內嵌選項

Customer Journey Analytics 提供多種資料內嵌選項：有些選項能移動傳統 Adobe Analytics 資料，有些則能直接從 Adobe Experience Platform 內嵌資料。此參考資料提供了高層級步驟以供遵循，並附帶連結，提供更詳細的資訊。

## 從傳統 Adobe Analytics 內嵌資料

此工作流程利用 Adobe Analytics 資料連接器，視您使用 DTM 或 Launch 作為 Tag Manager 而會有所不同。

### 透過 Dynamic Tag Management (DTM)

1. [建立資料層](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/prepare/data-layer.html) (如果尚未建立)。資料層是網站上 JavaScript 物件的架構，包含實作的所有變數值，可讓您在實作中更進一步精細控制，並讓維護工作更簡單輕鬆。
1. 使用 [DTM](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/other/dtm/dtm-implementation-overview.html) 在您的網站上實作程式碼，以彙集資料 (如果尚未完成)。Dynamic Tag Management 提供單一資料層，可從多個來源推送資料。
1. 在 Adobe Experience Platform 中建立 [Adobe Analytics 來源連接器](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。此來源連接器會採用 [Experience Data Model (XDM) 系統](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/home.html)的標準化架構，將您的 Analytics 資料內嵌至 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

### 透過 Launch

1. [建立資料層](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) (如果尚未建立)。資料層是網站上 JavaScript 物件的架構，包含實作的所有變數值，可讓您在實作中更進一步精細控制，並讓維護工作更簡單輕鬆。
1. 使用 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/launch/overview.html) 在您的網站上實作程式碼，以彙集資料 (如果尚未完成)。Launch 為標籤管理解決方案，可讓您部署 Analytics 程式碼及滿足其他標籤需求。Launch 可與其他解決方案和產品整合，並能供您部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。
1. 在 Adobe Experience Platform 中建立 [Adobe Analytics 來源連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。此來源連接器會採用 [Experience Data Model (XDM) 系統](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html)的標準化架構，將您的 Analytics 資料內嵌至 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

## 透過 Adobe Experience Platform Web SDK 和 Edge Network 擷取資料

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant) 是用戶端的 JavaScript 程式庫，可讓 Adobe Experience Cloud 客戶透過 Adobe Experience Platform Edge Network 與 Experience Cloud 中的各種服務互動。

1. [在 Launch 中設定 AEP Web SDK 擴充功能](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=zh-Hant#configure-the-aep-web-sdk-extension) ，以透過 Adobe Experience Platform Edge Network，從網頁屬性傳送資料至 Adobe Experience Cloud。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

## 使用批次擷取和串流擷取來擷取資料

Adobe Experience Platform 將來自多個來源的資料彙集在一起，以協助行銷人員進一步瞭解客戶的行為。Adobe Experience Platform 資料擷取代表平台從這些來源擷取資料的多種方法，以及該資料如何保存在資料湖中，以供下游平台服務使用。

### 批次擷取

1. 設定[批次擷取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=zh-Hant#batch)，讓您將資料以批次檔案的形式擷取至 Adobe Experience Platform。所擷取的資料可以是 CRM 系統中平面檔案 (例如 parquet 檔案) 的設定檔資料，或是符合 Experience Data Model (XDM) 登錄檔中已知結構的資料。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

### 串流擷取

1. 設定[串流擷取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hant#streaming)可讓您即時從用戶端和伺服器端裝置傳送資料至 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

## 將 Google Analytics 資料匯入，在 Customer Journey Analytics 中進行分析

請參閱本教學課程，瞭解如何[使用 Customer Journey Analytics 分析 Google Analytics 資料](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=zh-Hant#objectives)，以取得詳細步驟。

## 使用大量資料插入 API 將資料匯入 Analytics，然後透過 Experience Platform 中的 Adobe Source Connector 進行擷取

1. [使用大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 將伺服器端集合資料提交至 Adobe Analytics。它可讓您提交包含事件資料的 CSV 格式檔案。
1. [建立 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)，將此消費者資料匯入 Adobe Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。