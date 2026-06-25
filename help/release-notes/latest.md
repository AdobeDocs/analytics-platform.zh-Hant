---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8cdfe0db0aabba05fbebe7d9215182e0fca31d66
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 44%

---

# 最新Customer Journey Analytics發行說明（2026年6月）

**上次更新日期**：2026年6月25日

以下發行說明涵蓋2026年6月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。 因此，這些發行說明每月會更新好幾次。 請定期進行檢查。

## 新功能或更新功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **Data Mirror** <br/>[Data Mirror](/help/data-mirror/data-mirror.md)是一種Experience Platform功能，可使用關聯式結構描述，從外部資料倉儲解決方案（[!DNL Snowflake]、[!DNL Azure Databricks]和[!DNL Google BigQuery]）將資料列層級的變更擷取（變更資料擷取）到Customer Journey Analytics。 它保留資料關係、強制執行唯一性，並支援版本化，而不需要上游擷取、轉換和載入(ETL)程式。 | 2026 年 3 月 25 日 | 2026年6月17日 |
| **在AI小幫手中驗證您的資料** <br/>您可以使用AI小幫手[驗證Adobe Experience Platform資料集的資料品質](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/agents/data-validation)。 由Agent Orchestrator支援的資料驗證功能可以對資料集執行統計和語意驗證、分析資料集欄位、識別資料品質問題，並傳回自然語言摘要，其中包含可操作的深入分析。 | | 2026年6月22日 |

### Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-456858、AN-455865、AN-455706、AN-455592、AN-455484、AN-455180、AN-454999、AN-454170、AN-454145、AN-453793、AN-452921、AN-452009、AN-451958、AN-451643、AN-451600、AN-451525、AN-451477、AN-451262、AN-451161、AN-450772、AN-443594、AN-434416
**元件**：
**連線**： AN-457065、AN-453705
**Content Analytics**： AN-451203、AN-447596
**引導式分析**：
**匯出**： AN-452006、AN-451989、AN-440567
**資料檢視**： AN-451198
**實作**：
**Report Builder**： AN-440912、AN-457586、AN-457533、AN-455713、AN-455623、AN-455063、AN-454512、AN-454053、AN-453977、AN-453781、AN-453683、AN-451974、AN-451735、AN-451731、AN-451190、AN-449813、AN-447173、AN-447139、AN-446184、AN-445794、AN-445354、AN-442819
**報告**： AN-454589、AN-454517、AN-453982、AN-451822、AN-451497、AN-451463、AN-451259、AN-451215、AN-450661、AN-447699、AN-448375、AN-447692
**細分**：
**排程報告**： AN-451980、AN-451882、AN-450715
**共用的量度和維度**：
**對象分析**： AN-449656、AN-450400
**Other**： AN-457063、AN-454140、AN-453937、AN-453825、AN-452959、AN-452934、AN-452296、AN-451781、AN-450974

## 延遲的功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data) | 2025 年 10 月 29 日 | 待定<p>（原計畫於2025年10月29日推出）</p> |

>[!MORELIKETHIS]
>
>* [2026年Customer Journey Analytics舊版發行說明](/help/release-notes/2026.md)
>* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
>* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
>* [CX Enterprise發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
>* [Customer Journey Analytics檔案更新](/help/release-notes/doc-changes.md)
