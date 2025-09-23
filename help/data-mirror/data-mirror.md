---
title: Data Mirror概觀
description: 瞭解如何在Data Warehouse原生解決方案和Customer Journey Analytics之間同步資料
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# Experience Platform Data Mirror概觀

{{release-limited-testing}}

Data Mirror是一項Experience Platform功能，可讓您使用模型型架構，將外部資料庫的列層級變更擷取到Data Lake。 它保留資料關係、強制執行唯一性，並支援版本化，而不需要上游擷取、轉換、載入(ETL)程式。

使用Data Mirror同步處理外部資料倉儲原生解決方案（例如[!DNL Snowflake]、[!DNL Azure Databricks]或[!DNL Google BigQuery]）的插入、更新及刪除（可變資料），並直接將之移入Experience Platform。 在將資料帶入Experience Platform時，Data Mirror可協助您保留現有的資料庫模型結構和資料完整性。


## 功能與優點

Data Mirror提供下列資料庫同步處理的基本功能：

* **主要金鑰強制執行**。 確保資料集中的唯一性，並防止在擷取期間出現重複記錄。
* **資料列層級變更擷取**。 支援精細資料變更，包括精確控制的更新插入和刪除。
* **結構描述關係**。 透過描述項啟用資料集之間的外部和主索引鍵關係。
* **順序錯亂事件處理**。 使用版本和時間戳記描述項來處理變更事件，即使它們非依序到達亦然。
* **直接倉儲整合**。 與支援的雲端資料倉儲連線，以進行即時變更同步。

使用Data Mirror直接從來源系統擷取變更、強制執行結構描述完整性，並讓資料可用於分析、歷程協調及合規性工作流程。 Data Mirror可免除複雜的上游ETL程式，並透過啟用現有資料庫模型的直接映象來加速實作。 這種消除可透過精確控制刪除和資料衛生操作，從而增強資料治理。

<!-- Add link when AEP docs are ready... -->

另請參閱有關Data Mirror的Experience Platform檔案。


## 適用於Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>適用於Customer Journey Analytics的Experience Platform Data Mirror功能在&#x200B;**公開測試版**&#x200B;中提供，有效期至2026年3月25日。 在Beta版期間，變更資料擷取(CDC)更新僅限於貴組織每月資料列的0.5%。 每月資料列數的計算方式是您每年有權取得資料列數除以12。 如果您的組織超過此限制，Adobe保留權利終止對Experience Platform Data Mirror的Customer Journey Analytics功能測試版存取。
>

適用於Customer Journey Analytics的Experience Platform Data Mirror功能適用於選取的資料倉儲原生解決方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Data Mirror功能需要數個元件的正確設定和設定：

* [Data Warehouse原生解決方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象並使用模型資料](data-mirror.md)
>