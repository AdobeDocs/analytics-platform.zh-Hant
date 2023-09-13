---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6e94dcf003c26af5ce32544655477b1074b504b5
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 65%

---

# 目前的Adobe Customer Journey Analytics發行說明（2023年9月）

**上次更新日期**: 2023 年 9 月 7 日

這些發行說明涵蓋2023年9月13日至2023年10月3日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模型](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **支援 Analytics Source Connector 的 A4T 分類** | 支持 Adobe Analytics 新的 `correlationID` 欄位 | `_experience.decisioning.propositions.scopeDetails.correlationID` 欄位現在適用於 Adob&#x200B;&#x200B;e Analytics 來源連接器的結構描述中。此欄位是用來支持 A4T 分類，並將於 2023 年 9 月開始填入。 | | 不適用 | 2023 年 9 月 12 日 |
| **衍生欄位的更新** | 衍生欄位功能已進行下列更新：<ul><li>此 [!UICONTROL 查詢] 函式已重新命名為 [!UICONTROL 分類]，並提供其他載入CSV資料的選項。 **（2023年9月27日發行）**</li><li>定義衍生欄位時，可使用其他函式： [!UICONTROL Trim]， [!UICONTROL 小寫] 和 [!UICONTROL 查詢].</li><li>衍生欄位定義現在也支援來自的欄位 [!UICONTROL 查詢] 和 [!UICONTROL 個人資料] 資料集。</li></ul>[了解更多](/help/data-views/derived-fields/derived-fields.md) | 不適用 | 2023 年 9 月 13 日 |
| **Adobe Product Analytics中的新功能** | <ul><li>**異常偵測**：將事件與衍生自歷史趨勢的預期值比較。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**趨勢使用頻率檢視**：透過使用頻率測量功能的採用程度。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**使用者偏好設定**：設定許多使用者偏好設定，例如調色盤和數字格式。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html)</li></ul> | 不適用 | 2023 年 9 月 18 日 |
| **Experience Edge裝置查詢** | 透過Experience Platform邊緣網路啟用自動裝置型別資料收集。 此Experience Edge服務可讓Customer Journey Analytics與其他Experience Platform應用程式共同受益。 （請遵循檔案連結） | 不適用 | 2023 年 9 月 27 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-310972、AN-319509、AN-322245、AN-323411、AN-323719、AN-326101、AN-326125、AN-326888


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
