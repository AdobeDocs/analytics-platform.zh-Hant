---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2dab438b956513eaff3f05d2ff8de2fff43d9977
workflow-type: ht
source-wordcount: '571'
ht-degree: 100%

---

# 最新的 Adobe Customer Journey Analytics 版本注意事項 (2023 年 8 月)

**最後更新**：2023 年 8 月 9 日

這些版本注意事項涵蓋 2023 年 8 月 9 日至 9 月 13 日的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder 改良功能** | <ul><li>從「歷史記錄」標籤下載已排程任務；您可以在該處檢視已排程任務的歷史記錄。從該任務下載活頁簿。 </li><li>以開始日期作為維度：可讓使用者將資料區塊的開始日期顯示為資料區塊輸出中的維度。 </li></ul> | 不適用 | 2023 年 8 月 17 日 |
| **貨幣轉換** | Customer Journey 增加了支援多種貨幣的功能。您可以在資料檢視設定中轉換貨幣。[了解更多](/help/data-views/component-settings/format.md) | 不適用 | 2023 年 8 月 31 日 |
| **支援 Analytics Source Connector 的 A4T 分類** | 我們新增了關聯 ID，以便輕鬆加入 Adobe Target 活動和體驗事件的分類資料。 | 不適用 | 2023 年 8 月 31 日 |
| **報告活動管理員** | 讓管理員可以詳細瞭解每個連線的報告使用量，以便在尖峰報告期間輕鬆診斷並修正容量問題。 | 不適用 | 2023 年 9 月 6 日 |
| **PowerBI 和 Tableau 可存取 Customer Journey Analytics 資料檢視** | Adobe Customer Journey Analytics SQL 連接器可讓 SQL 存取您在 Customer Journey Analytics 中已定義的資料檢視。比較熟悉 Power BI、Tableau 或其他企業情報和視覺化工具的資料工程師與分析師，現在可以根據 Customer Journey Analytics 使用者用於其 Analysis Workspace 專案的相同資料檢視來建立報告和儀表板。[了解更多](/help/data-views/sql-connector.md) | 不適用 | 2023 年 9 月 13 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-309141、AN-319198、AN-324576、AN-324939、AN-325138、AN-325554

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
