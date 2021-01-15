---
title: Customer Journey Analytics 資料內嵌選項
description: 了解您能使用哪些方式將資料內嵌至 Customer Journey Analytics
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 61%

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

## 透過Adobe Experience Platform Web SDK和Edge Network收錄資料

[Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDK是用戶端的JavaScript程式庫，可讓Adobe Experience Cloud客戶透過Adobe Experience Platform Edge Network與Experience Cloud中的各種服務互動。您可以設定此擷取功能，不論是否包含Launch。

### 未啟動

此連結無法運作：https://docs.adobe.com/content/help/en/experience-platform/edge/get-started/quick-start-without-launch.html。 沒有Launch，還是有可能嗎？

### 使用Launch

1. [設定AEP Web SDK擴充](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) 功能，透過Adobe Experience Platform Edge Network，從Web屬性將資料傳送至Adobe Experience Cloud。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

## 使用批次擷取和串流擷取來擷取資料

Adobe Experience Platform將來自多個來源的資料匯集在一起，以協助行銷人員更好地瞭解客戶的行為。 Adobe Experience Platform資料擷取代表平台從這些來源擷取資料的多種方法，以及該資料如何保存在資料湖中，以供下游平台服務使用。

### 批次擷取

1. 設定[批次擷取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch)，讓您將資料以批次檔案的形式內嵌至Adobe Experience Platform。 所吸收的資料可以是CRM系統中平面檔案（例如鑲木地板檔案）的描述檔資料，或是符合Experience Data Model(XDM)註冊表中已知架構的資料。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

### 串流擷取

1. 設定[串流擷取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming)，即時從用戶端和伺服器端裝置傳送資料至Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。

## 將Google Analytics資料匯入客戶歷程分析

請參閱本教學課程，瞭解如何使用客戶歷程分析](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives)分析Google Analytics資料，以取得詳細步驟。[

## 使用大量資料插入API將資料匯入Analytics，然後透過Experience Platform中的Adobe Source Connector進行收錄

1. [使用大量資料插](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 入API將伺服器端收集資料送出至Adobe Analytics。它可讓您提交包含事件資料的CSV格式檔案。
1. [建立Adobe Analytics來源連](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) 線器，將此消費者資料匯入Adobe Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 建立一或多個連線和資料檢視，以利您掌握跨管道的報表內容。