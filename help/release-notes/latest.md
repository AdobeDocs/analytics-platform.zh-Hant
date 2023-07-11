---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新Customer Journey Analytics發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e9d2bfb4f4c4aa3ac96d0300e537376a1ef7821a
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 39%

---

# 最新Adobe Customer Journey Analytics發行說明（2023年7月）

**上次更新日期**：2023 年 7 月 10 日

Adobe Customer Journey Analytics發行版本會在 [持續傳遞模式](releases.md) 可讓您以更可擴充、分階段的方法部署功能。 因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | 新的專案型別可讓產品團隊快速自助滿足其資料需求，以便他們做出更多資料導向的產品決策。 這是以Customer Journey Analytics中現有的連線和資料檢視工作流程為基礎所建立。 不需要進行實作或設定變更。 [了解更多](/help/guided-analysis/overview.md)<p>Product Analytics是Customer Journey Analytics的付費附加元件。 如果您的組織想要布建以使用此功能，請聯絡您的Adobe客戶團隊。 | 不適用 | 2023 年 7 月 17 日 |
| **衍生欄位** | 這代表衍生欄位的初始版本。衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。您可以在資料檢視中進一步將衍生欄位定義為元件（量度或維度），然後在工作區中將衍生欄位用作元件。<p>此版本支援行銷管道範本和以下功能：</p><ul><li>串連</li><li>情況</li><li>尋找和取代</li><li>查詢</li><li>URL 剖析</li></ul> <p>[了解更多](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 8 月 2 日 |
| **擴充設定檔和查詢資料的查詢支援** | 提供將資料集新增為設定檔或查詢資料集中欄位查詢的功能。 先前僅支援事件資料集。 [了解更多] | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **Report Builder增強功能** | <ul><li>從儲存格篩選多個資料區塊。 您可以變更儲存格中多個資料區塊上的篩選器。 使用預先定義的儲存格，將其指派給多個資料區塊，並根據儲存格中定義的篩選器更新資料。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>顯示和隱藏列與欄標題。 您可以顯示或隱藏資料區塊表格標頭或列與欄標頭，以重新格式化表格並在報表中對齊資料區塊。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | 不適用 | 2023 年 7 月 19 日 |
| **體驗 Edge 地理位置查詢** | Adobe Experience Edge新增地理查詢服務，為所有Experience Edge使用者(Adobe Analytics、Customer Journey Analytics、Adobe Target、Adobe Medium Analytics、Adobe Experience Platform等)提供統一的地理資料。 | 不適用 | 2023 年 7 月 26 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-317971； AN-319234； AN-320439； AN-320519； AN-321740； AN-322444； AN-323116

## 給Customer Journey Analytics管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **變更Customer Journey Analytics處理資料的方式** | 2023 年 6 月 22 日 | 我們最近變更了處理Customer Journey Analytics中資料的方式。<ul><li>任何時間戳記少於24小時的事件資料都會串流進來。</li><li>任何時間戳記超過24小時前的事件資料（即使與較新資料位於相同批次中）都會被視為回填，並將以較低的優先順序擷取。</li></ul> |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用AdobeIO JWT憑證的Adobe Analytics API、Customer Journey Analytics API和Livestream客戶必須移轉至AdobeIO OAuth伺服器對伺服器憑證，方法是 **2025年1月1日**. 從 2024 年 5 月 1 日開始，Adobe I/O 即不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 相關資源

* [2023年舊版Customer Journey Analytics發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
