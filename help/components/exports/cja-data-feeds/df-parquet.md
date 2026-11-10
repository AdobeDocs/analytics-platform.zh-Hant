---
title: 使用Customer Journey Analytics資料摘要中的Parquet檔案
description: 瞭解Customer Journey Analytics資料摘要為何傳送Parquet檔案、Parquet如何與CSV、TSV和JSON比較，以及如何查詢或載入檔案。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%
---
# 在資料摘要中使用Parquet檔案

{{release-limited-testing}}

Customer Journey Analytics資料摘要會傳送Parquet格式的檔案。 大部分的現代資料倉儲都可以直接讀取Parquet檔案，因此在使用檔案之前，您通常不需要先轉換檔案。

使用下列資訊來瞭解資料摘要使用Parquet的原因、Parquet與其他檔案格式的比較方式，以及如何在Data Warehouse中查詢或載入Parquet檔案。

## 將Parquet用於資料摘要的優勢

Parquet比CSV、TSV或JSON更適合用於資料摘要輸出，原因如下：

* **寬摘要**：資料摘要可以有數百欄。 Parquet讓查詢只讀取它需要的欄。

* **巢狀欄位**： Parquet以原生方式表示巢狀欄位，例如產品清單。 CSV和TSV只能透過將其編碼為字串來表示它們。 如需詳細資訊，請參閱資料摘要[&#128279;](/help/components/exports/cja-data-feeds/df-sub-event.md)中的子事件元件。

* **內建結構描述**：每個Parquet檔案都儲存自己的結構描述，包括資料行名稱、資料型別和巢狀結構。 因為結構描述在檔案中，所以您的Data Warehouse可以直接從檔案建立表格。 您不需要提供單獨的標頭檔案或結構描述定義，而且Data Warehouse不需要推斷資料型別。

* **大型匯出**： Parquet通常會降低儲存和傳輸成本。 它也會避免在載入資料時進行文字剖析。

## Parquet與CSV、TSV和JSON的比較

CSV、TSV和JSON是常見的文字型檔案格式：

* **CSV和TSV**：每一列資料都是一行純文字，其值以逗號(CSV)或定位字元(TSV)分隔。 Adobe Analytics資料摘要會傳遞TSV檔案。 如需Customer Journey Analytics和Adobe Analytics中資料摘要的其他差異，請參閱[比較Customer Journey Analytics和Adobe Analytics中的資料摘要](/help/components/exports/cja-data-feeds/df-comparison.md)。

* **JSON**：每個記錄都儲存為具有具名欄位的文字，並可包含巢狀陣列和物件。

下表詳細說明了Parquet、CSV、TSV和JSON之間的差異：

| 特性 | Parquet | CSV或TSV | JSON |
| --- | --- | --- | --- |
| **查詢速度** | 快速。 查詢只會讀取它需要的欄。 | 較慢。 必須讀取及剖析整列。 | 較慢。 必須讀取及剖析整列。 |
| **資料類型** | 已輸入。 結構描述已內嵌在檔案中。 | 無型別。 所有值都是文字，載入資料時會推斷型別。 | 鬆散輸入。 |
| **巢狀資料** | 原生支援陣列和物件。 | 不支援。 陣列和物件必須平面化或編碼為字串。 | 原生支援陣列和物件。 |
| **可讀性** | 需要資料倉儲、DuckDB或Python等工具。 | 在文字編輯器或試算表中開啟。 | 在文字編輯器中開啟。 |

## 查詢或載入Parquet檔案

資料摘要檔案會以Parquet格式傳送至您[建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)時所選取的雲端儲存位置。

您通常不會下載檔案，而是將資料倉儲連線至儲存位置。 然後可以下列任一種方式使用Parquet檔案：

### 就地查詢檔案

定義指向雲端儲存空間中檔案的外部表格。 當您執行查詢時，Data Warehouse會讀取檔案。

* **Snowflake**：外部資料表，或針對外部階段的查詢
* **資料庫**：透過Amazon S3、Azure Data Lake Storage (ADLS)或Google雲端儲存空間的外部表格
* **BigQuery**：外部資料表透過Google雲端儲存空間
* **Amazon Redshift**： Amazon S3上的Redshift光譜

### 將檔案載入受管理的資料表

將檔案載入受管理表格是重複工作負荷的常見選擇。 例如：

* **Snowflake**： `COPY INTO`
* **BigQuery**：載入工作
* **資料庫**： `COPY INTO`或自動載入器

## 將Parquet資料轉換為CSV或JSON

如果您的下游流程需要CSV或JSON檔案，大部分資料倉儲和工具都可以在您載入Parquet資料後，將其匯出為任一格式。 例如，在Snowflake中，您可以將查詢結果解除安裝為CSV或具有`COPY INTO`的JSON。
