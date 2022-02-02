---
title: Customer Journey Analytics 快速入門
description: 了解實作 Customer Journey Analytics 所需的必要條件和工作流程。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 100%

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
|---|---|
| **步驟 1：將資料匯入 Adobe Experience Platform** | 這個在 Adobe Experience Platform 中執行的步驟涉及幾個子步驟：<ul><li>**步驟 1a：準備資料結構**：使用 [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) 將客戶體驗資料標準化，並為客戶體驗管理[定義結構](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)。</li><li>**步驟 1b：建立以結構為基礎的資料集**：Platform 中的資料是由資料集所構成，例如電子郵件資料集、CRM 資料集、POS 資料集、Adobe Analytics 資料集等等。每個資料集都是由結構和資料批次組成。您可以[在 Experience Platform 中](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)建立資料集。</li><li>**步驟 1c：將資料內嵌至 Experience Platform**：使用現成的 Adobe Analytics Platform Connector，將傳統 Adobe Analytics 資料匯入 Platform。您可以為每個報表套裝建立一個來源連線。請參閱 Adobe Experience Platform 文件中的[透過 Adobe Analytics 建立來源連線](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)。建立連線後，系統會自動建立目標結構和資料集以包含傳入的資料。此外，還會進行資料回填，以及內嵌長達 13 個月的歷史資料。完成初步內嵌作業後，您可以繼續進行`Step 2`，建立此 Analytics 資料集與 Customer Journey Analytics 之間的連線。或者，您也可以透過[批次內嵌](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)、[串流內嵌](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)或[其他 Source Connector](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) 嵌入其他資料類型。</li></ul> |
| **步驟 2：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對 Experience Platform 資料集製作報表，必須先為 Experience Platform 和工作區的資料集建立連線。<br>請參閱[建立連線](/help/connections/create-connection.md)。 |
| **步驟 3：建立資料檢視** | 資料檢視是「經過篩選」的資料查看畫面。您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等項目使用不同設定。您可以為單一資料集建立多個資料檢視。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 4：在工作區中製作跨管道資料報表** | 建立連線和資料檢視後，運用 Analysis Workspace 的強大功能與彈性，分析您所匯入的資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |
