---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7d915fc9b50163b7ec9c48232b99a85a3b063a77
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 52%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 7 月)

**上次更新日期**：2024年7月17日

這些發行說明涵蓋2024年7月17日至2024年8月的發行期。 Adobe Customer Journey Analytics發行會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。 因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智慧型警報** | 智慧型警報現在可在Customer Journey Analytics中使用，讓您在資料中發生異常事件時立即收到通知。<p>您可以設定要根據異常臨界值、變更的百分比或特定資料點觸發的警報。 警報提供與「異常偵測」整合的精細控制項，會在您最需要時觸發。</p><p>在Customer Journey Analytics中使用智慧型警報的程式幾乎與在Adobe Analytics中使用智慧型警報相同。 其中一個主要差異在於Customer Journey Analytics不提供每小時警報。 此差異是因為可擷取的各種事件資料的資料擷取作業僅會在延遲後完成，延遲時間通常比資料事件時間晚3至9小時。</p><p>（更新說明檔案連結，請前往）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 2024年7月26日 |
| **將報告匯出至雲端時，用來控制帳戶和位置的管理員設定** | [位置管理器中的新「管理設定」標籤](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)可讓管理員控制使用者是否可以建立和編輯帳戶和位置。<p>使用者[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)及[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)時會套用這些設定。</p><p>管理員也能限制使用者可以建立和使用的帳戶類型。帳戶類型包括 Google Cloud Platform、Azure RBAC、Amazon S3、AEP Data Landing Zone、Snowflake 等。</p><p>以前，任何使用者都可以建立、編輯和使用所有類型帳戶的帳戶和位置。</p> | 2024 年 7 月 11 日 | 2024 年 7 月 19 日 |
| **摘要層級資料來源** | 可讓您匯入沒有人員ID的時間序列資料。 此時間序列資料可用於支援各種使用案例，例如：<ul><li>將高階績效指標呈現為事件層級資料的一部分或旁邊。 這可能包括簡單的日期和單一量度值，也可能包括多個維度和量度，例如廣告曝光數、電子郵件開啟、廣告支出、銷售商品成本等。</li><li>每日、每週、每月或每季上傳目標或指標，並依據事件層級的量度來定位這些目標或指標，以便視覺化量度相對於組織目標或目標的趨勢。</li></ul><p>（更新說明檔案連結，請前往）</p> |  | 2024年7月31日 |
| **衍生欄位 — 重複資料刪除函式** | 衍生欄位中的[重複資料刪除函式](/help/data-views/derived-fields/derived-fields.md#deduplicate)可協助您避免重複計算值。 |  | 2024年7月17日 |
| 為CJA客戶&#x200B;**引導式分析布建** | 引導式分析可讓使用者透過引導式工作流程(以Customer Journey Analytics的跨管道資料為基礎)，針對客戶歷程提供高品質的資料和深入分析。 <p>從行銷到產品的跨職能團隊可以即時連結以使用和了解這些報告。</p><p>CJA套件中現在提供最多11個引導式分析檢視。 [了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024年7月17日 |
| **共用帳戶和位置 (用於匯出和匯入)** | 使用者現在可以將其建立的帳戶和位置提供給組織中的所有使用者。只有帳戶和位置擁有者以及系統管理員，才能編輯和刪除帳戶與位置。先前，帳戶和位置只能由建立它們的使用者使用。這些設定可於使用者[設定雲端匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)及[設定雲端匯出位置](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)時使用。 | 2024 年 6 月 12 日 | 2024 年 7 月中旬 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform中的篩選和排序選項可讓您更快地找到相關對象。</li></ul> <p>(文件連結待補充)</p> |  | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-306000； AN-288748； AN-351547； AN-351110

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
