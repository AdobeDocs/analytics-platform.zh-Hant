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
source-git-commit: 4dd845eaf5f101e21a8e754ac588cb837398b975
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 41%

---

# 最新Customer Journey Analytics發行說明（2026年7月）

**上次更新日期**：2026年7月8日

以下發行說明涵蓋2026年7月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **子事件分析** <br/>子事件分析可讓您在比事件層級更精細的層級分析資料。 您可以對事件中的個別容器進行分段，而不需篩選整個事件。 <p>例如，您可以將特定產品類別分段，而不納入同一訂單中購買的所有其他產品。 您也可以將屬於事件資料一部分的物件或陣列，定義為資料檢視中的個別容器。</p><p>(文件連結待補充。)</p> | 2026年7月15日 | 2026年7月底 |
| **B2B edition：支援ad hoc和關聯式資料集** <br/>Customer Journey Analytics B2B edition中以帳戶為基礎的連線現在也支援ad hoc和關聯式資料集。<p>(文件連結待補充。)</p> | | 2026年7月20日 |
| **Content Analytics：付費媒體資料** <br/>付費媒體現在可作為Content Analytics的第三個管道使用。<p>(文件連結待補充。)</p> | | 2026年7月31日 |
| **連線使用方式介面更新** <br/>在管理連線時，您現在可以在「使用方式」介面中檢視每個個別模組（例如Customer Journey Analytics或Customer Journey Analytics B2B edition）的使用方式詳細資料。 <p>此外，您現在可以依月份劃分每個模組的使用量報表。</p><p>(文件連結待補充。)</p> | | 2026年7月31日 |
| **CX Enterprise Co-worker：從Adobe Analytics移轉至Customer Journey Analytics時驗證您的資料** <br/>CX Enterprise Co-worker的一項新技能可讓您根據現有Adobe Analytics實作的資料，驗證Customer Journey Analytics實作的資料。 <p>此技能會自動視需要個別比較每個維度、量度和趨勢。 它也可以將所有Adobe Analytics報表套裝與所有Customer Journey Analytics資料檢視進行比較。 接著，該技能會產生AI導向的深入分析和建議，您可實施這些分析和建議，以利您移轉至Customer Journey Analytics。</p><p>(文件連結待補充。)</p> | | 2026年7月底 |

### Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-457527、AN-451161、AN-459034、AN-458071、AN-458398
**元件**：
**連線**： AN-457065
**Content Analytics**：
**引導式分析**：
**匯出**：
**資料檢視**： AN-453201
**資料擷取**：
**實作**：
**Report Builder**： AN-457533、AN-453683
**報告**： AN-457607、AN-447692、AN-451259、AN-455713
**細分**：
**排程報告**： AN-450715
**共用的量度和維度**：
**對象分析**：
**其他**： AN-457063

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

