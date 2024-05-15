---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 36badebf0710131b2f831feb645f20d8dd888b9b
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 43%

---

# 最新Adobe Customer Journey Analytics發行說明（2024年5月）

**上次更新**：2024年5月9日

這些發行說明涵蓋2024年5月15日至2024年6月的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI擴充功能** | BI擴充功能可讓SQL存取您在Customer Journey Analytics中定義的資料檢視。 [了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024年5月15日 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform 中的篩選和排序選項可讓您更快找到相關的對象。</li></ul> [了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/audiences/publish) |  | 2024年5月15日 |
| **用於Customer Journey Analytics的AI助理** | 可讓您在Customer Journey AnalyticsUI中詢問自然語言問題，並根據Customer Journey Analytics檔案取得答案。 (後續文件連結) | | 2024年5月30日 |
| **串流媒體：使用Web SDK傳送Web資料至Adobe Experience Platform Edge Network** | 您現在可以使用Adobe Experience Platform Web SDK將串流媒體網頁資料傳送到Adobe Experience Platform Edge Network，讓您建立更個人化的行銷活動並提供更個人化的內容，從而得到更多要報告的追蹤資料。<p>此增強功能為跨所有平台解決方案(例如Customer Journey Analytics、RT-CDP、AJO和事件轉送)的Web實施提供統一的收集方法。 過去，將串流媒體網頁資料傳送至Edge Network的唯一方式是使用Media Edge API。 [了解更多](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 2024 年 5 月 31 日 |
| **衍生欄位 — 數學函式** | 可讓您在資料檢視中執行簡單的數學運運算元，以回答有關使用者的問題。 例如，您可以將產品、保固和送貨收入結合在一起。 (後續文件連結) | | 2024年6月5日 |
| **衍生欄位 — 下一個或上一個函式** | 讓您檢視下一個或上一個值。 例如，在選取的行銷管道之前，某人先前互動的行銷管道為何？ 或者，使用者在選取頁面之前或之後互動的頁面為何？ 使用者在進店前互動最熱門的頻道為何？  (後續文件連結) | | 2024年6月12日 |
| **有關從Adobe Analytics升級至Customer Journey Analytics的新檔案** | 對於從Adobe Analytics升級至Customer Journey Analytics的組織，根據組織目前的Adobe Analytics實作和長期目標，有多種升級選項和許多需要牢記的考量事項。 現在提供新的文件資源來協助您更加瞭解：<ul><li>存在的各種升級路徑</li><li>根據組織目前的 Adobe Analytics 實作可以使用哪些升級路徑</li><li>每種升級路徑的優點和缺點</li><li>每個升級路徑的逐步操作指導</li><li>處理歷史資料的考量事項</li></ul>[開始升級至Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 現在可用 |
| **有關的新檔案 [資料匯出使用案例](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | 本節概述資料匯出使用案例，例如<ul><li>資料備份</li><li>資料驗證</li><li>Data Lake、Data Warehouse或BI工具</li><li>AI/ML整備</li></ul> 以及如何使用Experience Platform和Customer Journey Analytics功能實作這些方法。 | | 現在可用 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-342309、AN-342312、AN-345267、AN-345909、AN-346016、AN-346049、AN-346052、AN-346287、AN-346624、AN-347919

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | | |

{style="table-layout:auto"}

## 相關資源

* [2024 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2024.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
