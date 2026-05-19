---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 373deaea2b7d73484a3983bde490a86e950c2c0e
workflow-type: tm+mt
source-wordcount: 818
ht-degree: 45%

---

# 最新Customer Journey Analytics發行說明（2026年5月）

**上次更新日期**：2026年5月13日

這些發行說明涵蓋2026年5月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **CJA API Postman集合** <br/>可下載的Postman集合可用於呼叫CJA API端點。<p>如需詳細資訊，請參閱[analytics-cja-postman-collections Github存放庫](https://github.com/AdobeDocs/analytics-cja-postman-collections)。  </p> | | 2026年5月1日 |
| **適用於Customer Journey Analytics的MCP伺服器** <br/>Analytics MCP （模型內容通訊協定）伺服器可讓您將支援的MCP使用者端連線至Adobe Customer Journey Analytics。 在連線之後，您的MCP使用者端可以叫用產品特定工具來擷取資料、執行查詢，或執行支援的作業作為LLM或代理工作流程的一部分。 如需詳細資訊，請參閱[Analytics MCP伺服器](https://developer.adobe.com/analytics-mcp/docs/)。<p>如果您在Beta版使用這些MCP伺服器，請注意，Beta版和生產端點之間有不同的URL。 請確定在5月31日之前建立的任何代理工作流程均已更新為使用生產端點。</p> | | 2026年5月5日 |
| **原生行動應用程式體驗的Content Analytics支援**<br/>&#x200B;組織可將其內容效能分析延伸至iOS和Android應用程式，擷取影像資產和精細的體驗元素，以瞭解哪些應用程式內內容可促進使用者參與和業務成果。<p> [檔案](/help/content-analytics/content-analytics.md)已更新，以說明行動裝置頻道功能和設定。 有關[Content Analytics Mobile SDK擴充功能](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)的資訊可在[Adobe Developer](https://developer.adobe.com/)上取得。</p><p>所有Adobe Content Analytics客戶皆可使用深入分析。</p> | | 2026年5月6日 |
| **歷程畫布增強功能** <br/>歷程畫布視覺效果中提供下列增強功能： <ul><li>從歷程中排除節點[](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes)。</li><li>使用節點的流失資料來[建立區段](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow)、[趨勢](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data)、[對象](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience)和[劃分](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown)。</li></ul> | | 2026年5月18日 |
| **Adobe 工程 AI 代理中的資料驗證**<br/>Data Engineering 代理內提供新的資料驗證技能。 透過這些技能，在 Customer Journey Analytics 開始分析資料之前，團隊可以直接於 Adobe Experience Platform 快速評估數據品質。 <p>資料驗證技能支援隨需、欄位層級和資料集層級的驗證，將統計資料摘要與偵測無效或異常值的智慧功能結合。 </p><p>使用資料驗證技能可以減少手動 QA 工作量，並加速整個資料工程工作流程的可信任資料上線與轉換作業。</p><p>(文件連結待補充。)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年5月19日 <p>(原計劃於 2026 年 3 月 31 日發行)</p> |
| **Content Analytics：線條視覺化縮圖和預覽** <br/>[縮圖和預覽](/help/content-analytics/report/report.md)現在可用於Content Analytics線條視覺化中的資產和體驗。 |  | 2026年5月20日 |
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |

{style="table-layout:auto"}


## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-446522、AN-445779、AN-445759、AN-444676、AN-442813、AN-441943、AN-441717、AN-441538、AN-441123、AN-440976、AN-440952、AN-440919、AN-439797、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215、AN-、AN-
**元件**：
**連線**： AN-449652、AN-444560、AN-442824、AN-440937、AN-440092、AN-439823、AN-429781
**Content Analytics**：
**引導式分析**：
**匯出**： AN-438953、AN-437115
**資料檢視**： AN-442809
**實作**：
**Report Builder**： AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**報告**： AN-445123、AN-442231、AN-442169、AN-441811、AN-441733、AN-440505、AN-440300、AN-434824、AN-434210、AN-424000、AN-423359、AN-406242
**分段**：
**排程報告**：
**共用的量度和維度**：
**Other**： AN-449159、AN-444661、AN-443900、AN-397985

## 相關資源

* [2025 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2025.md)
* [Adobe Analytics發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [CX Enterprise發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
