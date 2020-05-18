---
title: Customer Journey Analytics 快速入門
description: Customer Journey Analytics 快速入門。
translation-type: ht
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Customer Journey Analytics 快速入門

若要實施 Customer Journey Analytics，您必須依照此工作流程操作。某些初始工作需在 Adobe Experience Platform 中執行，有些則需在 Customer Journey Analytics 中執行。

| 任務 | 執行位置 | 詳細資料 |
|---|---|---|
| **步驟 1：將資料匯入 Adobe Experience Platform** | Adobe Experience Platform | 有數種方式可內嵌串流和批次使用案例的資料，包括 API 和用於資料上傳的圖形介面。Experience Platform 可從以下項目取得資料：<ul><li>S3 儲存服務</li><li>Azure Blob 儲存體</li><li>Kafka 串流</li><li>SFTP 傳輸</li><li>CSV 檔案上傳</li><li>JSON 檔案上傳</li></ul> |
| **步驟 2：準備您的資料結構** | Adobe Experience Platform | 使用 [Adobe Experience Data Model (XDM)](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/home.translate.html)，標準化客戶體驗資料並定義客戶體驗管理的結構。 |
| **步驟 3：根據結構建立資料集** | Adobe Experience Platform | Platform 中的資料由資料集組成，例如電子郵件資料集、CRM 資料集、POS 資料集、Adobe Analytics 資料集等。每個資料集都是由結構和資料批次組成。您可以[在 Experience Platform 中](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)建立資料集。<br>雖然可匯入 Customer Journey Analytics 的資料集結構具有彈性，但必須符合幾項基本規則。最好先確定您的資料符合這些要求，再將其上傳至 Platform。(請注意，結構包含量度和維度。)<br>與 Customer Journey Analytics 相容的資料類型有三種：<ul><li>**事件資料**：代表及時事件的資料 (例如網站造訪、互動、交易、POS 資料、調查資料、廣告曝光數資料等)。這是典型的點按資料流資料，包含客戶 ID 或 Cookie ID 以及時間戳記。您可以透過事件資料使用任何所需的 ID。</li><li>**查找資料**：此資料用於查找在事件或設定檔資料中找到的值或索引鍵。例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查找資料。</li><li>**設定檔資料**：套用至事件資料中訪客、使用者或客戶的資料。例如，您可上傳有關客戶的 CRM 資料。</li></ul> |
| **步驟 4：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | Customer Journey Analytics | 請參閱[建立連線](/help/connections/create-connection.md)。 |
| **步驟 5：建立資料檢視** | Customer Journey Analytics | 請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 6：在 Workspace 中報告跨管道資料** | Customer Journey Analytics | 請參閱[執行基本分析](/help/projects/perform-basic-analysis.md)和[執行進階分析](/help/projects/perform-adv-analysis.md)。 |

## 必要條件

Customer Journey Analytics 適用於以下客戶

* Adobe Analytics [Select、Prime 或 Ultimate](https://www.adobe.com/tw/analytics/compare-adobe-analytics-packages.html) 客戶，以及
* 已針對 [Adobe Experience Platform](https://www.adobe.com/tw/experience-platform.html) 佈建的客戶，以及
* 已購買 Customer Journey Analytics SKU 的客戶

## 準備您的資料結構

[使用結構編輯器建立架構](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 步驟 1：將資料匯入 Adobe Experience Platform

必須先將 Experience Platform 資料內嵌至 Platform 中，才能在 CJA 中運用這些資料。有幾種方法可以做到：

* 如果您希望內嵌現有的 Adobe Analytics 資料，請使用 Adobe Analytics Platform Connector。
* 若要內嵌其他資料，請使用下列格式：S3 儲存服務、Azure Blob 儲存體、Kafka 串流、SFTP 傳輸、CSV 檔案上傳、JSON 檔案上傳

### 步驟 1a：將現有的 Analytics 資料內嵌到 Adobe Experience Platform 中

使用現成可用的 Adobe Analytics Platform Connector，將傳統的 Adobe Analytics 資料內嵌到 Platform 中。您可以為每個報表套裝建立一個來源連線。請參閱 Adobe Experience Platform 文件中的[透過 Adobe Analytics 建立來源連線](https://docs.adobe.com/content/help/zh-Hant/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)。

建立連線後，系統會自動建立目標結構和資料集以包含傳入的資料。此外，還會進行資料回填，以及內嵌長達 13 個月的歷史資料。初始內嵌完成時，您可以繼續進行`Step 4`，建立此 Analytics 資料集與 Customer Journey Analytics 之間的連線。

### 步驟 1b：內嵌其他資料類型

[批次內嵌](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)可讓您將資料以批次檔案的形式內嵌到 Experience Platform 中。批次是多個資料單位，由一或多個要作為一個單位進行內嵌的檔案所組成。內嵌後，批次會提供中繼資料，說明成功內嵌的記錄數，以及任何失敗的記錄和相關的錯誤訊息。必須使用此方法來內嵌手動上傳的資料檔案，例如一般 .CSV 檔案 (對應至 XDM 結構) 和 Parquet dataframe。

[串流內嵌](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)可讓您即時從用戶端和伺服器端裝置傳送資料至 Experience Platform。

[其他來源連接器](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)可讓您內嵌來自外部來源的資料，同時使用 Platform 服務來建構、加標籤以及增強傳入的資料。您可以內嵌來自各種來源的資料，例如 Adobe 應用程式 (Adobe Analytics、Audience Manager、Experience Platform Launch、Target)、雲端儲存空間 (Azure Blob、Amazon S3、FTP/SFTP、Google Cloud Storage)、第三方軟體和您的 CRM (Microsoft Dynamics 365、Salesforce)。

## 步驟 2：準備您的資料結構

bnbnbnbn
