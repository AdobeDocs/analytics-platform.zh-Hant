---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: aa7f4361b1353a86b87c36c3d08e99ddb8ffd049
workflow-type: ht
source-wordcount: '602'
ht-degree: 100%

---

# 目前的 Adobe Customer Journey Analytics 發行說明 (2023 年 ９ 月)

**上次更新日期**：2023 年 9 月 13 日

這些發行說明涵蓋 2023 年 9 月 13 日至 2023 年 10 月 3 日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **支援 Analytics Source Connector 的 A4T 分類** | `_experience.decisioning.propositions.scopeDetails.correlationID` 欄位現在適用於 Adob&#x200B;&#x200B;e Analytics 來源連接器的綱要中。此欄位是用來支持 A4T 分類，並將於 2023 年 9 月開始填入。 | | 不適用 | 2023 年 9 月 12 日 |
| **衍生欄位的更新** | 衍生欄位功能已進行了以下更新：<ul><li>「[!UICONTROL 查詢]」函數已重新命名為「[!UICONTROL 分類]」，並且有其他載入 CSV 資料的選項。 **(2023 年 9 月 27 日發行)**</li><li>定義衍生欄位時可以使用其他函數：「[!UICONTROL 修剪]」、「[!UICONTROL 小寫]」和「[!UICONTROL 查詢]」。</li><li>衍生欄位定義現在也支援來自「[!UICONTROL 查詢]」和「[!UICONTROL 設定檔]」資料集的欄位。</li></ul>[了解更多](/help/data-views/derived-fields/derived-fields.md) | 不適用 | 2023 年 9 月 13 日 |
| **Adobe Product Analytics 新功能** | <ul><li>**異常偵測**：將事件與歷史趨勢衍生的預期值進行比較。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**趨勢使用頻率視圖**：透過使用頻率來衡量您的功能的採用情況。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**使用者偏好設定**：設定多個使用者偏好設定，例如調色盤和數字格式。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html)</li></ul> | 不適用 | 2023 年 9 月 18 日 |
| **體驗 Edge 裝置查詢** | 透過 Experience Platform Edge 網路啟用自動裝置類型資料收集。 這項 Experience Edge 服務有利於 Customer Journey Analytics 以及其他 Experience Platform 應用程式。 (後續文件連結) | 不適用 | 2023 年 9 月 27 日 |
| **管理元件時可使用新的欄位** | 現在起，管理元件時可在[計算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)和[篩選器管理器](/help/components/filters/manage-filters.md)中使用以下新欄位：<ul><li>使用於</li><li>上次使用</li></ul><p>此資訊可協助您判斷某個元件對組織中的使用者是否有價值、其使用之處，以及是否需要刪除或修改。您可以將資料字典與此資訊搭配使用，以協助追蹤並深入了解元件在組織中的使用情況。</p> | 2023 年 9 月 20 日 | 2023 年 10 月 4 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-310972；AN-319509；AN-322245；AN-323411；AN-323719；AN-326101；AN-326125；AN-326888


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
