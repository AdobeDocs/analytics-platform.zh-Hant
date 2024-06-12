---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 933046a371407491b6e68749b63d48057fdf0e48
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 38%

---

# 最新Adobe Customer Journey Analytics發行說明（2024年6月）

**上次更新**：2024年6月12日

這些發行說明涵蓋2024年6月6日至2024年7月的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **適用於 Customer Journey Analytics 的 AI 助理** | 允許您在 Customer Journey Analytics UI 中提出自然語言的問題，並根據 Customer Journey Analytics 文件獲得答案。[了解更多](/help/ai-assistant.md) | | 2024 年 6 月 6 日 |
| **圖表式拚接：使用UIS圖表匯出進行拚接** | 透過圖表式拼接，您可以使用身分圖表透過以下方式取得客戶歷程的更好檢視：<ul><li>使用不同的識別碼加入資料集，而不需擷取、轉換和載入其他資料以反映單一識別碼。</li><li>跨資料集共用身分，藉此改善單一資料集的偏好或黃金身分涵蓋範圍。</li><li>將Real-time Customer Data Platform和Journey Optimizer中建立的設定檔與Customer Journey Analytics中的人員整合。</li></ul>(後續文件連結) |  | 2024年6月28日 |
| **對於人員到帳戶的 B2B 方案轉換** | 若要支援對B2B資料（包括帳戶、商機、行銷清單和行銷活動）進行以人員為基礎的查詢，您可以轉換B2B查詢資料集。 根據下列類別，此轉換僅適用於包含B2B查詢結構描述資料的資料集：<ul><li>XDM 商業帳戶個人關係</li><li>XDM 商業機會個人關係</li><li>XDM 業務行銷清單會員</li><li>XDM 商業活動會員</li></ul>[了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024 年 6 月 5 日 |
| **衍生欄位 - 數學函數** | 讓您在資料視圖中執行簡單的數學運算子，以便回答有關使用者的問題。例如，您可以合併產品、保固和運送等收入。 <p>[了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 2024 年 6 月 5 日 |
| **衍生欄位 — 下一個或上一個函式** | 讓您檢視下一個或上一個值。 例如，在選取的行銷管道之前，某人先前互動的行銷管道為何？ 或者，使用者在選取頁面之前或之後互動的頁面為何？ 使用者在進店前互動最熱門的頻道為何？ <p>[了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 2024 年 6 月 12 日 |
| **衍生欄位 — 摘要函式** | 提供在事件、工作階段和使用者層級，將彙總型別函式套用至量度或維度的功能。 (後續文件連結) | | 2024年6月26日 |
| **衍生欄位 — 重複資料刪除功能** | 協助防止重複計算值。 可在使用者或工作階段層級，或根據維度的唯一值套用。 (後續文件連結) |  | 2024年6月26日 |
| **擷取優先順序和延遲** | 您現在可以在90分鐘(SLT)內以Customer Journey Analytics擷取事件資料，無論資料是24小時、48小時還是7天前。 請注意，此功能因您公司購買的SKU套件而異：<ul><li>CJA優先擷取基本：90分鐘SLT處理內24小時前的資料（適用於CJA Foundation和CJA Select）</li><li>CJA優先擷取中繼：90分鐘SLT處理內72小時前的資料（適用於CJA Prime）</li><li>CJA優先擷取進階：90分鐘SLT處理內1週前的資料（適用於CJA Ultimate）</li></ul> |  | 2024 年 6 月 12 日 |
| **共用帳戶和位置 (用於匯出和匯入)** | 使用者現在可以將其建立的帳戶和位置提供給組織中的所有使用者。只有帳戶和位置擁有者和系統管理員可以編輯和刪除帳戶和位置。 以前，帳戶和位置只能由建立它們的使用者使用。 當使用者[設定雲端匯出帳戶](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)和[設定雲端匯出位置](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)時，可使用這些設定。 | 2024 年 6 月 12 日 | 2024年6月18日 |
| **自由表格的下拉式選單中提供多個篩選器時，請選取這些篩選器** | 當多個篩選器以下拉式選單形式新增至自由表格時，自由表格的使用者現在可以一次選取多個篩選器。 自由表格會經過篩選，加入任何選取的篩選器。 <p>過去，使用者只能在篩選器下拉式選單中一次選取一個篩選器。</p><p>（請遵循檔案連結。）<!--For more information, see "Add filters to a project" in "Use components in Analysis Workspace."--> |  | 2024年6月19日 |
| **工作區專案的目錄** | 專案現在有新的目錄可用。 目錄提供的連結可讓使用者快速跳至專案內的面板和視覺效果。 <p>目錄可為個別專案或特定使用者的所有專案啟用。</p><p>（請遵循檔案連結。）<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | 2024年6月19日 |
| **在自由表格中建立維度專案的超連結** | 您可以為一或多個維度專案建立超連結，以便在Analysis Workspace的自由格式表格內點選這些專案。 <p>您可以為具有URL值的維度專案建立超連結，或為具有非URL值的維度專案建立自訂URL。</p><p>您可以使用變數，為多個維度專案建立動態自訂URL。 變數可參考維度專案的值，也可以參考劃分維度。</p><p>（請遵循檔案連結。）<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | 2024年6月19日 |
| **對象已經發佈到 Experience Platform 中新的「對象」區段** | 現在起，從 Customer Journey Analytics 發佈的對象，可在 Adobe Experience Platform 的新「對象」區段中取得。<p>以前，從 Customer Journey Analytics 發佈的對象是在 Experience Platform 的「區段」部分下方取得。</p><p>此改善提供以下優點：</p><ul><li>對象出現在 Experience Platform 之前，不會再有 1 小時的延遲，而是在發佈之後幾秒鐘即可使用。</li><li>可以使用「來源」欄對 Experience Platform 中的對象進行排序，其中會顯示最初發佈對象的應用程式。</li><li>Experience Platform 中的篩選和排序選項可讓您更快找到相關的對象。</li></ul> <p>(後續文件連結)</p> |  | 2024年7月14日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-345454； AN-349816； AN-349905； AN-350617

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
