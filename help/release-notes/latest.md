---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4f228dbe58a9efbe988f274c071c61ec5e36d321
workflow-type: ht
source-wordcount: '776'
ht-degree: 100%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 7 月)

**上次更新日期**：2024 年 7 月 29 日

這些發行說明涵蓋 2024 年 7 月 17 日至 2024 年 8 月的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智慧型警報** | Customer Journey Analytics 現已提供智慧型警報，讓您在資料發生異常事件時能立即收到通知。<p>您可以根據異常臨界值、變化百分比或特定資料點設定警報觸發。警報具有整合異常偵測的精細控制，在您最需要時觸發。</p><p>在 Customer Journey Analytics 中使用智慧型警報的流程，與在 Adobe Analytics 中使用智慧型警報幾乎相同。一個主要差異是 Customer Journey Analytics 未提供每小時警報。會有此項差異是因為可擷取的各種事件資料，僅能以延遲方式完成資料擷取 (通常在資料事件時間之後 3 至 9 小時)。</p><p>(更新的文件連結待補充)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 待定 |
| **將報告匯出至雲端時，用來控制帳戶和位置的管理員設定** | [位置管理器中的新「管理設定」標籤](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)可讓管理員控制使用者是否可以建立和編輯帳戶和位置。<p>使用者[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)及[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)時會套用這些設定。</p><p>管理員也能限制使用者可以建立和使用的帳戶類型。帳戶類型包括 Google Cloud Platform、Azure RBAC、Amazon S3、AEP Data Landing Zone、Snowflake 等。</p><p>以前，任何使用者都可以建立、編輯和使用所有類型帳戶的帳戶和位置。</p> | 2024 年 7 月 11 日 | 2024 年 7 月 19 日 |
| **摘要層級資料來源** | 允許您引入沒有人員 ID 的時間序列資料。此時間序列資料可用於支援各種使用案例，例如：<ul><li>將高層級效能指標作為事件層級資料的一部分或隨附提供。這可以是簡單的日期和單一量度值，也可以包含多個維度和量度，例如廣告印象、電子郵件開啟、廣告支出、已售出商品成本等。</li><li>每天、每週、每月或每季上傳目標，並根據事件層級量度定位這些目標，協助將量度相對於組織目標的趨勢分析視覺化。</li></ul><p>(更新的文件連結待補充)</p> |  | 2024 年 8 月 11 日 |
| **衍生欄位 -「重複資料刪除 - 重複」功能** | 衍生欄位中的[「重複資料刪除 - 重複」功能](/help/data-views/derived-fields/derived-fields.md#deduplicate)可協助您避免對某個值進行多次計數。 |  | 2024 年 7 月 17 日 |
| **替 CJA 客戶佈建引導式分析** | 引導式分析可讓使用者透過建置在 Customer Journey Analytics 跨管道資料上的引導式工作流程，自行取得有關客戶歷程的高品質資料和深入分析。 <p>從行銷到產品的跨職能團隊可以即時連結以使用和了解這些報告。</p><p>CJA 套件中現已提供多達 11 個引導式分析視圖。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024 年 7 月 17 日 |
| **共用帳戶和位置 (用於匯出和匯入)** | 使用者現在可以將其建立的帳戶和位置提供給組織中的所有使用者。只有帳戶和位置擁有者以及系統管理員，才能編輯和刪除帳戶與位置。先前，帳戶和位置只能由建立它們的使用者使用。這些設定可於使用者[設定雲端匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)及[設定雲端匯出位置](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)時使用。 | 2024 年 6 月 12 日 | 2024 年 7 月 19 日 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform 中的篩選器和排序選項，可讓您更快找到相關的對象。</li></ul> <p>(文件連結待補充)</p> |  | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-306000、AN-288748、AN-351547、AN-351110

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
