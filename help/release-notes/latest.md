---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 29c124da55842bcb9085059a9008f7a7d6baf44e
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 43%

---

# 最新Adobe Customer Journey Analytics發行說明（2024年2月）

**上次更新**：2024年2月14日

這些發行說明涵蓋2024年2月14日到2024年3月11日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **時間序列預測** | [預測](../analysis-workspace/c-forecast/forecasting.md) 是新的Analysis Workspace功能，可用來預測自由表格和折線圖的標準或計算量度以及任何支援的時間詳細程度（每小時、每日、每週、每月及每年）。 | 2024 年 1 月 31 日 | 2024 年 2 月 21 日 |
| **Media Analytics報表 — 平均每分鐘觀眾數(AMA)** | 「平均每分鐘觀眾數」面板現在可在CJA中使用。 Media Analytics客戶可以使用「平均每分鐘觀眾數」面板來更瞭解其內容的平均使用量。 「平均每分鐘觀眾數」可比較任何長度或類型的節目。 此外，觀眾也可以比較這個數位「平均每分鐘觀眾數」，或是將其附加到線性電視的平均每分鐘指標。此面板提供較大的彈性來測量自訂時段的平均觀眾數，以及事後更新了持續時間分類時的平均觀眾數。 |  | 2024年2月16日 |
| **查閱和設定檔資料的列計數量度** | 資料集的列計數量度，已設定為連線的一部分，現在包含從設定檔和查詢資料集中新增、略過或刪除的記錄。 |  | 2024年2月14日 |
| **體驗邊緣機器人偵測** | [機器人偵測](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) 可讓您將Web SDK、Mobile SDK和伺服器API產生的事件識別為已知編目程式和機器人產生的事件。 | | 2024 年 2 月 21 日 |
| **使用量度** | 使用量度介面會顯示所有連線中擷取和可報告資料列的使用情形。 此介面可讓您確定您的Customer Journey Analytics使用方式是否符合合約所同意的內容。 | 2024年2月20日 | 2024年3月初 |
| **Adobe Product Analytics：與任何人共用** | 可讓您與沒有Adobe Product Analytics存取許可權的人共用指向Product Analytics專案的唯讀連結。 |  | 2024 年 2 月 21 日 |
| **Adobe Product Analytics：套用計算量度** | 您現在可以存取在Analysis Workspace中建立的計算量度，或在「趨勢：使用情況」檢視中存取計算量度產生器，讓您能夠分析一段時間內的量度趨勢並加以比較。 |  | 2024年2月16日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-333172、AN-336887、AN-337402、AN-337593、AN-338482、AN-338684、AN-339883、AN-340200

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| Adobe API 物件會員新增 | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。此類新增對於您的實施來說應該是非破壞性的變更。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |

{style="table-layout:auto"}

## 相關資源

* [2023 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
