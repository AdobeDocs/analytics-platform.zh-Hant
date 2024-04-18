---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 69566b840301f87a6362d6bd16b1e255a14d4e23
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 46%

---

# 最新Adobe Customer Journey Analytics發行說明（2024年4月）

**上次更新**：2024年4月17日

這些發行說明涵蓋2024年4月10日至2024年5月的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **串流媒體：將Roku資料傳送至Adobe Experience Platform Edge** | 現在，當 [使用Experience Platform Edge安裝Media Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)，您可以使用Adobe Experience Platform Roku SDK傳送串流媒體資料給Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **在報告活動管理器中顯示每月報告** | 在報告活動管理器中檢視所有連線的報告活動時，現在可以使用圖形來顯示 [每月報表/請求](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) 目前和上個月在IMS組織層級執行的專案。<p>**注意：** 在2024年3月期間開始提供資料。 | | 2024年4月15日 |
| **行動計分卡中智慧型註解** | [智慧型註解](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)可協助非分析師在沒有分析師幫助下更能了解他們的資料。現在可在 Customer Journey Analytics 計分卡中使用。 |  | 2024 年 4 月 17 日 |
| **僅限專案的許可權增強功能 [!UICONTROL 工作區] 元件** | 先前，如果一位使用者（使用者A）與另一位使用者（使用者B）共用專案，並授與使用者B專案的編輯存取權，則使用者B將能夠編輯專案。 但是，使用者B無法編輯 [!UICONTROL 快速區段] 內嵌在專案中。 該限制現已移除 — 使用者B可以編輯 [!UICONTROL 快速區段] 和嵌入共用專案的其他僅限專案元件。 |  | 2024 年 4 月 17 日 |
| **管理員可以管理他乞組織中的所有位置** | 上的新選項 [位置頁面](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) 可讓管理員檢視及管理組織中的所有位置。 以前，管理員只能查看和管理他們建立的位置。 |  | 2024 年 4 月 17 日 |
| **Adobe Product Analytics：功能對照表** | 瞭解您的核心、效能、一次性和可疑功能，有助於做出投資決策。 [!UICONTROL 功能矩陣] 會依使用頻率vs %作用中使用者來測量事件，並與使用中值比較。 | 2024 年 4 月 17 日 | 2024 年 4 月 30 日 |
| **Adobe Product Analytics：漏斗中的增強型深入分析** | 在 [摩擦](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 檢視，已增強書面深入分析，其中包含類別、增量及說明，以進一步瞭解圖表和表格。 | 2024 年 4 月 17 日 | 2024年4月26日 |
| **Adobe Product Analytics：增強的保留檢視** | 幾項功能已新增至 [保留](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) 費率檢視，以推動更深入且可自訂的保留率深入分析：<ul><li>解除連結開始和返回事件</li><li>在單一檢視中比較多個傳回事件</li><li>自訂套用在（無限制）上或之後、在每個（有限制）和括弧設定上的保留模型</li><li>在圖表中顯示和隱藏個別同類群組列</li></ul> | 2024年4月24日 | 2024年5月8日 |
| **Adobe Product Analytics：比較單一漏斗步驟中的事件** | 您現在可以在的單一漏斗步驟中比較事件 [摩擦](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 檢視。 當您的歷程有步驟選項或有一個執行 A/B 實驗的步驟時，此功能尤其實用。 | 2024年4月23日 | 2024年5月3日 |
| **對於人員到帳戶的 B2B 方案轉換** | 讓您轉換資料集，以便進一步支援 Customer Journey Analytics B2B 報告情境中基於人員的查詢。此功能可用於基於以下類別的 B2B 方案資料集：<ul><li>XDM 商業帳戶個人關係</li><li>XDM 商業機會個人關係</li><li>XDM 業務行銷清單會員</li><li>XDM 商業活動會員</li></ul> | | 2024年5月1日 |
| **Experience Edge 機器人偵測** | [機器人偵測](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=zh-Hant)可讓您將 Web SDK、Mobile SDK 和伺服器 API 產生的事件識別為由已知編目程式和機器人產生。 | | 2024年5月1日 |
| **衍生欄位： Next或Previous函式** | 這些新功能可讓您以欄位作為輸入，然後識別n個上一個或n個下一個值，以取得使用者歷程的更佳檢視。 此功能也可以與中的其他功能結合 [!UICONTROL 衍生欄位]，例如 [!UICONTROL 串連]，以建立新維度。 |  | 2024年5月1日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-319662、AN-337894、AN-338469、AN-340147、AN-340200、AN-340443、AN-341594、AN-342442、AN-342976、AN-343020、AN-343469、AN-343703、AN-343938、AN-344614、AN-344677；

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
