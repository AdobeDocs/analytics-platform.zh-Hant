---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4e41bda273f0f7e93941bb00b55bffc6b357ac1f
workflow-type: ht
source-wordcount: '524'
ht-degree: 100%

---

# 最新 Customer Journey Analytics (CJA) 發行說明 (2023 年 2 月)

**上次更新日期**：2023 年 2 月 23 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 主要功能和更新

| 功能 | 說明 | [開始推出](/help/release-notes/releases.md) | [全面發佈](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **更新 CJA 對象** | 在您建立對象後，Adobe 會為每個新的 CJA 對象建立一個 Experience Platform 串流區段。 只有在組織設定為串流分段時，串流區段才會建立。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created) | 不適用 | 2023 年 2 月 3 日 |
| **在 Mobile 計分卡中隱藏比較日期範圍** | 您現在使用 Mobile 計分卡，就可以隱藏比較日期範圍。 | 不適用 | 2023 年 2 月 8 日 |
| **Workspace 中的行事曆更新** | <ul><li>錨點面板日期：您可以使日期範圍元件相對於面板行事曆。 [了解更多](/help/components/date-ranges/calendar.md)</li><li>行事曆樣式更新：整個 UI 的行事曆樣式已升級，展現更為一致易用的工作流程。</li><li>行事曆公式更新：如果您使用相對日期，所有行事曆公式將反映面板日期範圍的開始。 [了解更多](/help/components/date-ranges/calendar.md)</li></ul> | 不適用 | 2023 年 2 月 8 日 |
| **面板日期範圍更新** | 在 Workspace 中，我們新增了以下改善：<ul><li>從 2 月版開始，元件和資料預覽將依據面板日期範圍顯示，而不是過去 90 天。 </li><li>左側邊欄中列出的所有元件都將根據面板日期範圍提供。</li><li>區段和計算量度產生器中的所有日期預覽都將依據面板日期範圍 (除非從沒有關聯面板的元件管理員存取，則仍將依據過去 90 天) 顯示。</li><li>任何資料預覽都將依據面板日期範圍顯示資料或元件。</li></ul> | 不適用 | 2023 年 2 月 8 日 |
| **Adobe Analytics Source Connector 串流傳輸的行/列篩選** | Adobe Experience Platform 中的 Analytics Source Connector 現在允許篩選 Analytics 資料；這類資料是用來在[即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)中填入設定檔。<p>列層級篩選有助減少與設定檔有關聯的事件數量。 行層級篩選有助減少事件本身的豐富度，進而讓您可最佳化設定檔權利的使用。這項篩選僅適用於傳送至即時客戶設定檔和[身份服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)的資料。<p>**篩選不會影響傳送到資料湖的資料；這類資料是供 Customer Journey Analytics** 等應用程式使用。 [了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant#filtering-for-profile) | 不適用 | 已重新排程至 2023 年 3 月 29 日 |

{style=&quot;table-layout:auto&quot;}

## Customer Journey Analytics 中的修正

AN-309106

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 目前沒有通知 | 不適用 | 不適用 |

{style=&quot;table-layout:auto&quot;}

## 相關資源

* [2023 年舊版 CJA 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
