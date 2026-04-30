---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 852bafc87c377ba1abb511574eef497c8829e132
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 66%

---

# 最新的 Customer Journey Analytics 發行說明 (2026 年 4 月)

**上次更新日期**： 2026年4月22日

這些發行說明涵蓋 2026 年 4 月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **支援義大利文**<br/> Customer Journey Analytics 的 Analysis Workspace 現已支援義大利文地區設定 (it-IT)。 <p>Customer Journey Analytics 支援 Experience Platform 使用者介面所支援的所有語言，如 [Experience Platform 使用者介面瀏覽器和語言支援](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)中所述。</p><p>您可以在 Experience Platform 中[變更您的預設語言](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)。</p> | | 2026 年 4 月 8 日 |
| **Adobe 工程 AI 代理中的資料驗證**<br/>Data Engineering 代理內提供新的資料驗證技能。 透過這些技能，在 Customer Journey Analytics 開始分析資料之前，團隊可以直接於 Adobe Experience Platform 快速評估數據品質。 <p>資料驗證技能支援隨需、欄位層級和資料集層級的驗證，將統計資料摘要與偵測無效或異常值的智慧功能結合。 </p><p>使用資料驗證技能可以減少手動 QA 工作量，並加速整個資料工程工作流程的可信任資料上線與轉換作業。</p><p>(文件連結待補充。)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年5月 <p>(原計劃於 2026 年 3 月 31 日發行)</p> |
| **適用於Customer Journey Analytics的MCP伺服器** <br/>Analytics MCP （模型內容通訊協定）伺服器可讓您將支援的MCP使用者端連線至Adobe Customer Journey Analytics。 在連線之後，您的MCP使用者端可以叫用產品特定工具來擷取資料、執行查詢，或執行支援的作業作為LLM或代理工作流程的一部分。 如需詳細資訊，請參閱[Analytics MCP伺服器](https://developer.adobe.com/analytics-mcp/docs/)。<p>如果您在Beta版使用這些MCP伺服器，請注意，Beta版和生產端點之間有不同的URL。 請確定在5月31日之前建立的任何代理工作流程均已更新為使用生產端點。</p> | | 2026年4月29日 |
| **原生行動應用程式體驗的Content Analytics支援**<br/>&#x200B;組織可將其內容效能分析延伸至iOS和Android應用程式，擷取影像資產和精細的體驗元素，以瞭解哪些應用程式內內容可促進使用者參與和業務成果。<p>所有Adobe Content Analytics客戶皆可使用深入分析。</p> | 2026年5月6日 | 待定 |
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |
| **多維度 API 報告**<br/>&#x200B;在單一 API 請求中報告多個維度並執行維度層級搜尋。 [了解更多](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026 年 3 月 |
| **多欄 API 排序**<br/>&#x200B;針對 API 請求中多個維度和量度物件進行排序。 在同一個排序定義中混合維度和量度。 [了解更多](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026 年 3 月 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-442813、AN-442410、AN-442231、AN-441943、AN-441717、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**元件**：
**連線**： AN-442824、AN-440937、AN-440092、AN-429781
**Content Analytics**：
**引導式分析**：
**匯出**：
**資料檢視**： AN-442809、AN-434824、AN-434210、AN-424000
**實作**：
**Report Builder**： AN-441136、AN-438147、AN-425150
**報告**： AN-443900、AN-441811、AN-441506、AN-440919、AN-440545、AN-440505、AN-440300
**分段**：
**排程報告**：
**共用的量度和維度**：
**其他**： AN-423359、AN-406242、AN-397985

## 相關資源

* [2025 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2025.md)
* [Adobe Analytics發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
