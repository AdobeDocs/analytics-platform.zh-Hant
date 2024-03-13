---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7f0a348738d2f3a53ec57558d321a3501afe8d00
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 48%

---

# 最新Adobe Customer Journey Analytics發行說明（2024年3月）

**上次更新**：2024年3月13日

這些發行說明涵蓋2024年3月13日到2024年4月的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **「專案」登陸頁面上可用的新欄** | 此 **[!UICONTROL 上次使用日期]** 現在當您在檢視專案標籤時 [Customer Journey Analytics登陸頁面](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html). <p>此資訊可顯示專案上次開啟的日期和時間，以協助您判斷專案是否對貴組織中的使用者有用。 先前， **[!UICONTROL 上次使用日期]** 欄僅在計算量度管理員、區段管理員和警報管理員中可用。</p> |  | 2024 年 3 月 13 日 |
| **使用情況量度** | 此 [使用量度介面](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant) 顯示所有連線中擷取及可報告資料列的使用情形。 此介面可讓您確定您的 Customer Journey Analytics 使用情況是否符合合約約定。 |  | 2024 年 3 月 13 日 |
| **Media Analytics 報告 - 平均每分鐘對象數 (AMA)** | CJA 現已提供「平均每分鐘對象數」面板。Media Analytics客戶可以使用「平均每分鐘觀眾數」面板來更瞭解其內容的平均使用量。 <p>「平均每分鐘對象數」可比較任何長度或類型的節目。 此外，客戶也可以比較這個數位平均每分鐘觀眾數和線性電視的平均每分鐘量度，或是將前者附加到後者。</p><p> 此面板提供較大的彈性來測量自訂時段的平均對象數，以及事後更新了持續時間分類時的平均對象數。</p><p>如需詳細資訊，請參閱 [「媒體平均每分鐘觀眾數」面板](/help/analysis-workspace/c-panels/average-minute-audience-panel.md).</p> |  | 2024 年 3 月 12 日 |
| **個人對帳戶的B2B結構描述轉換** | 可讓您轉換資料集，以便在Customer Journey AnalyticsB2B報表情境中更支援以人物為基礎的查詢。 此功能適用於根據下列類別的B2B結構描述資料集：<ul><li>XDM商業帳戶個人關係</li><li>XDM商業機會個人關係</li><li>XDM業務行銷清單成員</li><li>XDM商業活動會員</li></ul> | | 2024年3月26日 |
| **Adobe Product Analytics：比較單一漏斗步驟中的事件** | 在「漏斗：摩擦」檢視中，您現在可以在單一漏斗步驟中比較事件。 如果您的歷程有步驟選項或A/B實驗執行的步驟，這會特別有用。 | 2024年3月29日 | 2024年4月12日 |
| **管理員可以管理其組織中的所有位置** | 「位置」頁面上的新選項可讓管理員檢視及管理組織中的所有位置。 以前，管理員只能檢視和管理他們建立的位置。 | | 2024 年 4 月 |
| **對象會發佈到Experience Platform的新「對象」區段** | 從Customer Journey Analytics發佈的對象現在可在Experience Platform的新「對象」區段中取得。 之前，從Customer Journey Analytics發佈的對象可在Platform的「區段」區段下使用。 這項改善可提供下列優點：<ul><li>對象在Platform中出現前不再有1小時的延遲；發佈後幾秒鐘即可使用。</li><li>在Platform中，可以使用「來源」欄來排序對象，該欄會顯示對象最初發佈來源的應用程式。</li><li>Platform中的篩選和排序選項可讓您更快地找到相關對象。</li></ul>如需詳細資訊，請參閱區段 [在Experience Platform中使用Customer Journey Analytics對象](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#audiences-aep). |  | 2024 年 4 月 |
| **Experience Edge 機器人偵測** | [機器人偵測](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html)可讓您將 Web SDK、Mobile SDK 和伺服器 API 產生的事件識別為由已知編目程式和機器人產生。 | | 2024 年 4 月 29 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-340429； AN-341544； AN-341974； AN-342176； AN-342391

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **更新了資料視圖和連線 UI 中的連結** | 15 年 2 月 | Adobe 計劃於三月初更新以下 Customer Journey Analytics 產品使用者介面中的連結。請據以更新您的書籤。<ul><li>**資料視圖頁面，資料視圖管理器**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**建立新資料視圖**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**編輯資料視圖**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新連結](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**連線管理器**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**連線資訊**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**編輯連線**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**建立新連線**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adobe API 物件會員新增 | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。此類新增對於您的實施來說應該是非破壞性的變更。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |

{style="table-layout:auto"}

## 相關資源

* [2023 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
