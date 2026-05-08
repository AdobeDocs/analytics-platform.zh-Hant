---
title: Data Mirror概觀
description: 瞭解如何在Data Warehouse原生解決方案和Customer Journey Analytics之間同步資料
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Experience Platform Data Mirror概觀

{{release-limited-testing}}

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

另請參閱有關Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}的[Experience Platform檔案。

## 適用於Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>Data Mirror是目前在Beta版中的功能，可支援使用變更資料擷取(CDC)同步處理特定資料倉儲的資料，以便在Customer Journey Analytics中進行分析。<br/>此功能將於2026年6月18日正式提供給Customer Journey Analytics。 請參閱適用的產品說明，瞭解其如何影響未來的年度擷取限制耗用量。 請注意，當Data Mirror從Beta版過渡到全面推出時，您的組織仍能存取此功能。
>

適用於Customer Journey Analytics的Experience Platform Data Mirror可用於選取的Data Warehouse原生解決方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Experience Platform Data Mirror需要正確設定下列應用程式或元件：

* [資料倉儲原生解決方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象及使用關聯式資料](relational.md)
>[Data Mirror （Experience Platform檔案）](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[關聯式結構描述（Experience Platform檔案）](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/relational)
