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
source-git-commit: 3d3015ac59eefd5bd5e948996b2880310332a5e1
workflow-type: tm+mt
source-wordcount: 989
ht-degree: 27%

---

# 最新Customer Journey Analytics發行說明（2026年8月）

**上次更新日期**：2026年8月5日

這些發行說明涵蓋2026年8月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **歷程畫布增強功能**<br>&#x200B;現已推出下列歷程畫布增強功能：<ul><li>比較歷程與先前的時間範圍。 比較目前歷程與4週前、2季前、1年前或自訂日期範圍的歷程。</li><li>針對選取的節點，顯示在歷程中任何時間點上所選節點之後排名最前的維度專案。 當選取的節點是您分析中的關鍵事件，且您想要檢視人員之後在任何時間點做什麼，請使用此選項。<p>以前，只有頂部的緊接節點可以顯示在所選節點之前或之後。 </p></li><li>變更節點之間箭頭的形狀和樣式。 在節點之間拖曳箭頭以變更箭頭的形狀（曲率），然後按一下滑鼠右鍵以將其樣式變更為下列任一專案：實線、虛線、點狀線、虛線點或動畫。</li></ul><p></p>如需更多資訊，請參閱「[設定歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)」。 |  | 2026年8月18日 |
| **將區段限製為報表日期範圍**<br/>&#x200B;當區段包含日期範圍元件時，Workspace報表中的資料可能會超過報表日期範圍。<p>現在有新選項可用，可讓您將結果限製為報告日期範圍，而不論區段中包含的任何日期元件為何。 <p>建立或修改頂層容器為「人員」的區段時，此選項可供使用。</p><p>如需詳細資訊，請參閱[建立區段](/help/components/segments/seg-builder.md#components)。</p> | 2026年8月26日 | 2026年9月9日 |
| **支援其他資料使用標籤**<br> Customer Journey Analytics現在支援資料集中元素的下列其他資料使用標籤：<ul><li>C2 — 限制協力廠商資料匯出（現已推出）</li><li>C3 — 限制可直接識別的資料組合（現在可用）</li><li>C9 — 限制資料科學（預計於8月或9月發行）</li></ul><p>如需詳細資訊，請參閱[標籤、原則和行銷動作](/help/data-views/data-governance.md)。</p> | | 2026年8或9月 |
| **同意原則篩選與報告**<br>&#x200B;您現在可以報告哪些訪客符合您的Adobe Experience Platform同意原則。 （同意原則維度和量度會新增至您連線中的資料檢視。）<p>此外，您可以在將非同意的訪客資料擷取到Customer Journey Analytics之前將其排除。</p><p>如需詳細資訊，請參閱同意報表和篩選概觀。</p> | | 2026年8月 |
| **Content Analytics：付費媒體資料** <br/>付費媒體現在可作為Content Analytics的第三個管道使用。<p>(文件連結待補充。)</p> | | 2026年8月31日 |
| **B2B：個人對帳戶拼接**<br> B2B帳戶拼接使用帳戶資訊豐富您的事件資料集，並在Customer Journey Analytics中啟用完整客戶歷程的分析。 <p>當事件缺少帳戶ID （Customer Journey Analytics B2B edition擷取時會需要此ID）時，帳戶拼接會衍生並使用您提供的人員對帳戶對應資料集自動新增該資訊。</p><p>(文件連結待補充。)</p> | | 2026年8月底或9月 |
| **CJA報表API首次呼叫指南**<br> Adobe Customer Journey Analytics API首次呼叫指南提供設定基本報表要求的指示和範例。 | | 2026年8月10日 |
| **CJA報表API日期趨勢指南**<br> Adobe Customer Journey Analytics API日期趨勢指南提供設定基本報表要求的指示和範例。 | | 2026年8月17日 |

### Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-466867、AN-465995、AN-465315、AN-465313、AN-464375、AN-463634、AN-463248、AN-463175、AN-463049、AN-462347、AN-462124、AN-461922、AN-458398、AN-457849、AN-455002、AN-453357、AN-456863、AN-459816、AN-459034、AN-460774、AN-460671、AN-457760、AN-443594
**元件**：
**連線**： AN-464934、AN-460768
**Content Analytics**：
**引導式分析**：
**匯出**： AN-451819、AN-448419、AN-456001
**資料檢視**： AN-453201、AN-441965、AN-460967
**資料擷取**： AN-462123、AN-451836、AN-453790、AN-459000、AN-456057、AN-461271、AN-459016、AN-460935
**實作**：
**Report Builder**： AN-465346、AN-464768、AN-464580、AN-464301、AN-463048、AN-462800、AN-457042、AN-461033、AN-459042、AN-454250、AN-451735、AN-450776、AN-450200、AN-451665
**報告**： AN-463576、AN-462400、AN-456394、AN-455619、AN-459530、AN-454103、AN-452866、AN-461181
**分段**： AN-459002、AN-457730、AN-457146
**排程報告**： AN-455009、AN-460037、AN-462093
**共用的量度和維度**：
**對象分析**： AN-458292
**Other**： AN-466935、AN-462116、AN-454493、AN-457666、AN-457557、AN-456742、AN-437975、AN-460959

## 延遲的功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)。 | 2025 年 10 月 29 日 | 待定<p>（原計畫於2025年10月29日推出）</p> |

>[!MORELIKETHIS]
>
>* [2026年Customer Journey Analytics舊版發行說明](/help/release-notes/2026.md)
>* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
>* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
>* [CX Enterprise發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
>* [Customer Journey Analytics檔案更新](/help/release-notes/doc-changes.md)

