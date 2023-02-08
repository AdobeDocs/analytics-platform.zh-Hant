---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13c697331004b715271a7256c671293afb3c9b1f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 40%

---

# 最新Customer Journey Analytics(CJA)發行說明（2023年2月）

**上次更新日期**：2023 年 2 月 6 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 主要功能和更新

| 功能 | 說明 | [開始推出](/help/release-notes/releases.md) | [全面發佈](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **CJA對象更新** | 建立對象後，Adobe會為每個新CJA對象建立Experience Platform串流區段。 只有在您的組織已設定為串流細分時，才會建立串流區段。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | 不適用 | 2023年2月3日 |
| **隱藏行動計分卡中的比較日期範圍** | 使用行動計分卡，您現在可以隱藏比較日期範圍。 | 不適用 | 2023年2月8日 |
| **工作區中的日曆更新** | <ul><li>錨點面板日期：您可以建立與面板日曆相對的日期範圍元件。 [了解更多](/help/components/date-ranges/calendar.md)</li><li>日曆樣式更新：UI中的日曆樣式已升級，以呈現更一致且易於使用的工作流程。</li><li>日曆公式更新：如果您使用相對日期，所有日曆公式都會反映面板日期範圍的開始。 [了解更多](/help/components/date-ranges/calendar.md)</li></ul> | 不適用 | 2023年2月8日 |
| **Adobe Analytics Source Connector串流的列/欄篩選** | Adobe Experience Platform中的Analytics來源連接器現在允許篩選用於填入設定檔的Analytics資料 [即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant).<p>列層級篩選有助於減少與設定檔相關聯的事件數。 欄層級篩選有助於減少事件本身的豐富性，進而讓您最佳化設定檔權益的使用。 此篩選僅適用於傳送至「即時客戶設定檔」的資料，以及 [Identity服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant).<p>**篩選不會影響傳送至Data Lake以用於應用程式(例如Customer Journey Analytics)的資料**. [了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | 不適用 | 2023 年 2 月 22 日 |

{style=&quot;table-layout:auto&quot;}

## Customer Journey Analytics 中的修正

AN-309106

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 沒有當前通知 | 不適用 | 不適用 |

{style=&quot;table-layout:auto&quot;}

## 相關資源

* [2023 年舊版 CJA 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
