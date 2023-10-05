---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 49d91b513abd545ea73c7867817cd8724b460be4
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 51%

---

# 目前的Adobe Customer Journey Analytics發行說明（2023年10月）

**上次更新日期**：2023 年 10 月 4 日

這些發行說明涵蓋2023年10月4日至2023年10月24日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **將完整的表格匯出至雲端** | 「Customer Journey Analytics完整表格匯出」可讓您將數百萬個Workspace列匯出至雲端目的地。 <p>匯出完整表格可提供在工作區中設計之資料表格的一次性或排程傳送，且最多可支援五個劃分、五個量度、篩選器和計算量度，而所有這些全都可在串連表格中完成。 這是Adobe Analytics中Data Warehouse報表的演化，其中包含許多經常要求的新功能，目前在Data Warehouse中尚未提供。</p><p> 雲端匯出選項包括：</p><ul><li>Adobe Experience Platform Data Landing Zone</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>如需詳細資訊，請參閱 [將Customer Journey Analytics報表匯出至雲端](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 2023 年 10 月 4 日 | 2023 年 10 月 19 日 |
| **管理元件時可使用新的欄位** | 現在起，管理元件時可在[計算量度管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html)和[篩選器管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html)中使用以下新欄位：<ul><li>使用於</li><li>上次使用</li></ul>此資訊可協助您判斷某個元件對組織中的使用者是否有價值、其使用之處，以及是否需要刪除或修改。您可以將資料字典與此資訊搭配使用，以協助追蹤並深入了解元件在組織中的使用情況。 | 2023 年 9 月 23 日 | 2023 年 10 月 4 日 |
| **將Adobe Analytics專案及任何包含的元件移轉至Customer Journey Analytics** | 您現在可以將Adobe Analytics專案移轉至Customer Journey Analytics。 此程式可簡化從Adobe Analytics到Customer Journey Analytics的轉換。 <p>將專案移轉至Customer Journey Analytics時，資產會從Adobe Analytics報表套裝對應至Customer Journey Analytics資料檢視。</p> <p>您可以從Adobe Analytics介面將專案移轉至Customer Journey Analytics。 [了解更多](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | 不適用 | 2023 年 10 月 9 日 |
| **Adobe Product Analytics：顯示/隱藏數列** | 按一下圖表圖例或表格列，即可控制視覺效果中序列的可見度。  [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=en) | 不適用 | 2023 年 10 月 4 日 |
| **Adobe Product Analytics中的註解** | 引導式分析現在支援檢視在Customer Journey Analytics中建立的註解的功能。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en) | 不適用 | 2023 年 10 月 4 日 |
| **報表活動管理員** | 報告活動管理器可讓您檢視組織中每個連線的報告容量。 它為管理員提供了報告消耗的詳細可見度，以便在尖峰報告期間輕鬆診斷和修復容量問題。 報告活動管理員的主要功能包括：<ul><li>取消目前的報告請求（包括引導式分析和完整表格匯出的請求）</li><li>限制已定義時段的後續請求</li></ul>除了取消目前的請求之外，管理員現在還可以限制已定義時段內的請求。 管理員可依請求、專案或使用者限制請求。  了解更多 (即將推出) | 2023 年 10 月 17 日 | 2023 年 10 月 23 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-325940； AN-326468； AN-328301； AN-328640； AN-329370

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | 不適用 | 不適用 |

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
