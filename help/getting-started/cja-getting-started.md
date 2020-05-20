---
title: Customer Journey Analytics 快速入門
description: Customer Journey Analytics 快速入門。
translation-type: tm+mt
source-git-commit: e30bbae59e11bbf93668ffe072508727f6efdd51
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 71%

---


# Customer Journey Analytics 快速入門

若要實施 Customer Journey Analytics，您必須依照此工作流程操作。某些初始工作需在 Adobe Experience Platform 中執行，有些則需在 Customer Journey Analytics 中執行。

## 必要條件

Customer Journey Analytics 適用於以下客戶

* Adobe Analytics [Select、Prime 或 Ultimate](https://www.adobe.com/tw/analytics/compare-adobe-analytics-packages.html) 客戶，以及
* 已針對 [Adobe Experience Platform](https://www.adobe.com/tw/experience-platform.html) 佈建的客戶，以及
* 已購買 Customer Journey Analytics SKU 的客戶

## 工作流程

| 任務 | 詳細資料 |
|---|---|---|
| **步驟 1：將資料匯入 Adobe Experience Platform** | 此步驟在Adobe Experience Platform中執行，涉及數個子步驟：<br>**步驟1a: 準備您的資料結構&#x200B;**: 使用[Adobe Experience Data Model(XDM)](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/home.translate.html)，標準化客戶體驗資料並定義[客戶體驗管理的架構](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)。<br>**步驟1b: 根據架構建立資料集**: Platform中的資料由資料集組成，例如電子郵件資料集、CRM資料集、POS資料集、Adobe Analytics資料集等。 每個資料集都是由結構和資料批次組成。您可以[在 Experience Platform 中](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)建立資料集。<br>**步驟1c: 將資料內嵌至Experience Platform **: 使用現成可用的Adobe Analytics Platform Connector，將傳統的Adobe Analytics資料匯入Platform。 您可以為每個報表套裝建立一個來源連線。請參閱 Adobe Experience Platform 文件中的[透過 Adobe Analytics 建立來源連線](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)。建立連線後，系統會自動建立目標結構和資料集以包含傳入的資料。此外，還會進行資料回填，以及內嵌長達 13 個月的歷史資料。初始內嵌完成時，您可以繼續進行`Step 2`，建立此 Analytics 資料集與 Customer Journey Analytics 之間的連線。<br>或者，您也可以透過「批次擷取」、「串流擷取」[或「其他來源」連接器，來](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)[擷取其他](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)資料類型[](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)。 |
| **步驟 2：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將Adobe Experience Platform的資料集整合至工作區。 為了報告Experience Platform資料集，您必須先在Experience Platform和Workspace中建立資料集之間的連線。<br>請參閱[建立連線](/help/connections/create-connection.md)。 |
| **步驟 3：建立資料檢視** | 資料檢視是資料的「篩選」檢視。 您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等項目使用不同設定。您可以為單一資料集建立多個資料檢視。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 4：在 Workspace 中報告跨管道資料** | 建立連線和資料檢視後，使用 Analysis Workspace 的強大功能與彈性來分析您所匯入的資料。<br>請參閱[執行基本分析](/help/projects/perform-basic-analysis.md)和[執行進階分析](/help/projects/perform-adv-analysis.md)。 |
