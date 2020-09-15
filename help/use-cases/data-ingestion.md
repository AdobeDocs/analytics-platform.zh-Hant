---
title: 客戶歷程分析的資料擷取選項
description: 瞭解將資料收錄至客戶歷程分析的不同方式
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 27%

---


# 客戶歷程分析的資料擷取選項

在將資料吸收至客戶歷程分析時，您有許多選項。 有的假設您要移動傳統Adobe Analytics資料，有的則假設您直接從Adobe Experience Platform中收集資料。 此參考提供了要遵循的高級步驟，以及指向更詳細資訊的連結。

## 從傳統Adobe Analytics中收錄資料

此工作流程利用Adobe Analytics資料連接器，並視您使用DTM或Launch做為標籤管理器而有所不同。

### 透過動態標籤管理(DTM)

1. [建立資料層](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)，如果您還沒有。 資料層是網站上 JavaScript 物件的架構，包含實施內的所有變數值。可讓您在實施中進行更深入的控制及更輕鬆的維護。
1. 使用 [DTM](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/other/dtm/dtm-implementation-overview.html) 若要在您的網站上實作資料收集的程式碼（如果您尚未進行）。 Dynamic Tag Management 提供單一資料層，可從多個來源推送資料。
1. 建立 [Adobe Analytics來源連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) 在Adobe Experience Platform中。 此來源連接器將在稱為 [體驗資料模型(XDM)系統](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/home.html).
1. 使用 [客戶歷程分析](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-overview/cja-getting-started.html) 以建立一或多個連線和資料檢視，以通知您的跨通道報告。

### 透過Launch

1. [建立資料層](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)，如果您還沒有。 資料層是網站上 JavaScript 物件的架構，包含實施內的所有變數值。可讓您在實施中進行更深入的控制及更輕鬆的維護。
1. 使用 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) 若要在您的網站上實作資料收集的程式碼（如果您尚未進行）。 Launch 為標籤管理解決方案，可讓您部署 Analytics 程式碼及滿足其他標籤需求。Launch提供與其他解決方案和產品的整合，讓您部署自訂程式碼。 您可以完成上述所有工作，而不需依賴組織中的任何開發團隊來更新網站上的程式碼。
1. 建立 [Adobe Analytics來源連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) 在Adobe Experience Platform中。 此來源連接器將在稱為 [體驗資料模型(XDM)系統](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. 使用 [客戶歷程分析](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 以建立一或多個連線和資料檢視，以通知您的跨通道報告。
