---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f961bf0a615199de931a98f14d8b640890df7a2b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 66%

---

# 最新Customer Journey Analytics(CJA)發行說明（2022年9月）

**上次更新日期**：2022 年 9 月 9 日

>[!NOTE]
>
>本頁面包含搶鮮版內容，且可能有所變更。

## 相關資源

* [2022年舊版CJA發行說明](/help/release-notes/2022.md)

* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)

* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)

* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Analytics 來源連接器的跨區域支援** | 您現在可以從任何區域擷取報告套裝 (美國、英國或新加坡)。然而，這些報告套裝必須對應至跟 Experience Platform 沙箱例項 (正在建立來源連線之處) 相同的組織。[了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) | 2022 年 8 月 24 日 |
| **首次工作階段報告** | 探索特定工作階段是否為使用者的首次工作階段。 [了解更多](/help/data-views/data-views-usecases.md) | 2022 年 8 月 24 日 |
| **CJA的實驗面板** | 這個新的「工作區」面板可讓CJA使用者透過任何來源(線上、離線、Adobe解決方案、Adobe Journey Optimizer，甚至BYO（自備）資料)評估任何A/B實驗的提升度和可信度。 [了解更多](/help/analysis-workspace/c-panels/experimentation.md) | [有限版本](/help/release-notes/releases.md) 從2022年9月14日起 |
| **工作區中的組合圖視覺效果** | 組合圖表可讓您在工作區中更輕鬆、直覺地比較量度。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en) | 2022 年 9 月 14 日 |

{style=&quot;table-layout:auto&quot;}

## 修正

AN-298412

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 9 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics將採用此新資料集 **2022年10月5日**. 新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
