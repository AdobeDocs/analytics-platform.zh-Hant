---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 806bcaa72479c3e871e12fd1c4802bac97eda439
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 100%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2025 年 1 月)

**上次更新日期**：2025 年 1 月 22 日

這些發行說明涵蓋 2024 年 10 月 23 日至 2025 年 1 月 30 日的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新連線使用體驗** | 連線中的&#x200B;**[!UICONTROL 使用]**&#x200B;索引標籤現在能為以下這些類型的可報告列數提供增強的視覺效果：核心資料、擷取資料和歷史資料。您也可以依據連線、資料集、沙箱或標記來檢視和細分使用情況資料。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | 2025 年 1 月 15 日 |
| **適用於將 Adobe Analytics 專案及其所包含的任何元件移轉至 Customer Journey Analytics 的 API** | API 現在可用於將您的 Adobe Analytics 專案及其所包含的元件移轉至 Customer Journey Analytics。專案和元件移轉之前只能透過使用者介面進行。[了解更多](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs)。從下拉式選單中選取「**CJA 移轉 API**」。 |  | 2025 年 1 月 15 日 |
| **於 Journey Optimizer 報表頁面上，使用 Customer Journey Analytics 內的自訂範本** | 您現在可以在 Adobe Journey Optimizer 中自訂新的報告介面，只要在 Customer Journey Analytics 中建立或編輯範本，然後將要在 Journey Optimizer 報告頁面上使用的範本儲存起來即可。過去，Adobe Journey Optimizer 中的新報告介面無法自訂。 <p>如需詳細資訊，請參閱[建立和管理範本](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/templates/create-templates)中的「建立範本」或者「編輯或刪除範本」。 |  | 2025 年 1 月 15 日 |
| **Analysis Workspace 中的範本** | 現在可於 Customer Journey Analytics 中使用範本。<ul><li>**預先建立範本**：有大量的預先建立範本可供選取。您可以使用這些範本，快速深入分析最常見的報告情境。預先建立範本能以原樣使用。或者，可以在專案中將範本做為起始點，然後再對其進行自訂，以更符合特定目的。[了解更多](/help/analysis-workspace/templates/use-templates.md)</li><li>**公司範本**：管理員可以建立公司範本，以符合其組織特定使用案例的需求。管理員建立的公司範本可供其組織中的使用者運用。[了解更多](/help/analysis-workspace/templates/create-templates.md)</li></ul> | 1 月 15 日 | 2025 年 1 月 30 日 |
| **產品使用情況** | 了解您的組織如何使用 Customer Journey Analytics。啟用此功能會在 Adobe Experience Platform 中建立資料集；該資料集會收集組織中使用 Analysis Workspace 的任何人資料。連線和資料視圖也會自動建立，讓您可以存取最熱門專案類型、最活躍使用者以及專案最多使用的元件等維度。[了解更多](/help/tools/product-usage/usage-overview.md) | 2024 年 10 月 23 日 | 2025 年 1 月 22 日 |
| **智慧型註解 (第 2 版)** | 智慧型註解現在可使用以下視覺效果：折線圖、長條圖、水平長條圖、甜甜圈圖、區域圖、流程圖和流失存活圖。您可以選取在展開視圖中一次顯示所有智慧型註解，也可以在逐一視圖中顯示單一智慧型註解。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 2025 年 1 月 22 日 |
| **於「引導式分析」內替專案新增引導式分析** | 讓您能夠從引導式分析中為工作區專案新增引導式分析。您也可以直接在 Analysis Workspace 中新增引導式分析。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/guided-analysis/overview) |  | 2025 年 1 月 22 日 |
| **媒體集合：Adobe 來源連接器更新新的媒體報告 XDM** | Analytics 來源連接器會自動將 Adobe Analytics 中的串流媒體資料對應至 Web SDK 所使用的相同欄位。目前，資料會對應到舊位置和新位置，但將來只會使用新位置。(文件連結待補充) |  | 2025 年 1 月 30 日 |

## Customer Journey Analytics 中的修正

警報：AN-363263；AN-364880；AN-365029；AN-365960
對象：AN-362564；AN-363254；
資料攝取：AN-362359；AN-362751
資料視圖：AN-362089；AN-365213；AN-365770；AN-366171；AN-366681
衍生欄位：AN-359711；AN-362496
匯出位置：AN-363999
全表匯出：AN-363055
報告產生器：AN-362937
工作區：AN-359012；AN-359145；AN-359914；AN-361455；AN-361934；AN-362469；AN-363460；AN-364714；AN-364918；AN-366277；


## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | | |

## 相關資源

* [2024 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2024.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
