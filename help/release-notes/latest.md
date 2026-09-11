---
title: 目前的Customer Journey Analytics發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3aad257d518373812176cb123d799b83cf45520
workflow-type: tm+mt
source-wordcount: 1261
ht-degree: 20%

---

# 最新Customer Journey Analytics發行說明（2026年9月）

**上次更新日期**：2026年9月9日

以下發行說明涵蓋2026年9月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP伺服器外掛程式**<br/>&#x200B;使用適用於ChatGPT和Claude的新Customer Journey Analytics MCP伺服器外掛程式，快速存取您的資料。 <p>如需詳細資訊，請參閱[連線到ChatGPT](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt)和[連線到Claude](https://developer.adobe.com/analytics-mcp/docs/guides/claude)。</p> | 2026年9月1日 | 2026年9月1日 |
| **支援其他資料使用標籤**<br> Customer Journey Analytics現在支援資料集中元素的下列其他資料使用標籤：<ul><li>C2 — 限制協力廠商資料匯出（現已推出）</li><li>C3 — 限制可直接識別的資料組合（現在可用）</li><li>C9 — 限制資料科學（預計於8月或9月發行）</li></ul><p>如需詳細資訊，請參閱[標籤、原則和行銷動作](/help/data-views/data-governance.md)。</p> | | 2026年9月3日 |
| **同意原則篩選與報告**<br>&#x200B;您現在可以報告哪些訪客符合您的Adobe Experience Platform同意原則。 （同意原則維度和量度會新增至您連線中的資料檢視。）<p>此外，您可以在將非同意的訪客資料擷取到Customer Journey Analytics之前將其排除。</p><p>(文件連結待補充。)<!--For more information, see Consent reporting and filtering overview.--></p> | | 2026年9月 |
| **將區段限製為報表日期範圍**<br/>&#x200B;當區段包含日期範圍元件時，Workspace報表中的資料可能會超過報表日期範圍。<p>現在有新選項可用，可讓您將結果限製為報告日期範圍，而不論區段中包含的任何日期元件為何。</p><p>建立或修改頂層容器為「人員」的區段時，此選項可供使用。</p><p>如需詳細資訊，請參閱[建立區段](/help/components/segments/seg-builder.md#components)。</p> | 2026年8月26日 | 2026年9月9日 |
| **在Analysis Workspace中使用交談深入分析來分析LLM客戶體驗**<br/> Customer Journey Analytics現在將非結構化的聊天資料帶入Analysis Workspace，讓您報告屬性中發生的LLM支援瀏覽和購買體驗。<p>有了這項功能，您可以：</p><ul><li>透過Web SDK從對話式代理程式（您組織的自訂代理程式或Adobe Brand Concierge）收集提示、回應和代理程式中繼資料。</li><li>分析意圖、語調和情緒，以瞭解客戶詢問、代理商回應方式，以及客戶對其互動的感受。</li><li>使用您現有的結構、資料集和資料檢視進行大規模分析，然後在Analysis Workspace中呈現深入分析。</li><li>將代理互動連結至您更廣大的客戶歷程，讓對話與結果相互關聯，這樣您就能衡量對轉換、參與度等專案的實際影響。</li></ul><p>過去，LLM支援的體驗很難測量，而且幾乎無法連線至您現有的客戶歷程。</p><p>(文件連結待補充。)</p> | | 2026年9月22日 |
| **總母體報告**<br/>&#x200B;您現在可以分析並報告Customer Journey Analytics連線中存在的設定檔和查詢資料集中定義的實體。 該分析和報告超越了事件資料集之事件系列的時間型。 <p>此功能可啟用新類別的查詢、量度和對象定義，以反映企業客戶群的完整範圍。</p><p>(文件連結待補充。)</p> | | 2026年9月22日 |
| **每小時警示**<br/>&#x200B;您現在可以將警示的時間詳細程度設定為每小時。<p>每小時警示是針對一段時間內到達的資料。 如果資料的延遲超過一小時，較長的詳細程度可確保警報評估完整的資料。 如果您不確定資料需要多久才能送達，請洽詢資料工程師。</p>p>（請遵循檔案連結。）</p> | | 2026年9月 |
| **警示傳送嚴格遵守設定的延遲**<br/>&#x200B;現在警示會在您設定的延遲期間結束時傳送，無論指定事件範圍的資料是否完成或仍在接收中。 延遲時段之後到達的任何資料都不會包含在警報中。<p>以前，警報包括等待延遲送達資料的背景處理檢查，即使這表示警報是在設定的延遲時段後傳送。</p>p>（請遵循檔案連結。）</p> | | 2026年9月 |
| **Adobe Brand Visibility整合**<br/>&#x200B;將Adobe Brand Visibility與您組織的Customer Journey Analytics資料連結，以便測量AI驅動的探索如何轉化為實際的網站參與度和業務成果。<p>(文件連結待補充。)</p> | | 2026年9月 |
| **在CX Enterprise Coworker中升級與實作技能**<br>&#x200B;同事即將取得新技能。 這些技能有助於讓Customer Journey Analytics的升級和實作更順暢、更輕鬆：<ul><li>**實作指南技能**：產生一份量身打造的升級或實作步驟與建議清單。 然後可以使用預先定義的行動手冊將升級和實施指引轉換為同事專案。</li><li>**智慧型升級與實作檢查清單技能**：使用同事專案管理並追蹤自訂升級或實作檢查清單的實作進度、維護專案狀態、跨團隊共同作業、指派任務，以及視需要引入核准閘道。</li><li>**資料驗證技能**：確認您的實作已正確設定，且符合最佳實務。</li></ul><p>（請遵循檔案連結。）</p> | | 2026年9月30日 |

### Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-487374、AN-487119、AN-468907、AN-468810、AN-468363、AN-468096、AN-467414、AN-466986、AN-466982、AN-465073、AN-463571、AN-462373、AN-492801、AN-488821、AN-488452、AN-486517、AN-478930 468325
**元件**：
**連線**： AN-451458、AN-365942
**Content Analytics**：
**引導式分析**： AN-485600
**匯出**： AN-489161、AN-467131、AN-464746、AN-469034、AN-447252、AN-437803、AN-394444
**資料檢視**： AN-478732、AN-468836、AN-467851、AN-487651、AN-423592
**資料擷取**： AN-489829、AN-489722、AN-469451、AN-467436、AN-467049、AN-466087、AN-465049、AN-463524、AN-457433、AN-490288、AN-487500、AN-390916、AN-342311
**實作**：
**Report Builder**： AN-487486、AN-478944、AN-470036、AN-468589、AN-468436、AN-456747、AN-456700、AN-442695、AN-492330、AN-490564、AN-468293、AN-460921
**報告**： AN-479145、AN-469095、AN-468070、AN-467786、AN-456684、AN-465257、AN-422685、AN-406114、AN-356706、AN-322733
**分段**： AN-486561、AN-278260
**排程報告**： AN-479157
**共用的量度和維度**：
**對象分析**： AN-468237、AN-462553
**Other**： AN-469601、AN-462817、AN-362308、AN-349757、AN-326432、AN-326345、AN-324341、AN-309317

## 延遲的功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是排程資料上傳支援的即時內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)。</p> | 2025 年 10 月 29 日 | 待定<p>（原計畫於2025年10月29日推出）</p> |

>[!MORELIKETHIS]
>
>* [2026年Customer Journey Analytics舊版發行說明](/help/release-notes/2026.md)
>* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
>* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
>* [CX Enterprise發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
>* [Customer Journey Analytics檔案更新](/help/release-notes/doc-changes.md)

