---
title: 設定Experience Platform
description: 瞭解如何為Customer Journey Analytics的Experience Platform Data Mirror設定結構描述和資料集
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 2%

---

# 設定Experience Platform

{{release-limited-testing}}

適用於Customer Journey Analytics的Experience Platform Data Mirror需要正確設定數個Experience Platform元件：

* 綱要
* 資料集
* 來源聯結器

請尋找在設定這些元件中每個元件時應考量的以下詳細資料。

## 結構描述

您需要建立以模型為基礎的[結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based){target="_blank"}，以模型化您要映象的資料倉儲原生表格。 當您建構以模型為基礎的結構描述時，請確保符合下列需求：

* 當提示您輸入以模型為基礎的結構描述型別時，請確定您選取手動選項。
* 為資料型別選取適當的結構描述。 請注意，Experience Platform Data Mirror主要用於時間序列資料（例如事件資料）。

* 定義結構描述中的欄位及其屬性
* 為以模型為基礎的結構描述中的欄位設定必要屬性：

   * 主索引鍵
   * 版本識別碼
   * 時間戳記識別碼（適用於時間序列資料）。

## 資料集

您可以預先為結構描述設定資料集，或在設定來源聯結器時建立資料集。
當您預先建立資料集或選取資料集時，請確保資料使用您先前建立的模型式[結構描述](#schema)。


## 來源連接器

若要將來源聯結器設定為支援的Data Warehouse原生解決方案，您可以使用來源工作流程來引導您完成設定。 該工作流程包含下列步驟：

### Authentication

如需針對支援的Data Warehouse原生解決方案進行驗證的相關資訊，請參閱Experience Platform相關檔案：

* [Azure資料庫](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### 選取資料

成功連線至您的Data Warehouse原生解決方案後，請從您要用於資料映象的Data Warehouse原生解決方案中選取表格。 選取後，會顯示資料內容的預覽。


### 資料流詳細資料

請確定您已啟用變更資料擷取。 您會看到資訊面板，說明變更資料擷取的需求。

指定新的或現有的資料集，這些資料集以您先前建立的模型架構為基礎。 在資料流詳細資料介面中指定並選取其他選項。


### 映射

將Data Warehouse原生解決方案中表格的欄位對應到您為模型架構指定的欄位。


### 排程

定義排程，將資料從Data Warehouse原生解決方案的表格映象至Experience Platform的資料集。


### 請檢閱

檢閱支援資料映象和變更資料擷取的資料倉儲原生解決方案的來源聯結器設定。


完成來源聯結器的設定後，就會建立資料流。 從那時起，Data Warehouse原生解決方案中的資料變更（插入、更新、刪除）會映象到指定的資料集。


>[!MORELIKETHIS]
>
>[Data Mirror快速入門手冊：映象並使用模型資料](model-based.md)
>>[Data Mirror (Experience Platform檔案)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>>[以模型為基礎的結構描述(Experience Platform檔案)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
