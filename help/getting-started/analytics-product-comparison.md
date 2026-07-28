---
title: Customer Journey Analytics產品比較
description: 比較Journey Analytics報告和匯出工具的客戶屬性，例如Analysis Workspace、Report Builder、完整表格匯出、資料摘要、API和MCP。
keywords: 點按資料流；資料摘要；資料摘要；產品比較；Analysis Workspace；Report Builder；完整表格匯出
feature: Components
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Analytics產品比較

使用此頁面來比較關鍵屬性的Customer Journey Analytics報告和匯出工具，協助您根據分析或資料匯出需求選擇合適的工具。

| 產品名稱和說明連結 | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [完整表格匯出](/help/analysis-workspace/export/export-cloud.md) | [資料摘要](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP | BI 擴充功能 | 同事 |
|---|---|---|---|---|---|---|---|---|
| **存取方法** | 瀏覽器 | Microsoft Excel | 瀏覽器 | 透過瀏覽器進行設定 | RESTful API工具 | 與MCP相容的工具 | BI 工具 | 與MCP相容的工具 |
| **資料顆粒度** | 彙總 | 彙總 | 彙總 | 事件 | 彙總 | 彙總 | 彙總 | 彙總 |
| **可用 Experience Cloud ID (ECID)** | 否 | 否 | 無 | 是 | 無 | 否 | 否 | 否 |
| **可用時間戳記** | 否 | 否 | 無 | 是 | 無 | 否 | 否 | 否 |
| **處理層級** | 完整處理 | 完整處理，並提供個別的即時報表 | 完整處理 | 完整處理 | 完整處理 | 完整處理 | 完整處理 | 完整處理 |
| **套用機器人篩選的位置** | 在[資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/bot-detection)和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)內 | 在[資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/bot-detection)和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)內 | 在[資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/bot-detection)和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)內 | 在[資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/bot-detection)和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)內 |  |  | 在[資料串流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/bot-detection)和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)內 | |
| **可見列限制 (分頁前)** | 400 | 50,000 | 限制為 300 萬列、3,000 萬列、1.5 億列或 3 億列，視等級而定 | 相依於階層 | 50,000 | 50,000 | 50,000 | 50,000 |
| **多個資料檢視** | 可以，一個專案可以包含來自多個資料檢視的資料 | 可以，一個專案可以包含來自多個資料檢視的資料 | 否，匯出只能包含來自一個資料檢視的資料 | 否，匯出只能包含來自一個資料檢視的資料 | 否，每個查詢只能參考一個資料檢視 | 否，每個查詢只能參考一個資料檢視 | 否，每個查詢只能參考一個資料檢視 | 是，如果使用者提示 |
| **維度資料行數目** | 最多5個 | ? | 最多10 | 無限制 | 最多5個 | ? | ? | ? |
| **量度資料行數目** | ? | ? | 最多10 | 無限制 | ? | ? | ? | ? |
| **區段** <br> [了解更多](/help/components/segments/seg-overview.md) | 是 | 是 | 是 | 是，且具有[限制](/help/components/exports/cja-data-feeds/df-segmentation.md) | 是 | 是 | 是 | 是 |
| **計算量度** <br> [了解更多](/help/components/calc-metrics/calc-metr-overview.md) | 是 | 是 | 是，且具有[限制](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | 無 | 是 | 是 | 是 | 是 |
| **衍生欄位** <br> [了解更多](/help/data-views/derived-fields/derived-fields.md) | 是 | 是 | 是 | 是 | 是 | 是 | 是 | 是 |
| **歸因** <br> [了解更多](/help/analysis-workspace/attribution/overview.md) | 是 | 有限 | 是，且具有[限制](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | 無 | 是 | 是 | 是 | 是 |
| **排程傳送** | 是 | 是 | 是 | 是 | — | — | — | — |
| **傳送目的地** | 電子郵件 | 電子郵件 | Amazon S3、Azure RBAC、Azure SAS、GCP | Amazon S3、Azure RBAC、Azure SAS、GCP | — | — | — | — |

{style="table-layout:auto"}
