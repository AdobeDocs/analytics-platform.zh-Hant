---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c8b2133a55b73757c7a74e9309ff8b74df818e34
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 目前的 Customer Journey Analytics (CJA) 發行說明 (2023 年 4 月)

**上次更新日期**：2023 年 4 月 12 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 主要功能和更新

| 功能 | 說明 | [開始推出](/help/release-notes/releases.md) | [全面發佈](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Analytics Source Connector 串流傳輸的行/列篩選** | Adobe Experience Platform 中的 Analytics Source Connector 現在允許篩選 Analytics 資料；這類資料是用來在[即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)中填入設定檔。列層級篩選有助減少與設定檔有關聯的事件數量。行層級篩選有助減少事件本身的豐富度，進而讓您可最佳化設定檔權利的使用。這項篩選僅適用於傳送至即時客戶設定檔和[身份服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)的資料。**篩選不會影響傳送到資料湖的資料；這類資料是供 Customer Journey Analytics** 等應用程式使用。[了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant#filtering-for-profile) | 不適用 | 2023 年 3 月 29 日 |
| **Analysis Workspace 中的資料字典** | 資料字典可幫助使用者和管理員追蹤並深入了解在其 CJA 環境中的元件 (維度、量度)。[了解更多](/help/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 8 日 | 2023 年 3 月 29 日 |
| **專案連結共用 (不需登入) - 僅限 Private beta 存取權** | 您現在可以與無 CJA 存取權的人員共用 Analysis Workspace 專案的唯讀連結。您可以與組織外的人員或組織內未佈建 CJA 的人員共用專案連結。[了解更多](/help/analysis-workspace/curate-share/share-projects.md)<p>若要加入 Private beta，請聯絡您的 Adobe 客戶團隊。 | 2023 年 4 月 26 日 | 2023 年 6 月 |
| **Adobe產品分析 — 僅限私人測試版存取** | 2023年3月21日，Adobe推出「Adobe產品分析」，這是與跨管道資料互動以及Customer Journey Analytics深入分析的新方式。 這些新功能可讓產品團隊透過引導式分析工作流程，自行提供其產品體驗的資料和深入分析&#x200B;。 團隊可以：<ul><li>了解一段時間內使用者參與的模&#x200B;式</li><li>分析用戶群的增&#x200B;長</li><li>辨識一系列步驟中的摩擦區域&#x200B;</li><li>衡量功能發佈的影響&#x200B;</li><li>探索有意義的區段，以便在產品的終生歷程中參與及培&#x200B;養</li><li>在Analysis Workspace中開放，以便與分析人員進行更深入的分析和協作，以及執行更多操作&#x200B;!</li></ul>若您是CJA客戶，且有意加入私人測試版，請聯絡您的Adobe客戶團隊。 [了解更多](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | 不適用 | 2023 年 7 月 17 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-313118;AN-313390;AN-314135;AN-316381;AN-316811

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | 不適用 | 不適用 |

{style="table-layout:auto"}

## 相關資源

* [2023 年舊版 CJA 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
