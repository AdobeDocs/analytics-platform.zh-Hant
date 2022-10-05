---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc1a5b1b0f01ace6207820e2421d1770f68c3583
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 50%

---

# Customer Journey Analytics(CJA)發行說明（2022年10月）

**上次更新**:2022年10月5日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 相關資源

* [2022 年舊版 CJA 發行說明](/help/release-notes/2022.md)

* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)

* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **實驗面板** | 此全新的工作區面板可讓 CJA 使用者評估任何來源的任何 A/B 實驗的提升度和信賴度 - 線上、離線、來自 Adobe 解決方案、Adobe Journey Optimizer，甚至 BYO 資料。[了解更多](/help/analysis-workspace/c-panels/experimentation.md) | 2022 年 10 月 5 日 |
| **[!UICONTROL 關鍵量度摘要] 視覺效果** | 此 [!UICONTROL 關鍵量度摘要] 視覺效果可讓您查看重要量度在單一時間範圍內的趨勢。 也能讓您比較兩個時間範圍內的量度成效。了解更多 | 自2022年10月5日起分階段推出 |
| **CJA 中的日期欄位支援** | 允許 CJA 報告日期和日期時間欄位。[了解更多](/help/data-views/data-views-usecases.md#date) | 2022 年 10 月 5 日 |
| **行動應用程式：自訂詳細資料檢視** | 自訂詳細資料檢視可讓您更針對您與對象共用的資訊，讓對象專注於最重要的事項。 您可以變更與每個計分卡圖磚相關聯的詳細資料檢視的版面配置，並新增文字以更清楚說明一般使用者在資料中可能看到的內容。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=zh-Hant) | 2022 年 10 月 5 日 |

{style=&quot;table-layout:auto&quot;}

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **預設登陸頁面** | 2023年9月29日 | 此 [新登陸頁面](/help/getting-started/landing.md) 今年早些時候推出的體驗，將成為 **2023年1月**. 目前的頁面將遭取代，而且需要每個人都使用新體驗。 |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 29 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics已將此新資料集的採用延後至 **2023年1月**. 新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過提供的CJA資料 [!UICONTROL Analytics來源連接器] 也會自動利用新對應。 |
| **[!UICONTROL 異常偵測] 自動執行條件** | 2022 年 9 月 29 日 | 今天， [!UICONTROL 異常偵測] 在時間序列自由表格的所有欄上自動執行。 為確保資料可用於分析並加快專案載入速度，Adobe會變更 [!UICONTROL 異常偵測] 自動執行。 開始 **2022年10月26日**，異常偵測只會在表格中的第一個量度欄上自動執行。 您可以配置要運行的列設定 [!UICONTROL 異常偵測] ，視需要。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
