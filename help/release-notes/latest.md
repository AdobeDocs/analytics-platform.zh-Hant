---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5877ff515147964c2d4fbd6eaa43a8a99f0fe0
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 100%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 8 月)

**上次更新日期**：2024 年 8 月 14 日

這些發行說明涵蓋 2024 年 8 月 14 日至 2024 年 9 月的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **摘要層級資料來源** | 允許您引入沒有人員 ID 的時間序列資料。此時間序列資料可用於支援各種使用案例，例如：<ul><li>將高層級效能指標作為事件層級資料的一部分或隨附提供。這可以是簡單的日期和單一量度值，也可以包含多個維度和量度，例如廣告印象、電子郵件開啟、廣告支出、已售出商品成本等。</li><li>每小時或每天上傳目標，然後將這些目標與事件層級量度進行對比。這有助於可視化量度相對於組織目標的趨勢分析。</li></ul><p>如需詳細資訊，請參閱[摘要資料](/help/data-views/summary-data.md)。</p> | 2024 年 8 月 13 日 | 2024 年 8 月 21 日 |
| **客群已經發佈到 Experience Platform 中新的「客群」細分群體** | 現在起，從 Customer Journey Analytics 發佈的客群，可在 Adobe Experience Platform 的新「客群」細分群體中取得。<p>以前，從 Customer Journey Analytics 發佈的客群是在 Experience Platform 的「細分群體」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>客群出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的客群進行排序，其中會顯示最初發佈客群的應用程式。</li><li>Experience Platform 中的篩選和排序選項，可讓您更快找到相關的客群。</li></ul> <p>如需詳細資訊，請參閱文章「[建立和發佈客群](/help/components/audiences/publish.md)」中的「[在 Experience Platform 中使用 Customer Journey Analytics 客群](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform)」。</p> | 2024 年 9 月 | 2024 年 9 月 |
| **智慧型警報** | Customer Journey Analytics 中的智慧型警報，讓您在資料發生異常事件時能立即收到通知。<p>您可以根據異常臨界值、變化百分比或特定資料點設定警報觸發。警報具有整合異常偵測的精細控制，在您最需要時觸發。</p><p>在 Customer Journey Analytics 中使用智慧型警報的流程，與在 Adobe Analytics 中使用智慧型警報幾乎相同。一個主要差異是 Customer Journey Analytics 未提供每小時警報。會有此項差異是因為可擷取的各種事件資料，僅能以延遲方式完成資料擷取 (通常在資料事件時間之後 3 至 9 小時)。</p><p>(更新的文件連結待補充)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-354359；AN-351646；AN-346873；AN-352504；AN-353755；AN-354199；AN-354268；AN-354791；AN-354598；AN-354462；AN-354547；

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | | |

{style="table-layout:auto"}

## 相關資源

* [2024 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2024.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [串流媒體收集附加元件發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
