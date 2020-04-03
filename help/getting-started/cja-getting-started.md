---
title: 客戶歷程分析快速入門
description: 客戶歷程分析快速入門。
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# 客戶歷程分析快速入門

若要實作客戶歷程分析，您必須遵循此工作流程。 有些初始工作是在Adobe Experience Platform中執行，有些則在客戶歷程分析中執行。

| 任務 | 執行位置 | 詳細資料 |
|---|---|---|
| **步驟1:將您的資料匯入Adobe Experience Platform** | Adobe Experience Platform | 有數種方式可擷取串流和批次使用案例的資料，包括API和資料上傳的圖形介面。 Experience Platform可以從以下方面引入資料：<ul><li>S3儲存空間</li><li>Azure Blob儲存空間</li><li>卡夫卡溪</li><li>SFTP傳輸</li><li>CSV檔案上傳</li><li>JSON檔案上傳</li></ul> |
| **步驟2:準備您的資料結構** | Adobe Experience Platform | 使用 [Adobe Experience Data Model(XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) ，標準化客戶體驗資料並定義客戶體驗管理的架構。 |
| **步驟3:根據模式建立資料集** | Adobe Experience Platform | Platform中的資料由資料集組成，例如電子郵件資料集、CRM資料集、POS資料集、Adobe Analytics資料集等。 每個資料集都由模式和批資料組成。 您可以在Experience Platform中建 [立資料集](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>雖然可匯入客戶歷程分析的資料集架構是有彈性的，但它必須符合一些基本規則。 最好先確定您的資料符合這些要求，再將其上傳至平台。 （請注意，結構同時包含量度和維度。）<br>有三種資料類型與客戶歷程分析相容：<ul><li>**事件資料**:代表及時事件的資料（例如，網站瀏覽、互動、交易、POS資料、調查資料、廣告曝光資料等）。 這是典型的點按流資料，包含客戶ID或Cookie ID，以及時間戳記。 透過事件資料，我們允許您使用任何您想要的ID。</li><li>**查閱資料**:此資料用於查閱在「事件」或「描述檔」資料中找到的值或索引鍵。 例如，您可以上傳將事件資料中的數值ID對應至產品名稱的查閱資料。</li><li>**描述檔資料**:在「事件」資料中套用至訪客、使用者或客戶的資料。 例如，可讓您上傳有關客戶的CRM資料。</li></ul> |
| **步驟4：建立平台資料集和客戶歷程分析之間的連線** | 客戶歷程分析 | See [Create a connection](/help/connections/create-connection.md). |
| **步驟5:建立資料檢視** | 客戶歷程分析 | See [Create a data view](/help/data-views/create-dataview.md). |
| **步驟6:在工作區中報告跨通道資料** | 客戶歷程分析 | 請參 [閱執行基本分析](/help/projects/perform-basic-analysis.md)[和執行進階分析](/help/projects/perform-adv-analysis.md)。 |

## 必要條件

客戶歷程分析適用於

* Adobe Analytics [Select、Prime或Ultimate客戶](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) ，以及
* 已針對 [Adobe Experience Platform布建](https://www.adobe.com/experience-platform.html)，以及
* 已購買客戶歷程分析SKU

## 準備您的資料結構

[使用架構編輯器建立架構](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 步驟1:將您的資料匯入Adobe Experience Platform

在CJA中運用Experience Platform資料之前，您必須將該資料內嵌至Platform。 有幾種方法可以做到：

* 如果您想要匯入現有的Adobe Analytics資料，請使用Adobe Analytics平台連接器。
* 若要擷取其他資料，請使用下列格式：S3儲存、Azure Blob儲存、Kafka串流、SFTP傳輸、CSV檔案上傳、JSON檔案上傳

### 步驟1a:將您現有的Analytics資料匯入Adobe Experience Platform

使用現成可用的Adobe Analytics Platform Connector，將傳統的Adobe Analytics資料匯入Platform。 您可以為每個報表套裝建立一個來源連線。 請參 [閱Adobe Experience Platform檔案中的](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) 「建立與Adobe Analytics的來源連線」。

建立連線後，會自動建立目標模式和資料集以包含傳入的資料。 此外，還會進行資料回填，並且會收集長達13個月的歷史資料。 當初始擷取完成時，您可以繼續建立 `Step 4` 此Analytics資料集與客戶歷程分析之間的連線。

### 步驟1b:收錄其他資料類型

[批次擷取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) ，可讓您將資料以批次檔案的形式，收錄到Experience Platform。 批是由一個或多個要作為單個單位接收的檔案組成的資料單位。 收錄後，批次會提供中繼資料，說明成功收錄的記錄數，以及任何失敗的記錄和相關的錯誤訊息。 必須使用此方法來擷取手動上傳的資料檔案，例如平面。CSV檔案（映射至XDM結構）和Parce資料列。

[串流擷取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) ，可讓您即時從用戶端和伺服器端裝置傳送資料至Experience Platform。

[其他來源連接器](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) ，可讓您從外部來源擷取資料，同時讓您能夠使用平台服務來建構、標籤並增強傳入的資料。 您可以從多種來源收集資料，例如Adobe應用程式(Adobe Analytics、Audience Manager、Experience Platform Launch、Target)、雲端儲存空間（Azure Blob、Amazon S3、FTP/SFTP、Google雲端儲存空間）、協力廠商軟體和您的CRM(Microsoft Dynamics 365,Salesforce)。

## 步驟2:準備您的資料結構

bnbnbnb
