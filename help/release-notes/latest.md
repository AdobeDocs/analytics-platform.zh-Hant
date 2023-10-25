---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4a7762acbd05d6658ea7301070b5472965d1ea91
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 72%

---

# 目前的Adobe Customer Journey Analytics發行說明（2023年10/11月）


**上次更新日期**：2023 年 10 月 25 日

這些發行說明涵蓋2023年10月16日到2023年11月底的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics中「使用狀況」檢視的新功能** | 下列功能已新增至 [使用情況檢視](/help/guided-analysis/types/usage.md)：<ul><li>**趨勢線**：現在支援趨勢線。 按一下 [!UICONTROL 覆蓋] 在圖表上方以啟用它們。</li><li>**查詢劃分**：您現在可以將劃分套用至此檢視型別。 這些區段可作為查詢邊欄中的選項。</li></ul> | 不適用 | 2023 年 10 月 25 日 |
| **連線詳細資料頁面 — 略過的記錄** | 此功能可讓您深入瞭解在Customer Journey Analytics資料擷取期間略過某些記錄的原因。 可能的原因包括訪客ID過大（超過100萬筆記錄）、遺漏時間戳記和遺漏個人ID。 (請遵循文件) | 不適用 | 2023 年 10 月 25 日 |
| **CJA資料檢視API的檔案** | 請參閱 [資料檢視API](https://developer.adobe.com/cja-apis/docs/endpoints/dataviews/) 瞭解如何以程式設計方式建立、修改或刪除資料檢視。 | 不適用 | 2023 年 10 月 16 日 |
| **查詢和設定檔資料集的列計數指標** | 這些指標先前僅適用於事件資料集。 | 不適用 | 2023 年 10 月 16 日 |
| **將完整表格匯出至雲端** | 「Customer Journey Analytics 完整表格匯出」可讓您將數百萬個 Workspace 列匯出至雲端目標。 <p>匯出完整表格可提供在 Workspace 中設計之資料表格的一次性或排程傳送，最多可支援五個劃分、五個量度、篩選器和計算量度，且全部都可以在串連表格中完成。這是 Adobe Analytics 中 Data Warehouse 報告的演化，其中包含許多經常要求且目前在 Data Warehouse 中尚未提供的新功能。</p><p> 雲端匯出選項包括：</p><ul><li>Adobe Experience Platform 資料登錄區</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>如需更多資訊，請參閱[將 Customer Journey Analytics 報告匯出至雲端](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html)。 | 2023 年 10 月 4 日 | 2023 年 10 月 19 日 |
| **報告活動管理員** | 報告活動管理器可讓您查看組織中每個連線的報告產能。它為管理員提供報告使用量的詳細可見度，以便在尖峰報告期間輕鬆診斷和修正產能問題。報告活動管理員的主要功能包括：<ul><li>取消目前的報告請求 (包括引導式分析和完整表格匯出的請求)</li><li>限制已定義時段的後續請求</li></ul>除了取消目前的請求之外，管理員現在還可以限制定義時段內的請求。管理員可依據請求、專案或使用者來限制請求。[了解更多](/help/reporting-activity-manager/reporting-activity-overview.md) | 2023 年 10 月 17 日 | 2023 年 10 月 24 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-327661、AN-329282、AN-329383、AN-329808、AN-331030、AN-331087、AN-331105

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | 不適用 | 不適用 |

{style="table-layout:auto"}

## 相關資源

* [2023 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
