---
title: 資料匯出使用案例
description: 瞭解用於Customer Journey Analytics的各種資料匯出使用案例
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 8118435a3982c405f76de9070afa05b8fd71ebf3
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# 資料匯出使用案例

本節提供資料匯出使用案例。 每個使用案例都在自己的文章中說明。 對於某些使用案例，會提供多個解決方案。

## 簡介

Adobe Analytics和Customer Journey Analytics之間的其中一項獨特差異，與歸因和工作階段化的資料處理有關。 另請參閱 [比較Adobe Analytics和Customer Journey Analytics的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) 以取得詳細資訊。

### Adobe Analytics：集合時間歸因和作業化。

在Adobe Analytics中，所有事件都會依裝置ID即時和順序處理，允許Adobe在收集時間產生、儲存和匯出具有持續或歸因值的點按資料流資料，包括：

* Dimension持續性（例如在90天後過期的促銷活動追蹤程式碼）。
* 造訪次數與工作階段化。
* Dimension值，由處理和VISTA規則計算。

這會影響從Adobe Analytics匯出資料：

* 初始收集後的資料處理是靜態的。
* 資料摘要包含「發佈」欄，以反映收集時間處理。


### Customer Journey Analytics：查詢時間歸因和作業化

在Customer Journey Analytics中，系統不會依順序收集事件，而是使用人員ID而非裝置ID，讓Customer Journey Analytics在報告時更新歸因和作業化。 這類資料收集引進了彈性，例如：

* 拼接可以 _重播_ 每日或每週的資料量，將匿名事件與已知事件建立關聯。 另請參閱 [拼接](../../stitching/overview.md) 以取得詳細資訊。
* 工作階段化和儲存值每次都會變更
   * 收集新資料或
   * 拼接會將事件新增到個人的歷程記錄中。

報表時間處理會影響資料從Customer Journey Analytics的匯出。 包含持續值的匯出內容不會符合Customer Journey Analytics報表，且值會隨著時間推移而消失。

為了量度一致性，建議您在Customer Journey Analytics中使用新功能。 一般而言，Experience Platform和Customer Journey Analytics資料匯出功能會超過Adobe Analytics的資料摘要功能。 Experience Platform和Customer Journey Analytics可提供：

* 新資料來源及處理作業須匯出資料

   * 包括非數位資料來源，
   * 根據商業規則套用自訂歸因和作業化，以及
   * 使用拼接功能保持客戶歷程更新。

* 實現量身打造的資料匯出使用案例

   * 將資料匯出至您所需的位置，包括Business Intelligence(BI)工具和雲端目的地，
   * 透過BI工具整合，保持資料與Analysis Workspace同步，
   * 您不需要在自己的系統中複製處理邏輯，
   * 新支援計算量度、衍生欄位和區段，以及

* 設計考量安全性和資料控管

   * 依使用者和目的地監控所有資料匯出，
   * 設定匯出資料的限制，以及
   * 設定傳送問題的警示以及排程傳送期間的限制。


## 使用案例和解決方案

一般而言，資料匯出支援許多使用案例。 就所需的資料以及如何存取和匯出該資料而言，每個使用案例都不同。 Experience Platform和Customer Journey Analytics提供許多功能，不論是獨立或結合使用，皆可解決各種使用案例。 下表概略介紹已識別的資料匯出使用案例，以及實施這些使用案例的Experience Platform和Customer Journey Analytics功能。

| 資料匯出使用案例 | Experience Platform和Customer Journey Analytics功能 |
|---|---|
| **資料備份**<br/>&#x200B;保留完整的數位資料復本，以符合法規或法規要求。 | **Experience Platform**： [**匯出資料集**](export-datasets.md)<br/>&#x200B;依排程或臨機將Experience Platform收集的資料直接匯出至雲端目的地。<br/>*目前限量版，Customer Journey Analytics客戶的完整版預計於2024年6月發行。* |
| **資料驗證**<br/>&#x200B;評估點按資料流資料的資料收集準確度。 | **Experience Platform**： [**查詢服務(資料Distiller)和匯出資料集**](queryservice-export-datasets.md)<br/> Interactive PostgreSQL介面使用您最愛的SQL工具執行臨機SQL查詢，以驗證資料集中的資料。<br/><br/>**Customer Journey Analytics**： [**匯出完整表格**](export-full-table.md)<br/>&#x200B;驗證來自CJA的處理資料，並套用歸因和工作階段化。 |
| **Data Lake、Data Warehouse或BI工具**<br/>&#x200B;將數位資料帶入您自己的BI工具或資料湖，以搭配其他資料集使用。 | **Customer Journey Analytics**： [**BI擴充功能**](bi-extension.md)<br/>&#x200B;將Customer Journey Analytics處理的量度新增至資料視覺化工具(例如Power BI)，並與自訂報表的其他資料結合&#x200B;<br/><br/>**Experience Platform**： [**查詢服務(資料Distiller)和匯出資料集**](queryservice-export-datasets.md)<br>&#x200B;使用SQL產生自訂的點按資料流資料，以傳送至雲端目的地。 |
| **AI/ML整備**<br/>&#x200B;使用Customer Journey Analytics資料增強人工智慧/機器學習模型和任務。 | **Customer Journey Analytics**： [**匯出完整表格**](export-full-table.md)<br/>&#x200B;將Customer Journey Analytics處理的維度和量度一次性或循環匯出至雲端目的地，包括計算量度和細分。<br/><br/>**Experience Platform**： [**查詢服務(資料Distiller)和匯出資料集**](queryservice-export-datasets.md)<br/>&#x200B;使用SQL產生自訂的點按資料流資料，以豐富AI/ML模型。 |
