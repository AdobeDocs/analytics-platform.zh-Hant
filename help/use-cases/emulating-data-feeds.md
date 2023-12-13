---
title: 模擬資料摘要功能
description: 瞭解如何以Experience Platform中的資料模擬Adobe Analytics資料摘要。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: b41adb3f3fa4abbfa7be491e5a1fbf81e1623598
workflow-type: tm+mt
source-wordcount: '2556'
ht-degree: 5%

---

# 模擬資料摘要功能

Adobe Analytics資料摘要是從Adobe Analytics中取得原始資料的有力方式。 此使用案例說明如何從Experience Platform取得類似的原始資料型別，以便您可以在Adobe以外自行決定的其他平台和工具中使用資料。

## 簡介

模擬Adobe Analytics資料摘要的過程包括：

* 定義 **排定的查詢** ，為您的資料摘要產生資料作為輸出資料集 ![輸出資料集](assets/output-dataset.svg)，使用 **查詢服務**.
* 定義 **排程的資料集匯出** ，會使用將輸出資料集匯出至雲端儲存空間目的地 **資料集匯出**.

![資料摘要](assets/data-feed.svg)


## 先決條件

使用此使用案例所述的功能之前，請確定您符合下列所有需求：

* 將資料收集至Experience Platform資料湖的有效實作。
* 存取資料Distiller附加元件，以確保您有權執行批次查詢。 另請參閱 [查詢服務封裝](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) 以取得詳細資訊。
* 存取匯出資料集功能，此功能在您購買Real-Time CDP Prime或Ultimate套件、Adobe Journey Optimizer或Customer Journey Analytics時可用。 另請參閱 [將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hant) 以取得詳細資訊。
* 一或多個目的地(例如：Amazon S3、Google Cloud Storage)已設定為可在其中匯出資料摘要的原始資料。


## 查詢服務

Experience Platform查詢服務可讓您查詢及聯結Experience Platform資料湖中的任何資料集，就像它是資料庫表格一樣。 然後，您可以將結果擷取為新資料集，以供進一步用於報告或匯出。

您使用查詢服務 [使用者介面](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en)， a [使用者端透過PostgresQL通訊協定連線](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en)，或 [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 以建立及排程收集資料摘要資料的查詢。

### 建立查詢

您可以使用標準ANSI SQL for SELECT敘述句和其他有限命令的所有功能，來建立和執行產生資料摘要資料的查詢。 另請參閱 [SQL語法](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) 以取得詳細資訊。 除了此SQL語法以外，Adobe還支援：

* 預先建立 [Adobe定義函式(ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) 可協助您對儲存在Experience Platform資料湖中的事件資料執行常見的業務相關工作，包括 [工作階段化](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=zh-Hant) 和 [歸因](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hant)，
* 數個內建 [Spark SQL函式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en)，
* [中繼資料PostgreSQL命令](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en)，
* [準備的陳述式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### 身分

在Experience Platform中，有多種身分可供使用。 建立查詢時，請確定您正在正確查詢身分。

您通常會在個別的欄位群組中找到身分。 在實作ECID (`ecid`)可定義為具有的欄位群組的一部分 `core` 物件，它本身就是物件的一部分， `identification` 物件。 (例如： `_sampleorg.identification.core.ecid`)。 ECID在結構中的組織方式可能有所不同。

或者，您可以使用 `identityMap` 以查詢身分。 此物件的型別 `Map` 並使用 [巢狀資料結構](#nested-data-structure).


#### 資料摘要欄

您可以在查詢中使用的XDM欄位取決於資料集所依據的結構描述定義。 請確定您瞭解資料集所根據的結構描述。

若要簡化資料摘要欄和XDM欄位之間的對應，您應考慮包含 [Adobe Analytics ExperienceEvent范](https://github.com/adobe/xdm/blob/master/extensions/adobe/experience/analytics/experienceevent-all.schema.json) 「體驗事件」結構描述中的欄位群組。 另請參閱 [資料模型化的最佳實務](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en) 更具體地說 [Adobe應用程式結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en#adobe-application-schema-field-groups).

例如，如果您想使用 *頁面名稱* 做為資料摘要的一部分：

* 在Adobe Analytics資料摘要的UI中，您可以選取 **[!UICONTROL pagename]** 作為欄，以新增至您的資料摘要定義。
* 在查詢服務中，您包括 `web.webPageDetails.name` 從 `sample_event_dataset_for_website_global_v1_1` 資料集(根據 **網站的範例事件結構描述(Gobal v1.1)** 體驗事件結構描述)。 請參閱 [Web詳細資料結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) 以取得詳細資訊。

若要瞭解體驗事件資料集和基礎結構描述中，前Adobe Analytics資料摘要欄和XDM欄位之間的對應，請參閱 [Analytics欄位對映](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant) 和 [Adobe Analytics ExperienceEvent完整擴充功能結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以取得詳細資訊。

此外， [由Experience PlatformWeb SDK自動收集的資訊（立即可用）](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) 可能與識別查詢的欄相關。

#### 點選層級資料和識別

根據實作，傳統上在Adobe Analytics中收集的點選層級資料現在會儲存為Experience Platform中的時間戳記事件資料。 下表摘錄自 [分析欄位對應](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en#generated-mapping-fields) 和顯示如何將點選層級特定的Adobe Analytics資料摘要欄與查詢中的對應XDM欄位的範例。 此表格也顯示如何使用XDM欄位識別點選、造訪和訪客的範例。

| 資料摘要欄 | XDM欄位 | 類型 | 說明 |
|---|---|---|---|
| hitid_high + hitid_low | _id | 字串 | 用於識別點選的唯一識別碼。 |
| hitid_low | _id | 字串 | 搭配hitid_high使用以專門識別點選。 |
| hitid_high | _id | 字串 | 搭配hitid_high使用以專門識別點選。 |
| hit_time_gmt | receivedTimestamp | 字串 | 點選的時間戳記，根據Unix時間。 |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | 字串 | 訪客初次點擊的時間戳記，格式為 Unix 時間。 |
| cust_hit_time_gmt | timestamp | 字串 | 這僅用於啟用時間戳記的資料集。 這是根據Unix時間而隨其傳送的時間戳記。 |
| visid_high + visid_low | identityMap | 物件 | 造訪的唯一識別碼。 |
| visid_high + visid_low | endUserIDs。_experience.aaid.id | 字串 | 造訪的唯一識別碼。 |
| visid_high | endUserIDs。_experience.aaid.primary | 布林值 | 搭配visid_low使用以專門識別造訪。 |
| visid_high | endUserIDs。_experience.aaid.namespace.code | 字串 | 搭配visid_low使用以專門識別造訪。 |
| visid_low | identityMap | 物件 | 搭配visid_high使用以專門識別造訪。 |
| cust_visid | identityMap | 物件 | 客戶訪客ID |
| cust_visid | endUserIDs。_experience.aacustomid.id | 物件 | 客戶訪客ID。 |
| cust_visid | endUserIDs。_experience.aacustomid.primary | 布林值 | 客戶訪客ID名稱空間程式碼。 |
| cust_visid | endUserIDs。_experience.aacustomid.namespace.code | 字串 | 搭配visid_low使用以專門識別客戶訪客id。 |
| 地理\_* | placeContext.geo.* | 字串，數字 | 地理位置資料，例如國家、地區、城市等 |
| visit_page_num | _experience.analytics.session.depth | 數字 | 用於點選深度維度的變數。 此值會因使用者產生的每次點選而增加1，並在每次造訪後重設。 |
| event_list | commerce.purchases， commerce.productViews， commerce.productListOpens， commerce.checkouts， commerce.productListAdds， commerce.productListRemovals， commerce.productListViews， \_experience.analytics.event101to200。*， ...， \_experience.analytics.event901_1000。\* | 字串 | 標準商務和點選時觸發的自訂事件。 |
| page_event | web.webInteraction.type | 字串 | 影像要求中傳送的點選型別（標準點選、下載連結、退出連結或自訂連結已點按）。 |
| page_event | web.webInteraction.linkClicks.value | 數字 | 影像要求中傳送的點選型別（標準點選、下載連結、退出連結或自訂連結已點按）。 |
| page_event_var_1 | web.webInteraction.URL | 字串 | 僅用於連結追蹤影像要求中的變數。 此變數包含下載連結、退出連結或自訂連結點選的URL。 |
| page_event_var_2 | web.webInteraction.name | 字串 | 僅用於連結追蹤影像要求中的變數。 這會列出連結的自訂名稱（如果已指定）。 |
| first_hit_ref_type | _experience.analytics.endUser.firstWeb.webReferrer.type | 字串 | 數值ID，代表訪客第一個反向連結的反向連結型別。 |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | 整數 | 訪客初次點擊的時間戳記，格式為 Unix 時間。 |
| paid_search | search.isPaid | 布林值 | 如果點選符合付費搜尋偵測，則會設定此旗標。 |
| ref_type | web.webReferrertype | 字串 | 此數值 ID 表示點擊的反向連結類型。 |

#### 張貼欄

Adobe Analytics資料摘要會使用附有欄的概念 `post_` 前置詞，處理之後包含資料的欄。 如需詳細資訊，請參閱[資料摘要常見問題](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=en#post)。

透過Experience Platform邊緣網路（Web SDK、Mobile SDK、伺服器API）在資料集中收集的資料不含 `post_` 欄位，說明原因 `post_` 前置詞和 *非* `post_` 在Analytics欄位中將資料摘要欄加上前置詞後，對應至相同的XDM欄位。 例如，兩者 `page_url` 和 `post_page_url` 資料摘要欄會對應至相同的 `web.webPageDetails.URL` XDM欄位。

另請參閱 [比較Adobe Analytics和Customer Journey Analytics的資料處理](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=zh-Hant) 以取得資料處理差異的概觀。

此 `post_` 在Experience Platform資料湖中收集資料時，為其資料欄型別加上前置詞，則不需要進階轉換，才能成功用於資料摘要使用案例。 在查詢中執行這些進階轉換涉及使用 [Adobe定義的函式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) 用於工作階段化、歸因和重複資料刪除。 另請參閱 [範例](#examples) 這些函式的使用方式。

#### 查詢

若要從其他資料集中查詢資料，請使用標準SQL功能(`WHERE` 子句， `INNER JOIN`， `OUTER JOIN`和其他)。

#### 計算

若要在欄位（欄）上執行計算，請使用標準SQL函式(例如 `COUNT(*)` 或 [數學和統計運運算元與函式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) Spark SQL的一部分。 此外， [視窗函式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en#window-functions) 提供更新彙總的支援，並傳回有序子集中每一列的單一專案。 另請參閱 [範例](#examples) 這些函式的使用方式。

#### 巢狀資料結構

資料集所根據的結構描述通常包含複雜的資料型別，包括巢狀資料結構。 先前已提及 `identityMap` 是巢狀資料結構的範例。 如需範例，請參閱下文 `identityMap` 資料。

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

您可以使用 [`explode()` 或其他陣列功能](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) 從Spark SQL取得巢狀資料結構內的資料，例如：

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

或者，您可以使用點標籤法來參照個別元素。 例如：

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

請參閱「[在 Query Service 中使用巢狀資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en)」以了解更多資訊。


#### 範例

例如，查詢若使用Experience Platform資料湖中資料集的資料，點選Adobe定義函式和/或Spark SQL的其他功能，而這會提供類似結果給對等的Adobe Analytics資料摘要，請參閱

* [捨棄的瀏覽](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en)，
* [歸因分析](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en)，
* [機器人篩選](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)，
* 和查詢服務指南中的其他範例使用案例。


### 排程查詢

您可以排程查詢，以確保查詢已執行，而且結果會以您偏好的間隔產生。

#### 使用查詢編輯器

您可以使用查詢編輯器排程查詢。 排程查詢時，您可以定義輸出資料集。 另請參閱 [查詢排程](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) 以取得詳細資訊。


#### 使用查詢服務API

或者，您可以使用RESTful API來定義查詢和排程查詢。 另請參閱 [查詢服務API指南](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 以取得詳細資訊。
請確定您將輸出資料集定義為選用的一部分 `ctasParameters` 建立查詢時的屬性([建立查詢](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery))或建立查詢的排程時([建立排定的查詢](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule))。



## 資料集匯出

一旦您建立並排程查詢，且已驗證輸出資料集中的結果符合您的要求，您就可以將原始資料集匯出至雲端儲存空間目的地。 此匯出位於「Experience Platform目的地」術語中，稱為「資料集匯出目的地」。 另請參閱 [將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hant) 以取得概覽。

支援下列雲端儲存空間目的地：

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [資料登陸區域](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google雲端儲存空間](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### EXPERIENCE PLATFORMUI

您可以透過Experience Platform UI匯出及排程匯出輸出資料集。 本節將說明相關步驟。

#### 選取目的地

當您決定要匯出輸出資料集的雲端儲存空間目的地時， [選取目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). 如果您尚未設定偏好雲端儲存空間的目的地，您必須 [建立新的目的地連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

在設定目的地時，您可以定義檔案型別（JSON或Parquet）、產生的檔案是否應壓縮，以及資訊清單檔案是否應包含在內。


#### 選取資料集

當您選取目的地時，在下一個 **[!UICONTROL 選取資料集]** 您必須從資料集清單中選取輸出資料集的步驟。 如果您建立了多個排程的查詢，且希望輸出資料集傳送至相同的雲端儲存空間目的地，則可選取對應的輸出資料集。 另請參閱 [選取您的資料集](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) 以取得詳細資訊。

#### 排程資料集匯出

最後，您想要將資料集匯出排程為 **[!UICONTROL 正在排程]** 步驟。 在該步驟中，您可以定義排程，以及輸出資料集匯出是否應為增量式的。 另請參閱 [排程資料集匯出](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) 以取得詳細資訊。


#### 最後步驟

[檢閱](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) 您的選取範圍以及正確後，開始將輸出資料集匯出至雲端儲存空間目的地。

您必須 [驗證](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) 資料匯出成功。 匯出資料集時，Experience Platform會建立一或多個 `.json` 或 `.parquet` 存放位置中定義的檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立資料夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。

### 流程服務API

或者，您可以使用API匯出和排程匯出輸出資料集。 相關步驟的記錄於 [使用流量服務API匯出資料集](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### 開始使用

確定您擁有 [必要許可權](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) 若要匯出資料集，以及您要將輸出資料集傳送到的目的地支援匯出資料集。 然後，您必須 [收集必要和選用標題的值](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) 您可在API呼叫中使用，也可以 [識別目的地的連線規格和流程規格ID](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) 您打算將資料集匯出至。

#### 擷取合格的資料集

您可以 [擷取合格資料集的清單](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) 匯出，並使用「 」確認輸出資料集是否屬於該清單 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API。


#### 建立來源連線

接下來，您必須 [建立來源連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) 針對您要匯出至雲端儲存空間目的地的輸出資料集（使用其唯一ID）。 您使用 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 驗證到目的地（建立基礎連線）

您現在必須 [建立基礎連線](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) 以使用正確驗證並安全地儲存認證至您的雲端儲存空間目的地 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API。


#### 提供匯出引數

接下來，您必須 [建立其他目標連線，以儲存匯出引數](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) 對於您的輸出資料集，再次使用 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API。 這些匯出引數包括位置、檔案格式、壓縮等等。

#### 設定資料流

最後，您 [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) 以確保您的輸出資料集已使用，匯出至雲端儲存空間目的地 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API。 在此步驟中，您可以使用來定義匯出排程 `scheduleParams` 引數。

#### 驗證資料流

至 [檢查資料流的成功執行](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs)，使用 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，將資料流ID指定為查詢引數。 此資料流ID是您設定資料流時傳回的識別碼。

[驗證](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) 資料匯出成功。 匯出資料集時，Experience Platform會建立一或多個 `.json` 或 `.parquet` 存放位置中定義的檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立資料夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。

## 結論

簡而言之，模擬Adobe Analytics資料摘要功能隱含著使用查詢服務設定排程查詢，以及在排程的資料集匯出中使用這些查詢的結果。

>[!IMPORTANT]
>
>此使用案例涉及兩個排程器。 為確保模擬資料摘要功能可正常運作，請確定在查詢服務和資料匯出中設定的排程不會干預。

