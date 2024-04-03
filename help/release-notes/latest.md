---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e6696dc9639e3309695a7a20427753fa629d1816
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 100%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 3 月)

**上次更新日期**：2024 年 3 月 20 日

這些發行說明涵蓋 2024 年 3 月 13 日至 2024 年 4 月的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **專案登陸頁面珼在提供新欄** | 現在，在 [Customer Journey Analytics 登陸頁面](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=zh-Hant)上檢視「專案」標籤時，會提供&#x200B;**[!UICONTROL 「上次使用」]**&#x200B;欄。 <p>這項資訊可顯示專案上次開啟的日期和時間，幫助您確定此專案對您組織中的使用者是否重要。以前，**[!UICONTROL 「上次使用」]**&#x200B;欄只適用於計算量度管理器、區段管理器以及警報管理器。</p> |  | 2024 年 3 月 13 日 |
| **使用情況量度** | [使用情況量度介面](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant)顯示所有連線中擷取和可報告的行的使用情況。此介面可讓您確定 Customer Journey Analytics 使用情況是否與合約的協議相符。 |  | 2024 年 3 月 13 日 |
| **Media Analytics 報告 - 平均每分鐘對象數 (AMA)** | CJA 現已提供「平均每分鐘對象數」面板。Media Analytics 客戶可以使用「平均每分鐘對象數」面板來更了解其內容的平均使用量。 <p>「平均每分鐘對象數」可比較任何長度或類型的節目。此外，客戶也可以比較將此「數位平均每分鐘對象數」與「線性電視平均每分鐘量度」進行比較，或是把前者附加到後者上。</p><p> 此面板提供較大的彈性來測量自訂時段的平均對象數，以及事後已更新持續時間分類時的平均對象數。</p><p>有關詳細資訊，請參閱「[媒體平均每分鐘對象數面板](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)」。</p> |  | 2024 年 3 月 12 日 |
| **對於人員到帳戶的 B2B 方案轉換** | 讓您轉換資料集，以便進一步支援 Customer Journey Analytics B2B 報告情境中基於人員的查詢。此功能可用於基於以下類別的 B2B 方案資料集：<ul><li>XDM 商業帳戶個人關係</li><li>XDM 商業機會個人關係</li><li>XDM 業務行銷清單會員</li><li>XDM 商業活動會員</li></ul> | | 2024 年 3 月 26 日 |
| **Report Builder 使用情況包含在計算量度管理器和篩選器管理器的「使用於」欄中** | 現在，在計算量度管理器或篩選器管理器中檢視「**使用於**」欄時，可以看到 Report Builder 使用情況資料。<p>之前，篩選器管理器僅提供警報、專案、已排程專案和計算量度的使用情況資料；而計算量度管理器僅提供警報、專案、已排程專案的使用情況資料。</p> |  | 7 月 |
| **Adobe Product Analytics：比較單一漏斗步驟中的事件** | 在漏斗中：摩擦視圖，現在您可以比較單一漏斗步驟內的事件。當您的歷程有步驟選項或有一個執行 A/B 實驗的步驟時，此功能尤其實用。 | 2024 年 3 月 29 日 | 2024 年 4 月 12 日 |
| **管理員可以管理其組織中的所有位置和帳戶** | 「位置」標籤 (在「元件 > 輸出」頁面上) 上的新選項可以讓管理員檢視和管理組織中的所有位置。 <p>「位置」帳戶標籤 (在「元件 > 輸出」頁面上) 上的新選項可以讓管理員檢視和管理組織中的所有帳戶。</p><p>以前，管理員只能檢視和管理他們建立的位置和帳戶。</p> | | 2024 年 4 月 |
| **對象已經發佈到 Experience Platform 中新的「對象」部分** | 現在可以在 Experience Platform 的新「對象」部分，找到從 Customer Journey Analytics 中發布的對象。以前，可以在 Platform 的「區段」部分之下找到從 Customer Journey Analytics 發佈的對象。此改善提供以下優點：<ul><li>對象出現在 Platform 之前不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Platform 中的對象進行排序，其中顯示最初發佈對象的應用程式。</li><li>Platform 中的篩選和排序選項可讓您更快速找到相關的對象。</li></ul>有關詳細資訊，請參閱「[在 Experience Platform 中使用 Customer Journey Analytics 對象](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=zh-Hant#audiences-aep)」一節。 |  | 2024 年 4 月 |
| **Experience Edge 機器人偵測** | [機器人偵測](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=zh-Hant)可讓您將 Web SDK、Mobile SDK 和伺服器 API 產生的事件識別為由已知編目程式和機器人產生。 | | 2024 年 4 月 29 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-340429；AN-341544；AN-341974；AN-342176；AN-342391

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **資料視圖和連線 UI 中的連結已更新** | 2 月 15 日 | Adobe 計劃於三月初更新以下 Customer Journey Analytics 產品使用者介面中的連結。請據以更新您的書籤。<ul><li>**資料視圖頁面，資料視圖管理器**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**建立新資料視圖**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**編輯資料視圖**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新連結](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**連線管理器**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**連線資訊**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**編輯連線**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**建立新連線**：[現有連結](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新連結](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Adobe API 物件會員新增 | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。此類新增對於您的實施來說應該是非破壞性的變更。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |

{style="table-layout:auto"}

## 相關資源

* [2023 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
