---
title: Customer Journey Analytics 資料內嵌選項
description: 了解您能使用哪些方式將資料內嵌至 Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 97%

---


# Customer Journey Analytics 資料內嵌選項

Customer Journey Analytics 提供多種資料內嵌選項：有些選項能移動傳統 Adobe Analytics 資料，有些則能直接從 Adobe Experience Platform 內嵌資料。此參考提供了要遵循的高級步驟，以及指向更詳細資訊的連結。

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
