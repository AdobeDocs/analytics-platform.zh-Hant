---
title: 目前的Customer Journey Analytics發行說明
description: 檢視最新Customer Journey Analytics發行說明，包括目前期間的新功能、已修正問題和延遲發行。
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: c9d7bb10d15aa25bf3fa6dcd2e95fea39cd6faf7
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 27%
---
# 目前的Customer Journey Analytics發行說明（2026年10月）

**上次更新日期**：2026年10月7日

以下發行說明涵蓋2026年10月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP伺服器的唯讀許可權**<br/>&#x200B;管理員現在可以授與使用者對Customer Journey Analytics MCP伺服器的唯讀存取權。 新的[!UICONTROL MCP唯讀存取]許可權專案可讓使用者存取所有唯讀工具，而不允許他們建立專案、區段或計算量度。<p>現有的[!UICONTROL MCP存取]許可權專案已重新命名為[!UICONTROL MCP完整存取]。 具有此許可權的使用者可繼續存取所有工具，包括建立、變更或刪除元件的工具。</p><p>如需詳細資訊，請參閱Customer Journey Analytics MCP伺服器檔案中的[設定許可權](https://developer.adobe.com/analytics-mcp/docs/guides/permissions)。</p> | | 2026年10月6日 |
| **在Analysis Workspace中使用交談深入分析來分析LLM客戶體驗**<br/> Customer Journey Analytics現在將非結構化的聊天資料帶入Analysis Workspace，讓您報告屬性中發生的LLM支援瀏覽和購買體驗。<p>有了這項功能，您可以：</p><ul><li>透過Web SDK從對話式代理程式（您組織的自訂代理程式或Adobe Brand Concierge）收集提示、回應和代理程式中繼資料。</li><li>分析意圖、語調和情緒，以瞭解客戶詢問、代理商回應方式，以及客戶對其互動的感受。</li><li>使用您現有的結構、資料集和資料檢視進行大規模分析，然後在Analysis Workspace中呈現深入分析。</li><li>將代理互動連結至您更廣大的客戶歷程，讓對話與結果相互關聯，這樣您就能衡量對轉換、參與度等專案的實際影響。</li></ul><p>過去，LLM支援的體驗很難測量，而且幾乎無法連線至您現有的客戶歷程。</p><p>如需詳細資訊，請參閱[交談見解](/help/conversation-insights/overview.md)。</p> | | 2026年10月8日<p>（原計畫於2026年9月22日推出）</p> |
| **自動產生元件說明** <br/>您現在可以自動產生維度、量度、計算量度、區段和日期範圍的說明。 這可讓Workspace使用者瞭解要使用哪些元件，尤其是在擁有大型元件庫的組織中。 <p>您可以產生單一元件的說明，或同時產生許多元件的說明。</p> <p>(文件連結待補充。)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日 |
| **Adobe Brand Visibility整合**<br/>&#x200B;將Adobe Brand Visibility與您組織的Customer Journey Analytics資料連結，以便測量AI驅動的探索如何轉化為實際的網站參與度和業務成果。<p>(文件連結待補充。)</p> | | 2026年10 |


### Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-495340、AN-494789、AN-493307、AN-468900
**元件**： AN-492523
**連線**： AN-492236
**Content Analytics**：
**引導式分析**： AN-495592
**匯出**： AN-495077、AN-494337、AN-486563、AN-469919、AN-462560、AN-462372
**資料檢視**： AN-492093、AN-467770、AN-455367、AN-444467
**資料擷取**： AN-496439、AN-495339、AN-493456、AN-491984、AN-490515、AN-490479、AN-470065
**實作**：
**Report Builder**： AN-496602、AN-494224、AN-493737、AN-493508、AN-493505、AN-492806、AN-468981、AN-454376
**報告**： AN-495661、AN-493562、AN-487058、AN-478768
**細分**：
**排程報告**： AN-491103、AN-468049
**共用的量度和維度**： AN-493722
**對象分析**： AN-469101
**其他**： AN-493865

## 延遲的功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **總母體報告**<br/>&#x200B;您現在可以分析並報告Customer Journey Analytics連線中存在的設定檔和查詢資料集中定義的實體。 該分析和報告超越了事件資料集之事件系列的時間型。 <p>此功能可啟用新類別的查詢、量度和對象定義，以反映企業客戶群的完整範圍。</p><p>(文件連結待補充。)</p> | | 待定<p>（原計畫於2026年9月22日推出）</p> |
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是排程資料上傳支援的即時內容範例：</p><ul><li>FAST （免費廣告支援電視）平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)。</p> | 2025 年 10 月 29 日 | 待定<p>（原計畫於2025年10月29日推出）</p> |

>[!MORELIKETHIS]
>
>* [2026年Customer Journey Analytics舊版發行說明](/help/release-notes/2026.md)
>* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
>* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
>* [CX Enterprise發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
>* [Customer Journey Analytics檔案更新](/help/release-notes/doc-changes.md)

