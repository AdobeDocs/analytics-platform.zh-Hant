---
title: Experience Platform查詢服務(資料Distiller)和匯出資料集
description: 說明如何使用查詢服務(資料Distiller)和資料集匯出功能來匯出資料。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 3568aad27001b322da77f5d1fb762db5ba6d433d
workflow-type: tm+mt
source-wordcount: '2642'
ht-degree: 3%

---

# 查詢服務(資料Distiller)和匯出資料集

本文概述如何使用Experience Platform查詢服務(資料Distiller)和資料集匯出的組合，來實作下列[個資料匯出使用案例](overview.md)：

- 資料驗證
- Data Lake，BI工具Data Warehouse
- 人工智慧和機器學習的整備。


Adobe Analytics可使用其[資料摘要](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview)功能來實作這些使用案例。 資料摘要是從 Adobe Analytics 中取得原始資料的有力方式。本文會說明如何從Experience Platform中取得類似的原始資料，以便您實施上述使用案例。 在適用情況下，本文所述的功能會與Adobe Analytics資料摘要進行比較，以釐清資料與程式的差異。

## 簡介

使用查詢服務(Data Distiller)匯出資料時，資料集匯出包含以下專案：

- 正在定義&#x200B;**排程的查詢**，該查詢會使用&#x200B;**查詢服務**，為您的資料摘要產生資料，作為輸出資料集![輸出資料集](../assets/output-dataset.svg)。
- 定義使用&#x200B;**資料集匯出**&#x200B;將輸出資料集匯出至雲端儲存空間目的地的&#x200B;**排程資料集匯出**。

![資料摘要](../assets/queryservice-export-datasets.svg)


## 先決條件

使用此使用案例所述的功能之前，請確定您符合下列所有需求：

- 將資料收集至Experience Platform資料湖的有效實作。
- 存取資料Distiller附加元件，以確保您有權執行批次查詢。 如需詳細資訊，請參閱[查詢服務封裝](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging)。
- 存取匯出資料集功能，此功能在您購買Real-Time CDP Prime或Ultimate套件、Adobe Journey Optimizer或Customer Journey Analytics時可用。 如需詳細資訊，請參閱[將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)。
- 一或多個已設定目的地(例如：Amazon S3、Google Cloud Storage)可匯出資料摘要的原始資料。


## 查詢服務

Experience Platform查詢服務可讓您查詢及聯結Experience Platform資料湖中的任何資料集，就像它是資料庫表格一樣。 然後，您可以將結果擷取為新資料集，以供進一步用於報告或匯出。

您可以使用Query Service [使用者介面](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview)、透過PostgresQL通訊協定[&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)連線的使用者端或[RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)，建立並排程收集資料摘要資料的查詢。

### 建立查詢

您可以使用標準ANSI SQL for SELECT敘述句和其他有限命令的所有功能，來建立和執行產生資料摘要資料的查詢。 如需詳細資訊，請參閱[SQL語法](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax)。 除了此SQL語法以外，Adobe還支援：

- 預先建立的[Adobe定義函式(ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)，可協助對儲存在Experience Platform資料湖中的事件資料執行一般商業相關工作，包括[Sessionization](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing)和[Attribution](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview)的函式，
- 數個內建[Spark SQL函式](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions)，
- [中繼資料PostgreSQL命令](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata)，
- [準備的陳述式](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements)。

#### 資料摘要欄

您可以在查詢中使用的XDM欄位取決於資料集所依據的結構描述定義。 請確定您瞭解資料集所根據的結構描述。 請參閱[資料集使用者介面指南](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide)以取得詳細資訊。

若要協助您定義資料摘要欄位與XDM欄位之間的對應，請參閱[分析欄位對應](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。 另請參閱[結構描述UI總覽](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields)，以取得有關如何管理XDM資源（包括結構描述、類別、欄位群組和資料型別）的詳細資訊。

例如，如果您想使用&#x200B;*頁面名稱*&#x200B;作為資料摘要的一部分：

- 在Adobe Analytics資料摘要的UI中，您可以選取&#x200B;**[!UICONTROL pagename]**&#x200B;作為要新增至資料摘要定義的欄。
- 在查詢服務中，您在查詢中包含來自`sample_event_dataset_for_website_global_v1_1`資料集的`web.webPageDetails.name` (根據網站的&#x200B;**範例事件結構描述（全域v1.1）**&#x200B;體驗事件結構描述)。 如需詳細資訊，請參閱[網頁詳細資料結構描述欄位群組](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details)。


#### 身分

在Experience Platform中，有多種身分可供使用。 建立查詢時，請確定您正在正確查詢身分。


您通常會在個別的欄位群組中找到身分。 在實作中，ECID (`ecid`)可以定義為具有`core`物件的欄位群組的一部分，其本身是`identification`物件的一部分（例如： `_sampleorg.identification.core.ecid`）。 ECID在結構中的組織方式可能有所不同。

或者，您可以使用`identityMap`來查詢身分。 `identityMap`的型別為`Map`，且使用[巢狀資料結構](#nested-data-structure)。

請參閱[在UI中定義身分欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)，以取得如何在Experience Platform中定義身分欄位的詳細資訊。

請參考Analytics資料中的[主要識別碼](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data)，瞭解使用Analytics來源聯結器時，Adobe Analytics身分如何對應到Experience Platform身分識別。 此對應可作為設定身分識別的指引，即使未使用Analytics來源聯結器亦然。


#### 點選層級資料和識別

根據實作，傳統上在Adobe Analytics中收集的點選層級資料現在會儲存為Experience Platform中的時間戳記事件資料。 下表擷取自[Analytics欄位對應](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields)，並示範如何將點選層級特定的Adobe Analytics資料摘要欄與查詢中的對應XDM欄位進行對應。 此表格也顯示如何使用XDM欄位識別點選、造訪和訪客的範例。

| 資料摘要欄 | XDM欄位 | 類型 | 說明 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | 字串 | 用於識別點選的唯一識別碼。 |
| `hitid_low` | `_id` | 字串 | 與`hitid_high`搭配使用以唯一識別點選。 |
| `hitid_high` | `_id` | 字串 | 與`hitid_high`搭配使用以唯一識別點選。 |
| `hit_time_gmt` | `receivedTimestamp` | 字串 | 點選的時間戳記，根據UNIX®時間。 |
| `cust_hit_time_gmt` | `timestamp` | 字串 | 此時間戳記只會用於啟用時間戳記的資料集。 根據UNIX®時間，此時間戳記會隨點選傳送。 |
| `visid_high` + `visid_low` | `identityMap` | 物件 | 造訪的唯一識別碼。 |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | 字串 | 造訪的唯一識別碼。 |
| `visid_high` | `endUserIDs._experience.aaid.primary` | 布林值 | 與`visid_low`搭配使用以唯一識別造訪。 |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | 字串 | 與`visid_low`搭配使用以唯一識別造訪。 |
| `visid_low` | `identityMap` | 物件 | 與`visid_high`搭配使用以唯一識別造訪。 |
| `cust_visid` | `identityMap` | 物件 | 客戶訪客ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | 物件 | 客戶訪客ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | 布林值 | 客戶訪客ID名稱空間程式碼。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | 字串 | 與`visid_low`搭配使用以唯一識別客戶訪客ID。 |
| `geo\_*` | `placeContext.geo.* ` | 字串，數字 | 地理位置資料，例如國家、地區、城市等 |
| `event_list` | `commerce.purchases`、`commerce.productViews`、`commerce.productListOpens`、`commerce.checkouts`、`commerce.productListAdds`、`commerce.productListRemovals`、`commerce.productListViews`、`_experience.analytics.event101to200.*`、...、`_experience.analytics.event901_1000.*` | 字串 | 標準商務和點選時觸發的自訂事件。 |
| `page_event` | `web.webInteraction.type` | 字串 | 影像要求中傳送的點選型別（標準點選、下載連結、退出連結或自訂連結已點按）。 |
| `page_event` | `web.webInteraction.linkClicks.value` | 數字 | 影像要求中傳送的點選型別（標準點選、下載連結、退出連結或自訂連結已點按）。 |
| `page_event_var_1` | `web.webInteraction.URL` | 字串 | 僅用於連結追蹤影像要求中的變數。 此變數包含下載連結、退出連結或自訂連結點選的URL。 |
| `page_event_var_2` | `web.webInteraction.name` | 字串 | 僅用於連結追蹤影像要求中的變數。 這會列出連結的自訂名稱（如果已指定）。 |
| `paid_search` | `search.isPaid` | 布林值 | 如果點選符合付費搜尋偵測，則會設定此旗標。 |
| `ref_type` | `web.webReferrertype` | 字串 | 此數值 ID 表示點擊的反向連結類型。 |

#### 張貼欄

Adobe Analytics資料摘要使用具有`post_`首碼的欄的概念，這些欄是包含處理後的資料之欄。 如需詳細資訊，請參閱[資料摘要常見問題](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post)。

透過Experience PlatformEdge Network（Web SDK、Mobile SDK、伺服器API）在資料集中收集的資料沒有`post_`欄位的概念。 因此，`post_`首碼和&#x200B;*非*-`post_`首碼資料摘要資料行對應到相同的XDM欄位。 例如，`page_url`和`post_page_url`資料摘要欄位都對應到相同的`web.webPageDetails.URL` XDM欄位。

請參閱[比較Adobe Analytics與Customer Journey Analytics的資料處理](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons)，以取得資料處理差異的概觀。

但在Experience Platform資料湖中收集資料時，`post_`首碼資料行型別的資料確實需要進階轉換，才能成功用於資料摘要使用案例。 在您的查詢中執行這些進階轉換，涉及使用[Adobe定義的函式](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)進行工作階段化、歸因及重複資料刪除。 請參閱[範例](#examples)以瞭解如何使用這些函式。

#### 查詢

若要從其他資料集中查詢資料，請使用標準SQL功能（`WHERE`子句、`INNER JOIN`、`OUTER JOIN`及其他）。

#### 計算

若要在欄位（欄）上執行計算，請使用標準SQL函式（例如`COUNT(*)`），或Spark SQL的[數學和統計運運算元和函式](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math)部分。 此外，[視窗函式](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions)支援更新彙總，並為排序子集中的每一列傳回單一專案。 請參閱[範例](#examples)以瞭解如何使用這些函式。

#### 巢狀資料結構

資料集所根據的結構描述通常包含複雜的資料型別，包括巢狀資料結構。 先前提到的`identityMap`是巢狀資料結構的範例。 請參閱下方的`identityMap`資料範例。

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

您可以使用Spark SQL中的[`explode()`或其他陣列函式](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays)來取得巢狀資料結構內的資料，例如：

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

或者，您可以使用點標籤法來參照個別元素。 例如：

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

請參閱「[在 Query Service 中使用巢狀資料結構](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures)」以了解更多資訊。


#### 範例

對於查詢：

- 使用Experience Platform資料湖中資料集的資料，
- 正在點選Adobe定義函式和/或Spark SQL的額外功能，以及
- 會將類似的結果提供給同等的Adobe Analytics資料摘要，

請參閱：

- [放棄瀏覽](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [歸因分析](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [機器人篩選](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- 和查詢服務指南[&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview)中其他支援的使用案例。

以下是跨工作階段正確套用歸因的範例，說明如何

- 使用過去90天作為回顧，
- 套用工作階段化和/或歸因之類的視窗函式，以及
- 根據`ingest_time`限制輸出。

+++
詳細資料

  若要這麼做，您必須……

   - 使用處理狀態表`checkpoint_log`來追蹤目前與上次擷取時間。 如需詳細資訊，請參閱[本指南](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/incremental-load)。
   - 停用卸除系統資料行，以便使用`_acp_system_metadata.ingestTime`。
   - 使用最內部的`SELECT`來抓取您要使用的欄位，並將事件限制在您的回溯期間，以進行工作階段化和/或歸因計算。 例如90天。
   - 使用下一個層級`SELECT`來套用工作階段化和/或歸因視窗函式及其他計算。
   - 在輸出表格中使用`INSERT INTO`，將回顧限制在自上次處理時間後到達的事件。 若要這麼做，請篩選`_acp_system_metadata.ingestTime `與上次儲存於處理狀態表格中的時間。

  **工作階段化視窗功能範例**

  ```sql
  $$ BEGIN
     -- Disable dropping system columns
     set drop_system_columns=false; 
  
     -- Initialize variables
     SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
     -- Get the last processed batch ingestion time
     SET @from_batch_ingestion_time = SELECT coalesce(last_batch_ingestion_time, 'HEAD') 
        FROM checkpoint_log a 
        JOIN (
              SELECT MAX(process_timestamp) AS process_timestamp 
              FROM checkpoint_log
              WHERE process_name = 'data_feed' 
              AND process_status = 'SUCCESSFUL'
        ) b
        ON a.process_timestamp = b.process_timestamp;
  
     -- Get the last batch ingestion time
     SET @to_batch_ingestion_time = SELECT MAX(_acp_system_metadata.ingestTime) 
        FROM events_dataset;
  
     -- Sessionize the data and insert into data_feed.
     INSERT INTO data_feed
     SELECT *
     FROM (
        SELECT
              userIdentity,
              timestamp,
              SESS_TIMEOUT(timestamp, 60 * 30) OVER (
                 PARTITION BY userIdentity
                 ORDER BY timestamp
                 ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
              ) AS session_data,
              page_name,
              ingest_time
        FROM (
              SELECT
                 userIdentity,
                 timestamp,
                 web.webPageDetails.name AS page_name,
                 _acp_system_metadata.ingestTime AS ingest_time
              FROM events_dataset
              WHERE timestamp >= current_date - 90
        ) AS a
        ORDER BY userIdentity, timestamp ASC
     ) AS b
     WHERE b.ingest_time >= @from_batch_ingestion_time;
  
     -- Update the checkpoint_log table
     INSERT INTO checkpoint_log
     SELECT
        'data_feed' process_name,
        'SUCCESSFUL' process_status,
        cast(@to_batch_ingestion_time AS string) last_batch_ingestion_time,
        cast(@last_updated_timestamp AS TIMESTAMP) process_timestamp
  END
  $$;
  ```

  **歸因視窗功能範例**

  ```sql
  $$ BEGIN
   SET drop_system_columns=false;
  
  -- Initialize variables
   SET @last_updated_timestamp = SELECT CURRENT_TIMESTAMP;
  
  -- Get the last processed batch ingestion time 1718755872325
   SET @from_batch_ingestion_time =
       SELECT coalesce(last_snapshot_id, 'HEAD')
       FROM checkpoint_log a
       JOIN (
           SELECT MAX(process_timestamp) AS process_timestamp
           FROM checkpoint_log
           WHERE process_name = 'data_feed'
           AND process_status = 'SUCCESSFUL'
       ) b
       ON a.process_timestamp = b.process_timestamp;
  
   -- Get the last batch ingestion time 1718758687865
   SET @to_batch_ingestion_time =
       SELECT MAX(_acp_system_metadata.ingestTime)
       FROM demo_data_trey_mcintyre_midvalues;
  
   -- Sessionize the data and insert into new_sessionized_data
   INSERT INTO new_sessionized_data
   SELECT *
   FROM (
       SELECT
           _id,
           timestamp,
           struct(User_Identity,
           cast(SESS_TIMEOUT(timestamp, 60 * 30) OVER (
               PARTITION BY User_Identity
               ORDER BY timestamp
               ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
           ) as string) AS SessionData,
           to_timestamp(from_unixtime(ingest_time/1000, 'yyyy-MM-dd HH:mm:ss')) AS IngestTime,      
           PageName,
           first_url,
           first_channel_type
             ) as _demosystem5
       FROM (
           SELECT
               _id,
               ENDUSERIDS._EXPERIENCE.MCID.ID as User_Identity,
               timestamp,
               web.webPageDetails.name AS PageName,
              attribution_first_touch(timestamp, '', web.webReferrer.url) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_url,
              attribution_first_touch(timestamp, '',channel.typeAtSource) OVER (PARTITION BY ENDUSERIDS._EXPERIENCE.MCID.ID ORDER BY timestamp ASC ROWS BETWEEN UNBOUNDED PRECEDING AND UNBOUNDED FOLLOWING).value AS first_channel_type,
               _acp_system_metadata.ingestTime AS ingest_time
           FROM demo_data_trey_mcintyre_midvalues
           WHERE timestamp >= current_date - 90
       )
       ORDER BY User_Identity, timestamp ASC    
   )
   WHERE _demosystem5.IngestTime >= to_timestamp(from_unixtime(@from_batch_ingestion_time/1000, 'yyyy-MM-dd HH:mm:ss'));
  
  -- Update the checkpoint_log table
  INSERT INTO checkpoint_log
  SELECT
     'data_feed' as process_name,
     'SUCCESSFUL' as process_status,
     cast(@to_batch_ingestion_time AS string) as last_snapshot_id,
     cast(@last_updated_timestamp AS timestamp) as process_timestamp;
  
  END
  $$;
  ```

+++


### 排程查詢

您可以排程查詢，以確保查詢已執行，而且結果會以您偏好的間隔產生。

#### 使用查詢編輯器

您可以使用查詢編輯器排程查詢。 排程查詢時，您可以定義輸出資料集。 如需詳細資訊，請參閱[查詢排程](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules)。


#### 使用查詢服務API

或者，您可以使用RESTful API來定義查詢和排程查詢。 如需詳細資訊，請參閱[查詢服務API指南](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)。
建立查詢（[建立查詢](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)）或建立查詢排程（[建立排程查詢](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)）時，請確定將輸出資料集定義為選用的`ctasParameters`屬性的一部分。



## 匯出資料集

一旦您建立並排程查詢，且驗證結果後，您就可以將原始資料集匯出至雲端儲存空間目的地。 此匯出位於「Experience Platform目的地」術語中，稱為「資料集匯出目的地」。 請參閱[將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)以取得概觀。

支援下列雲端儲存空間目的地：

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [資料登陸區域](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google雲端儲存空間](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### EXPERIENCE PLATFORMUI

您可以透過Experience Platform UI匯出及排程匯出輸出資料集。 本節將說明相關步驟。

#### 選取目的地

當您決定要將輸出資料集匯出的雲端儲存空間目的地時，[請選取目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination)。 當您尚未設定慣用雲端儲存空間的目的地時，您必須[建立新的目的地連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination)。

在設定目的地時，您可以

- 定義檔案型別（JSON或Parquet），
- 產生的檔案是否應該壓縮，以及
- 是否應該包含資訊清單檔案。


#### 選取資料集

當您選取目的地時，在下一個&#x200B;**[!UICONTROL 選取資料集]**&#x200B;步驟中，您必須從資料集清單中選取您的輸出資料集。 如果您建立了多個排程的查詢，且希望輸出資料集傳送至相同的雲端儲存空間目的地，則可選取對應的輸出資料集。 如需詳細資訊，請參閱[選取您的資料集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets)。

#### 排程資料集匯出

最後，您想要排程資料集匯出，作為&#x200B;**[!UICONTROL 排程]**&#x200B;步驟的一部分。 在該步驟中，您可以定義排程，以及輸出資料集匯出是否應為增量式的。 如需詳細資訊，請參閱[排程資料集匯出](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling)。


#### 最後步驟

[檢閱](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review)您的選取專案，並在正確後，開始將輸出資料集匯出至雲端儲存空間目的地。

您必須[驗證](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)資料匯出成功。 匯出資料集時，Experience Platform會在目的地中定義的儲存位置中建立一或多個`.json`或`.parquet`檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立資料夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。

### 流程服務API

或者，您可以使用API匯出和排程匯出輸出資料集。 有關步驟已記錄在[使用流程服務API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets)匯出資料集內。

#### 開始使用

若要匯出資料集，請確定您具有[必要的許可權](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions)。 同時確認您要傳送輸出資料集的目的地支援匯出資料集。 然後，您必須[收集您在API呼叫中使用的必要和選用標頭](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers)的值。 您也需要[識別您要將資料集匯出至的目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec)的連線規格和流量規格ID。

#### 擷取合格的資料集

您可以[擷取符合匯出條件的資料集清單](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets)，並使用[`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API來驗證您的輸出資料集是否屬於該清單。


#### 建立來源連線

接下來，您必須使用唯一識別碼，為要匯出至雲端儲存空間目的地的輸出資料集[建立來源連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection)。 您使用[`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 驗證到目的地（建立基礎連線）

您現在必須[建立基礎連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection)，以使用[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API驗證並安全地儲存認證至您的雲端儲存空間目的地。


#### 提供匯出引數

接下來，您必須[&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection)建立其他目標連線，再次使用[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API為您的輸出資料集儲存匯出引數。 這些匯出引數包括位置、檔案格式、壓縮等等。

#### 設定資料流

最後，您[設定資料流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow)，以確保您的輸出資料集已使用[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API匯出至雲端儲存空間目的地。 在此步驟中，您可以使用`scheduleParams`引數定義匯出排程。

#### 驗證資料流

若要[檢查資料流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)的成功執行，請使用[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，將資料流ID指定為查詢引數。 此資料流ID是您設定資料流時傳回的識別碼。

[驗證](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)資料匯出成功。 匯出資料集時，Experience Platform會在目的地中定義的儲存位置中建立一或多個`.json`或`.parquet`檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立資料夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。

## 結論

簡而言之，模擬Adobe Analytics資料摘要功能隱含著使用查詢服務設定排程查詢，以及在排程資料集匯出中使用這些查詢的結果。

>[!IMPORTANT]
>
>此使用案例涉及兩個排程器。 為確保模擬資料摘要功能可正常運作，請確定在查詢服務和資料匯出中設定的排程不會干預。
