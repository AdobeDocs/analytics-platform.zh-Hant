---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 284c73374ca3fdfc4afbc2824209bebdc764fb64
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 96%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 4 月)

**上次更新日期**：2024 年 4 月 17 日

這些發行說明涵蓋 2024 年 4 月 10 日至 2024 年 5 月的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **串流媒體：將 Roku 資料傳送至 Adobe Experience Platform Edge** | 現在，[透過 Experience Platform Edge 安裝 Media Analytics](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) 時，您可以使用 Adobe Experience Platform Roku SDK 將串流媒體資料傳送至 Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **在報告活動管理員中公開每月報告** | 在報告活動管理員中檢視所有連線的報告活動時，現在可以使用一個圖表來顯示在 IMS 組織層級執行的 [每月報告/請求](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) (當月和上個月)。<p>**備註：**&#x200B;資料從 2024 年 3 月中開始提供。 | | 2024 年 4 月 15 日 |
| **行動計分卡中智慧型註解** | [智慧型註解](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)可協助非分析師在沒有分析師幫助下更能了解他們的資料。現在可在 Customer Journey Analytics 計分卡中使用。 |  | 2024 年 4 月 17 日 |
| **僅限專案 [!UICONTROL Workspace] 元件的權限增強** | 在過去，如果某位使用者 (使用者 A) 與另一位使用者 (使用者 B) 共用專案，並授予使用者 B 對專案的編輯存取權，則使用者 B 將可編輯該專案。但是，使用者B無法編輯 [!UICONTROL 快速篩選] 內嵌在專案中。 該限制現已移除 — 使用者B可以編輯 [快速篩選](/help/components/filters/quick-filters.md) 和嵌入共用專案的其他僅限專案元件。 |  | 2024 年 4 月 17 日 |
| **管理員可以管理其組織中的所有位置** | [「位置」頁面](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/locations/locations-manager)上的新選項可讓管理員檢視和管理組織中的所有位置。以前，管理員只能查看和管理他們建立的位置。 |  | 2024 年 4 月 |
| **Adobe Product Analytics 功能矩陣** | 了解您的核心、優勢、一次性和有疑問的功能是什麼，從而推動投資決策。[!UICONTROL 功能矩陣]是透過使用頻率與作用中使用者百分比來衡量事件，並與使用中位數進行比較。 | 2024 年 4 月 17 日 | 2024 年 4 月 30 日 |
| **Adobe Product Analytics：強化漏斗中的深入解析** | 在「[摩擦](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/guided-analysis/funnel/friction)」視圖中，書面深入解析已強化，以包括類別、增量和說明，從而進一步了解圖表和表格。 | 2024 年 4 月 17 日 | 2024 年 4 月 26 日 |
| **Adobe Product Analytics：強化保留視圖** | 「[保留率](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/guided-analysis/retention/retention-rates)」視圖中新增了多項功能，以推動更深入且可自訂的保留深入解析：<ul><li>解除連結開始和返回事件</li><li>在單一視圖中比較多個返回事件</li><li>自訂已套用在或晚於 (未繫結)、每個 (繫結) 和階層分類設定的保留模型</li><li>顯示和隱藏圖表中的各個同類群組列</li></ul> | 2024 年 4 月 24 日 | 2024 年 5 月 8 日 |
| **Adobe Product Analytics：比較單一漏斗步驟中的事件** | 現在起，您可以在[摩擦](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/guided-analysis/funnel/friction)視圖中比較單一漏斗步驟內的事件。您的歷程有步驟選項或有一個執行 A/B 實驗的步驟時，此功能特別實用。 | 2024 年 4 月 23 日 | 2024 年 5 月 3 日 |
| **對於人員到帳戶的 B2B 方案轉換** | 讓您轉換資料集，以便進一步支援 Customer Journey Analytics B2B 報告情境中基於人員的查詢。此功能可用於基於以下類別的 B2B 方案資料集：<ul><li>XDM 商業帳戶個人關係</li><li>XDM 商業機會個人關係</li><li>XDM 業務行銷清單會員</li><li>XDM 商業活動會員</li></ul> | | 2024 年 5 月 1 日 |
| **Experience Edge 機器人偵測** | [機器人偵測](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=zh-Hant)可讓您將 Web SDK、Mobile SDK 和伺服器 API 產生的事件識別為由已知編目程式和機器人產生。 | | 2024 年 5 月 1 日 |
| **衍生欄位：「下一個」或「上一個」函數** | 這些新功能可讓您將欄位作為輸入，然後識別前 n 個或下 n 個值，以便更完善地檢視使用者歷程。此功能還可以與「[!UICONTROL 衍生欄位]」中的其他函數 (例如「[!UICONTROL 串連]」) 結合使用，以建立新維度。 |  | 2024 年 5 月 1 日 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform 中的篩選和排序選項可讓您更快找到相關的對象。</li></ul> |  | 2024 年 5 月 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-319662；AN-337894；AN-338469；AN-340147；AN-340200；AN-340443；AN-341594；AN-342442；AN-342976；AN-343020；AN-343469；AN-343703；AN-343938；AN-344614；AN-344677；

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **資料視圖和連線 UI 中的連結已更新** | 2 月 15 日 | Adobe 計劃於三月初更新以下 Customer Journey Analytics 產品使用者介面中的連結。請據以更新您的書籤。<ul><li>**資料視圖頁面，資料視圖管理器**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**建立新資料視圖**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**編輯資料視圖**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新連結](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**連線管理器**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**連線資訊**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**編輯連線**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**建立新連線**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## 相關資源

* [2024 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2024.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
