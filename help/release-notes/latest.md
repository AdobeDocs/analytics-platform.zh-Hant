---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e55cd5d9da816b9413dba7542acb385f12709642
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 100%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2023 年 7 月)

**上次更新日期**：2023 年 7 月 13 日

Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics 是一種與 Customer Journey Analytics 跨管道資料和深入見解進行互動的新方式。這些新功能使產品團隊能夠透過引導式分析工作流程取得有關其產品體驗的自助資料和深入見解。團隊可以：<ul><li>了解一段時間內使用者參與模式&#x200B;</li><li>追蹤產品使用者群的成長與保留率</li><li>識別產品中的摩擦區域</li><li>衡量功能發行與首次使用的影響&#x200B;</li><li>在整個產品生命歷程中，找到可以投入和培養的有意義使用者區間</li><li>連結 Analysis Workspace 以進行更深入的分析，以及與分析師協作</li></ul>Adobe Product Analytics 是 Customer Journey Analytics 的付費附加元件。如果您的組織想要佈建使用此功能，請聯絡您的 Adobe 客戶團隊。[了解更多](/help/guided-analysis/overview.md) | 不適用 | 2023 年 7 月 17 日 |
| **衍生欄位** | 這代表衍生欄位的初始版本。衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。您可以進一步將衍生欄位定義為資料檢視中的元件 (量度或維度)，然後使用衍生欄位做為工作區的元件。<p>此版本支援行銷管道範本和以下功能：</p><ul><li>串連</li><li>情況</li><li>尋找和取代</li><li>查詢</li><li>URL 剖析</li></ul> <p>[了解更多](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 8 月 2 日 |
| **已擴大對設定檔和查詢資料的查詢支援** | 提供功能，可將資料集新增為設定檔或查詢資料集內的欄位查詢。之前僅支援事件資料集。[了解更多](/help/connections/create-connection.md) | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **Report Builder 改良功能** | <ul><li>從儲存格篩選多個資料區塊。您可以從儲存格變更對多個資料區塊的篩選。使用預先定義的儲存格，將其分配給多個資料區塊，並根據儲存格所定義的篩選器來更新資料。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=zh-Hant)</li><li>顯示和隱藏行與欄標題。您可以顯示或隱藏資料區塊表標題，或行與欄標題，以便將表格重新格式化並對齊報告中的資料區塊。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=zh-Hant#build-the-data-block)</li></ul> | 不適用 | 2023 年 7 月 19 日 |
| **體驗 Edge 地理位置查詢** | [Adobe Experience Edge 新增了地理查詢服務，為所有的 Experience Edge 使用者 (Adobe Analytics、Customer Journey Analytics、Adobe Target、Adobe Media Analytics、Adobe Experience Platform 等) 提供統一的地理資料。](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant) | 不適用 | 2023 年 7 月 26 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-317971；AN-319234；AN-320439；AN-320519；AN-321740；AN-322444；AN-323116

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **Customer Journey Analytics 資料處理方式的變更** | 2023 年 6 月 22 日 | 我們最近變更了 Customer Journey Analytics 處理資料的方式。<ul><li>任何時間戳記不到 24 小時的事件資料都會串流進入。</li><li>任何時間戳記超過 24 小時的事件資料 (即使與較新的資料屬於同一批次) 都視為回填，並將以較低的優先順序擷取。</li></ul> |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API、Customer Journey Analytics API 和 Livestream 客戶，必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe IO 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 相關資源

* [2023 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
