---
title: 模擬資料摘要功能
description: 瞭解如何以Experience Platform中的資料模擬Adobe Analytics資料摘要。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: d5719dddfb4cefda761370951973d55b3904032f
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 1%

---

# 模擬資料摘要功能

Adobe Analytics資料摘要是從Adobe Analytics中取得原始資料的有力方式。 此使用案例說明如何從Experience Platform中取得類似的原始資料，以便用於組織自行決定的其他Adobe之外的平台。

## 先決條件

使用此使用案例所述的功能之前，請確定您符合下列所有需求：

* 將線上和離線資料傳送至Experience Platform資料湖的有效實作。
* 存取查詢服務，此服務會封裝為平台式應用程式或資料Distiller附加元件的一部分。 另請參閱 [查詢服務封裝](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) 以取得詳細資訊。
* 已購買Real-Time CDP Prime或Ultimate套件、Adobe Journey Optimizer或Customer Journey Analytics的客戶可存取匯出資料集功能。 另請參閱 [將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hant) 以取得詳細資訊。
* 一或多個目的地(例如：Amazon S3、Google Cloud Storage)已設定為可在其中匯出資料摘要的原始資料。

## 簡介

模擬Adobe Analytics資料摘要的過程包括：

* 定義 **排定的查詢** ，為您的資料摘要產生資料，作為輸出資料集，使用 **查詢服務**.
* 定義 **排程的資料集匯出** ，會使用將輸出資料集匯出至雲端儲存空間目的地 **資料集匯出**.


![資料摘要](assets/data-feed.svg)


## 查詢服務

Experience Platform查詢服務可讓您查詢及聯結Experience Platform資料湖中的任何資料集，就好像它是資料庫表格一樣。 然後，您可以將結果擷取為新資料集，以供進一步用於報告或匯出。

您使用查詢服務 [使用者介面](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en)， a [使用者端透過PostgresSQL通訊協定連線](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en)，或 [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 以建立及排程收集資料摘要資料的查詢。

### 建立查詢

您可以使用標準ANSI SQL for SELECT敘述句和其他有限命令的所有功能，來建立和執行產生資料摘要資料的查詢。 另請參閱 [SQL語法](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) 以取得詳細資訊。 除了此SQL語法以外，Adobe還支援：

* 預先建立 [Adobe定義函式(ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) 可協助您對儲存在Experience Platform Data Lake中的事件資料執行常見的業務相關工作，包括 [工作階段化](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=zh-Hant) 和 [歸因](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hant)，
* 數個內建 [Spark SQL函式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en)，
* [中繼資料PostgreSQL命令](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en)，
* [準備的陳述式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### 範例

以下列出為資料摘要收集資料的一些查詢範例。 這些範例使用 `demo_system_event_dataset_for_website_global_v1_1` 作為範例體驗事件資料集，其中包含從與網站互動的客戶所收集到的資料。

+++前五大產品

*網站上檢視的五大產品為何？*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++產品互動漏斗

*網站上的各種產品互動為何？*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++人們做什麼

*使用者在進入「取消服務」頁面做為工作階段中的第三個頁面之前，會在網站上執行什麼動作？*

此查詢使用Adobe定義的函式 `SESS_TIMEOUT` 和 `NEXT`.

* 此 `SESS_TIMEOUT()` 會重現使用Adobe Analytics找到的造訪群組。 它執行類似的以時間為基礎的群組，但使用可自訂的引數。
* `NEXT()` 和 `PREVIOUS()` 協助您瞭解客戶如何導覽您的網站。

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++多少時間

*訪客造訪「取消服務」頁面後，多久之後才會致電客服中心？*

若要回答這類查詢，請使用 `TIME_BETWEEN_NEXT_MATCH()` Adobe定義的函式。 上一個或下一個相符函式之間的時間提供一個新維度，可測量自特定事件以來經過的時間。

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++結果如何

*客戶致電客服中心會有什麼結果？*

對於此查詢， `demo_system_event_dataset_for_website_global_v1_1` 以範例聯結資料集 `demo_system_event_dataset_for_call_center_global_v1_1` 包含客服中心互動的資料集。

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++行銷管道參與(Adobe Analytics資料)

*對於義大利文焦點網路流量，各行銷管道的參與度為何？*

例如，此範例使用由Adobe Analytics來源聯結器自動建立的資料集 `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

如需更多（進階）範例查詢，請參閱 [捨棄的瀏覽](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en)， [歸因分析](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en)， [機器人篩選](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)、以及查詢服務指南中的其他範例。


#### 身分

在Experience Platform中，有多種身分可供使用。 請確定您正在正確查詢身分。 在上述範例中，ECID被定義為核心物件的一部分，而核心物件本身是識別物件的一部分，兩者都使用體驗事件核心欄位群組新增到結構描述(例如： `_sampleorg.identification.core.ecid`)。 ECID在結構中的組織方式可能有所不同。

或者，您可以使用 `identityMap` 以查詢身分。 此物件的型別 `Map` 並使用 [巢狀資料結構](#nested-data-structure).

對於使用Adobe Analytics來源聯結器擷取的資料，可能有多個身分可供使用。 主要識別碼取決於ECID或AAID是否存在。 另請參閱 [Adobe Analytics資料中的主要識別碼](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) 和 [AAID、ECID、AACUSTOMID和Analytics來源聯結器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hant) 以取得詳細資訊

#### 資料摘要欄

您可以在查詢中使用的欄位（欄）取決於資料集所依據的結構定義。 請確定您瞭解資料集所根據的結構描述。

例如，在一些 [範例查詢](#examples) 您已查詢 *頁面名稱*.

* 在Adobe Analytics資料摘要的UI中，您可以選取 **[!UICONTROL pagename]** 作為欄，以新增至您的資料摘要定義。
* 在查詢服務中，您包括 `web.webPageDetails.name` 從 `demo_system_event_dataset_for_website_global_v1_1` 資料集(根據 **示範系統 — 網站的事件結構(Gobal v1.1)** 體驗事件結構描述)。 請參閱 [Web詳細資料結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) 以取得詳細資訊。

若要瞭解體驗事件資料集和基礎結構描述中，前Adobe Analytics資料欄和XDM欄位之間的對應，請參閱 [Analytics欄位對映](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant) 和 [Adobe Analytics ExperienceEvent完整擴充功能結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以取得詳細資訊。

此外，Experience Platform Web SDK自動收集的資訊（現成可用）也可能與識別查詢的欄有關。 另請參閱 [自動收集的資訊](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) 以取得詳細資訊。


#### 查詢

若要從其他資料集查詢資料，請使用標準的SQL功能（WHERE子句、INNER JOIN、OUTER JOIN等）。 請參閱 [結果如何](#examples) 在範例中查詢。

#### 計算

若要在欄位（欄）上執行計算，只需使用標準SQL函式(例如 `COUNT(*)` 在 [產品互動漏斗](#examples) 查詢)或 [數學和統計運運算元與函式](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) Spark SQL的一部分。

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

您可以使用 [`explode()` 或其他陣列功能](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) 從Spark SQL取得巢狀資料結構內的資料。

例如：

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

或者，您可以使用點標籤法來參照個別元素。 例如：

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

請參閱「[在 Query Service 中使用巢狀資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en)」以了解更多資訊。

### 排程查詢

您可以排程查詢，以確保查詢已執行，而且結果會以您偏好的間隔產生。 排程查詢時，您可以定義輸出資料集。

#### 使用查詢編輯器

您可以使用查詢編輯器排程查詢。 定義查詢的排程時，您可以定義輸出資料集。 另請參閱 [查詢排程](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) 以取得詳細資訊。


#### 使用查詢服務API

或者，您可以使用RESTful API來定義查詢和排程查詢。 另請參閱 [查詢服務API指南](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) 以取得詳細資訊。
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

