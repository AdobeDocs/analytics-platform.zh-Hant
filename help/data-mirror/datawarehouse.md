---
title: 設定Data Warehouse原生解決方案
description: 瞭解如何為Customer Journey Analytics的Experience Platform Data Mirror設定Data Warehouse原生解決方案
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
autotag-review: '2026-05-19T08:56:46.637Z'
TQID: 'https://experienceleague.adobe.com/A3GkkNVAO9qpbOqCrZnf6PNJfRuwMaodJVOOuSRg0w8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: b3197353-f189-4932-8378-3f3bc40e6071id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: bfef374d-acfd-4c57-bf74-a2b36053c545
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 0%

---

# 設定Data Warehouse原生解決方案

{{release-limited-testing}}

為了支援適用於Customer Journey Analytics的Experience Platform Data Mirror，您要從三個支援的資料倉儲原生解決方案([[!DNL Azure Databricks]](#azure-databricks)、[[!DNL Google BigQuery]](#google-bigquery)、[[!DNL Snowflake]](#snowflake))使用的資料需要啟用才能擷取變更資料。


## [!DNL Azure Databricks]

啟用[!DNL Azure Databricks]資料表中的&#x200B;**變更資料摘要**，以在來源連線中使用變更資料擷取。

使用下列命令來啟用表格上的變更資料摘要：

**新資料表**

若要將變更資料摘要套用至新的資料表，您必須在`CREATE TABLE`命令中將資料表屬性`delta.enableChangeDataFeed`設定為`TRUE`。

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**現有的資料表**

若要將變更資料摘要套用至現有的資料表，您必須在`ALTER TABLE`命令中將資料表屬性`delta.enableChangeDataFeed`設定為`TRUE`。

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**所有新資料表**

若要將變更資料摘要套用至所有新表格，您必須將預設屬性設定為`TRUE`。

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

如需詳細資訊，請閱讀啟用變更資料摘要](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed)的[[!DNL Azure Databricks] 指南。

請閱讀下列檔案，以瞭解如何為[!DNL Azure Databricks]來源連線啟用變更資料擷取的步驟：

* [建立 [!DNL Azure Databricks] 基本連線](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks)。
* [為資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)建立來源連線。

## [!DNL Google BigQuery]

若要在您的[!DNL Google BigQuery]來源連線中使用變更資料擷取，請瀏覽至[!DNL Google Cloud]主控台中的[!DNL Google BigQuery]頁面，並將`enable_change_history`設定為`TRUE`。 此屬性可啟用資料表變更記錄。

如需詳細資訊，請閱讀 [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list)中[資料定義語言陳述式的指南。

請閱讀下列檔案，以瞭解如何為[!DNL Google BigQuery]來源連線啟用變更資料擷取的步驟：

* [建立 [!DNL Google BigQuery] 基本連線](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery)。
* [為資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)建立來源連線。

## [!DNL Snowflake]

啟用[!DNL Snowflake]資料表中的&#x200B;**變更追蹤**，以在來源連線中使用變更資料擷取。

在[!DNL Snowflake]中，使用`ALTER TABLE`並設定`CHANGE_TRACKING`為`TRUE`來啟用變更追蹤。

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

如需詳細資訊，請閱讀使用changes子句](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes)的[[!DNL Snowflake] 指南。

請閱讀下列檔案，以瞭解如何為[!DNL Snowflake]來源連線啟用變更資料擷取的步驟：

* [建立 [!DNL Snowflake] 基本連線](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake)。
* [為資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)建立來源連線。


>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象並使用關聯式資料](relational.md)
>
