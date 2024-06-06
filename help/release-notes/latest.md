---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c3fbf86e06e47583165a661683bc7490ecd1b17f
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 99%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 5 月)

**上次更新**：2024年6月6日

這些發行說明涵蓋 2024 年 5 月 15 日至 2024 年 6 月的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **適用於 Customer Journey Analytics 的 AI 助理** | 允許您在 Customer Journey Analytics UI 中提出自然語言的問題，並根據 Customer Journey Analytics 文件獲得答案。[了解更多](/help/ai-assistant.md) | | 2024年6月6日 |
| **BI 擴充功能** | BI 擴充功能可讓 SQL 存取您在 Customer Journey Analytics 中定義的資料視圖。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024 年 5 月 15 日 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform 中的篩選和排序選項可讓您更快找到相關的對象。</li></ul> <p>(更新的後續文件連結)</p> |  | 2024 年 5 月下旬至 6 月上旬 |
| **串流媒體：使用 Web SDK，將 Web 資料傳送至 Adobe Experience Platform Edge Network** | 現在，您可以使用 Adobe Experience Platform Web SDK 將串流媒體 Web 資料傳送至 Adobe Experience Platform Edge Network，讓您能夠建立更個人化的行銷活動並提供更個人化的內容，最後獲得更多可供報告的追蹤資料。<p>此增強功能可為所有平台解決方案 (例如 Customer Journey Analytics、RT-CDP、AJO 和事件轉送) 的 Web 實施提供統一的資料收集方法。以前，將串流媒體 Web 資料傳送到 Edge Network 時，唯一的方法就是使用 Media Edge API。 <p>[了解更多](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 2024 年 5 月 29 日 |
| **衍生欄位 - 數學函數** | 讓您在資料視圖中執行簡單的數學運算子，以便回答有關使用者的問題。例如，您可以合併產品、保固和運送等收入。 <p>(更新的後續文件連結)</p> | | 2024 年 6 月 5 日 |
| **共用帳戶和位置 (用於匯出和匯入)** | 使用者現在可以將其建立的帳戶和位置提供給組織中的所有使用者。只有帳戶和位置擁有者以及系統管理員才能編輯和刪除帳戶與位置。<p>先前，帳戶和位置只能由建立它們的使用者使用。</p><p>當使用者設定雲端匯出帳戶和設定雲端匯出位置時，可使用這些設定。</p> <p>(更新的後續文件連結)</p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **關於從 Adobe Analytics 升級到 Customer Journey Analytics 的新文件** | 對於從 Adobe Analytics 升級到 Customer Journey Analytics 的組織來說，根據組織目前的 Adobe Analytics 實作和長期目標，有多種升級選項和許多需要牢記的考量事項。現在提供新的文件資源來協助您更加瞭解：<ul><li>存在的各種升級路徑</li><li>根據組織目前的 Adobe Analytics 實作可以使用哪些升級路徑</li><li>每種升級路徑的優點和缺點</li><li>每個升級路徑的逐步操作指導</li><li>處理歷史資料的考量事項</li></ul>[開始升級到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 現已提供 |
| **有關[資料匯出使用案例](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-usecases/data-export/overview)的文件** | 此全新部分列有資料匯出的使用案例，例如<ul><li>資料備份</li><li>資料驗證</li><li>資料湖、Data Warehouse 或 BI 工具</li><li>為 AI/ML 做好準備</li></ul> 以及如何使用 Experience Platform 和 Customer Journey Analytics 功能來實施。 | | 現已提供 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-342309；AN-342312；AN-345267；AN-345909；AN-346016；AN-346049；AN-346052；AN-346287；AN-346624；AN-347919

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
