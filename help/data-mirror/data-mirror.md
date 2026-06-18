---
title: Data Mirror概觀
description: 瞭解如何在Data Warehouse原生解決方案和Customer Journey Analytics之間同步資料
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 3%

---

# Experience Platform Data Mirror概觀

Data Mirror是Experience Platform的一項功能，可讓您使用關聯式結構描述，將外部資料庫的列層級變更擷取到Data Lake。 它保留資料關係、強制執行唯一性，並支援版本化，而不需要上游擷取、轉換和載入(ETL)程式。

使用Experience Platform Data Mirror，直接將外部資料倉儲原生解決方案（[!DNL Snowflake]、[!DNL Azure Databricks]或[!DNL Google BigQuery]）的插入、更新及刪除（可變資料）與Experience Platform中的資料同步。 在將資料帶入Experience Platform時，Data Mirror可協助您保留現有的資料庫模型結構和資料完整性。

## 功能與優點

Data Mirror提供下列資料庫同步處理的基本功能：

* **主要金鑰強制執行。** 確保資料集中的唯一性，並防止在擷取期間出現重複記錄。
* **資料列層級變更擷取。** 支援精細資料變更，包括精確控制的更新插入和刪除。
* **結構描述關聯性。** 透過描述項啟用資料集之間的外部和主索引鍵關係。
* **處理順序錯亂的事件。** 使用版本和時間戳記描述項來處理變更事件，即使它們非依序到達亦然。
* **直接倉儲整合。** 與支援的雲端資料倉儲連線，以進行即時變更同步。

使用Data Mirror直接從來源系統擷取變更、強制執行結構描述完整性，並讓資料可用於分析、歷程協調及合規性工作流程。 Data Mirror可免除複雜的上游ETL程式，並透過啟用現有資料庫模型的直接映象來加速實作。 這種消除可透過精確控制刪除和資料衛生操作，從而增強資料治理。

另請參閱有關Data Mirror[&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}的Experience Platform檔案。

## 適用於Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>Data Mirror是一項功能，可支援使用變更資料擷取(CDC)同步處理特定資料倉儲的資料，以便在Customer Journey Analytics中進行分析。<br/>請參閱適用的產品說明，瞭解此功能如何影響年度擷取限制耗用量。
>

>[!IMPORTANT]
>
>您在Experience Platform中針對Customer Journey Analytics的Data Mirror所建立的變更資料擷取資料集，不應在其他Experience Platform解決方案（如Real-Time Customer Data Platform或Journey Optimizer）中重複使用。 如果您想要對這些解決方案使用相同的資料，請考慮使用相同的資料建立替代資料集。
>



適用於Customer Journey Analytics的Experience Platform Data Mirror可用於選取的Data Warehouse原生解決方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Experience Platform Data Mirror需要正確設定下列應用程式或元件：

* [資料倉儲原生解決方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象並使用關聯式資料](relational.md)
>[Data Mirror （Experience Platform檔案）](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[關聯式結構描述（Experience Platform檔案）](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/relational)
