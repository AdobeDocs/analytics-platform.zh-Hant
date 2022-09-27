---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d2aec8976d7d81c28a6b9b76c58fec0fc2c3b360
workflow-type: ht
source-wordcount: '432'
ht-degree: 100%

---

# 目前的 Customer Journey Analytics (CJA) 發行說明 (2022 年 ９ 月)

**上次更新日期**：2022 年 9 月 14 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 相關資源

* [2022 年舊版 CJA 發行說明](/help/release-notes/2022.md)

* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)

* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Analytics 來源連接器的跨區域支援** | 您現在可以從任何區域擷取報告套裝 (美國、英國或新加坡)。然而，這些報告套裝必須對應至跟 Experience Platform 沙箱例項 (正在建立來源連線之處) 相同的組織。[了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) | 2022 年 8 月 24 日 |
| **首次工作階段報告** | 探索特定工作階段是否為使用者的首次工作階段。 [了解更多](/help/data-views/data-views-usecases.md) | 2022 年 8 月 24 日 |
| **CJA 的 Experimentation 面板** | 此全新的工作區面板可讓 CJA 使用者評估任何來源的任何 A/B 實驗的提升度和信賴度 - 線上、離線、來自 Adobe 解決方案、Adobe Journey Optimizer，甚至 BYO (自備) 資料。[了解更多](/help/analysis-workspace/c-panels/experimentation.md) | [限量版](/help/release-notes/releases.md) 2022 年 9 月 14 日開始發售 |
| **在 Workspace 中的組合圖表視覺效果** | 組合圖表讓您更輕鬆且直覺地比較在 Workspace 內的指標。[了解更多](/help/analysis-workspace/visualizations/combo-charts.md) | 2022 年 9 月 14 日 |
| **CJA 支援資料控管標籤和原則** | 自動化 CJA 與 Adobe Experience Platform 隱私權標籤和原則之間的整合。於資料集上建立的資料標籤為 Platform 所取用，會在 CJA 資料檢視中浮現，以阻止或警告從敏感性欄位建立量度和/或維度的使用者。此外，當從 CJA (透過工作區或 Report Builder 報告、匯出、API 等) 匯出資料時，將會新增其他警告或標籤，以通知使用者報告包含需要以特定方式處理敏感性資訊。[了解更多](/help/data-views/data-governance.md) | 2022 年 9 月 14 日 |

{style=&quot;table-layout:auto&quot;}

## 修正

AN-298412

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 9 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics 將在 **2022 年 10 月 5 日**&#x200B;採用此新的資料集。新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
