---
title: Data Mirror概觀
description: 瞭解如何在Data Warehouse原生解決方案和Customer Journey Analytics之間同步資料
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: 4b11c98d24b131eb32040943e869132c8182747f
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 1%

---

# Experience Platform Data Mirror概觀

{{release-limited-testing}}

Data Mirror是一項Experience Platform功能，可讓您使用模型型架構，將外部資料庫的列層級變更擷取到Data Lake。 它保留資料關係、強制執行唯一性，並支援版本化，而不需要上游擷取、轉換和載入(ETL)程式。

使用Experience Platform Data Mirror，直接將外部資料倉儲原生解決方案（[!DNL Snowflake]、[!DNL Azure Databricks]或[!DNL Google BigQuery]）的插入、更新及刪除（可變資料）與Experience Platform中的資料同步。 在將資料帶入Experience Platform時，Data Mirror可協助您保留現有的資料庫模型結構和資料完整性。

## 功能與優點

Data Mirror提供下列資料庫同步處理的基本功能：

* **主要金鑰強制執行。**&#x200B;確保資料集中的唯一性，並防止在擷取期間出現重複記錄。
* **資料列層級變更擷取。**&#x200B;支援包含精確控制的更新插入及刪除的細微資料變更。
* **結構描述關係。**&#x200B;透過描述項啟用資料集之間的外部和主索引鍵關係。
* **順序錯亂事件處理。**&#x200B;使用版本和時間戳記描述元處理變更事件，即使它們未依照順序到達。
* **直接倉儲整合。**&#x200B;與支援的雲端資料倉儲連線，以進行即時變更同步處理。

使用Data Mirror直接從來源系統擷取變更、強制執行結構描述完整性，並讓資料可用於分析、歷程協調及合規性工作流程。 Data Mirror可免除複雜的上游ETL程式，並透過啟用現有資料庫模型的直接映象來加速實作。 這種消除可透過精確控制刪除和資料衛生操作，從而增強資料治理。

另請參閱有關Data Mirror[的](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}Experience Platform檔案。

## 適用於Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>適用於Customer Journey Analytics的Experience Platform Data Mirror功能在&#x200B;**公開測試版**&#x200B;中提供，有效期至2026年3月25日。<br/><br/>在Beta期間：<ul><li>變更資料擷取(CDC)更新上限為Customer Journey Analytics的1000萬日變更列權利。</li><li>客戶可透過來源聯結器每天擷取多達200萬筆變更列至Adobe Experience Platform資料湖。</li></ul><br/>如果您的組織超過這些限制，Adobe保留終止Experience Platform Data Mirror功能測試版存取的權利。 <br/>若要要求存取此功能，請連絡您的Adobe帳戶團隊。
>

適用於Customer Journey Analytics的Experience Platform Data Mirror可用於選取的Data Warehouse原生解決方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Experience Platform Data Mirror需要正確設定下列應用程式或元件：

* [Data Warehouse原生解決方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象並使用模型資料](model-based.md)
>&#x200B;>[Data Mirror (Experience Platform檔案)](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/data-mirror/overview)
>&#x200B;>[以模型為基礎的結構描述(Experience Platform檔案)](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/model-based)
