---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1534b628841a5b4588379b944822073f3288d710
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 93%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2024 年 6 月)

**上次更新日期**：2024 年 6 月 18 日

這些發行說明涵蓋的發行期間為 2024 年 6 月 6 日至 7 月。Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **適用於 Customer Journey Analytics 的 AI 助理** | 允許您在 Customer Journey Analytics UI 中提出自然語言的問題，並根據 Customer Journey Analytics 文件獲得答案。[了解更多](/help/ai-assistant.md) | | 2024 年 6 月 6 日 |
| **圖表式銜接** | 透過圖表式拼接，您可以使用Experience Platform身分服務中的身分圖表，透過以下方式取得客戶歷程的更好檢視：<ul><li>無需擷取、轉換並載入額外資料來反映單一識別碼，即可連接不同識別碼的資料集。</li><li>在資料集之間共用身分，以提高單一資料集的首選或黃金身分涵蓋範圍。</li><li>讓 Real-Time Customer Data Platform 和 Journey Optimizer 中建立的輪廓與 Customer Journey Analytics 中的人員保持一致。</li></ul>[了解更多](/help/stitching/overview.md) |  | 2024 年 6 月 28 日 |
| **人員到帳戶的 B2B 方案轉換** | 您可以轉換 B2B 查詢資料集，以支援基於人員的 B2B 資料查詢 (包括帳戶、商機、行銷名單和行銷活動)。此轉換僅適用於基於下列類別的 B2B 查詢結構描述資料集：<ul><li>XDM 商業帳戶個人關係</li><li>XDM 商業機會個人關係</li><li>XDM 業務行銷清單會員</li><li>XDM 商業活動會員</li></ul>[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024 年 6 月 5 日 |
| **衍生欄位 - 數學函數** | 讓您在資料視圖中執行簡單的數學運算子，以便回答有關使用者的問題。例如，您可以合併產品、保固和運送等營收。[了解更多](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 2024 年 6 月 5 日 |
| **衍生欄位 -「下一個」或「上一個」函數** | 讓您查看下一個或上一個值為何。例如，在選定的行銷管道之前，用戶與哪些行銷管道有過互動？或者，在選定頁面之前或之後，用戶與哪個頁面有過互動？使用者在進店前互動最熱門的頻道為何？ [了解更多](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 2024 年 6 月 12 日 |
| **衍生欄位 — 摘要函式** | 提供在事件、工作階段和使用者層級上，為量度或維度套用彙總類型函數的能力。[了解更多](/help/data-views/derived-fields/derived-fields.md#summarize) | | 2024 年 6 月 26 日 |
| **衍生欄位 -「重複資料刪除 - 兩次」功能** | 有助於防止重複計算某個值。可以在使用者或工作階段層級套用，或基於維度的唯一值套用。(文件連結待補充) |  | 2024年7月10日 |
| **擷取優先順序和延遲** | 現在，您可以在 90 分鐘內 (SLT)，擷取 24 小時、48 小時或 7 天內的 Customer Journey Analytics 事件資料。請注意，此功能的內容將根據貴公司購買的 SKU 封裝而有所不同。<ul><li>CJA Priority Ingestion Basic：在 90 分鐘 (SLT) 內，處理 24 小時內的資料 (適用於 CJA Foundation 和 CJA Select)</li><li>CJA Priority Ingestion Intermediate：在 90 分鐘 (SLT) 內，處理 72 小時內的資料 (適用於 CJA Prime)</li><li>CJA Priority Ingestion Advanced：在 90 分鐘 (SLT) 內，處理 1 週內的資料 (適用於 CJA Ultimate)</li></ul> |  | 2024 年 6 月 12 日 |
| **共用帳戶和位置 (用於匯出和匯入)** | 使用者現在可以將其建立的帳戶和位置提供給組織中的所有使用者。只有帳戶和位置擁有者以及系統管理員，才能編輯和刪除帳戶與位置。先前，帳戶和位置只能由建立它們的使用者使用。這些設定可於使用者[設定雲端匯出帳戶](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)及[設定雲端匯出位置](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)時使用。 | 2024 年 6 月 12 日 | 2024年7月中旬 |
| **在下拉篩選器中選擇多個欄位** | 當多個欄位新增至下拉篩選器時，使用者便可以一次選擇多個欄位。此面板經過篩選，以包含任何已選取的欄位。 <p>先前，使用者在下拉篩選器中一次只能選擇一個欄位。</p><p>在下拉式篩選器上按一下滑鼠右鍵時，要求在下拉式篩選器中進行選取的選項已移至選單中。</p><p>先前，使用者可以點選下拉式選單中「無篩選器」選項旁邊的 (x)。</p><p>如需詳細資訊，請參閱[面板概觀](/help/analysis-workspace/c-panels/panels.md)中的[靜態下拉式篩選器](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters)。</p><p>[觀看此功能的影片示範](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 2024 年 6 月 19 日 |
| **Workspace 專案的目錄** | 現在可為專案提供新的目錄。目錄提供的連結可讓使用者在專案中的面板和視覺化內容之間快速切換。 <p>所有專案的左側邊欄皆提供目錄。</p><p>如需詳細資訊，請參閱[專案目錄](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)。</p><p>[觀看此功能的影片示範](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 2024 年 6 月 19 日 |
| **為自由格式表格中的維度項目建立超連結** | 您可以為一個或多個維度項目建立超連結，以使這些在 Analysis Workspace 的自由格式表格中成為可點選項目。 <p>您可以為具有 URL 值的維度項目建立超連結，也可以為具有非 URL 值的維度項目建立自訂 URL。</p><p>您可以使用變數，為多個維度項目建立動態自訂 URL。變數可以參考維度項目的值，也可以參考劃分維度。</p><p>如需詳細資訊，請參閱[為自由格式表格中的維度建立超連結](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。</p><p>[觀看此功能的影片示範](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 2024 年 6 月 19 日 |
| **搭配使用 Customer Journey Analytics 資料視圖與 Adobe Journey Optimizer** | 您可以使用 Customer Journey Analytics 中最新的設定選項，指定與 Adobe Journey Optimizer 搭配使用的 Customer Journey Analytics 資料視圖，以免除手動設定的麻煩。 <p>如需有關如何啟用此設定選項的資訊，請參閱「[建立或編輯資料視圖](/help/data-views/create-dataview.md)」中的「[相容性](/help/data-views/create-dataview.md#compatibility)」部分。</p><p>先前在 Customer Journey Analytics 中查看 Journey Optimizer 資料時，您必須手動設定連線和資料視圖。</p> |  | 2024 年 6 月 19 日 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform 中的篩選和排序選項可讓您更快找到相關的對象。</li></ul> <p>(文件連結待補充)</p> |  | 2024 年 7 月 14 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-345454、AN-349816、AN-349905、AN-350617

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
