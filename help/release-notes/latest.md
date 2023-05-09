---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1c00f3974293c9022365e69d6c1b38d79f52d872
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 32%

---

# 目前的 Customer Journey Analytics (CJA) 發行說明 (2023 年 5 月)

**上次更新日期**：2023 年 5 月 8 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 主要功能和更新

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非生產沙箱的回填** | 在非生產沙箱中建立 Analytics 來源連接器資料流時，非生產沙箱中的回填將限制為 3 個月。生產沙箱將維持 13 個月。 | 不適用 | 2023 年 4 月 26 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外部人員，或組織內未布建Adobe Analytics的人員共用。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>此功能預設為啟用，系統管理員可以停用此功能。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023年5月3日 | 2023 年 6 月 |
| **更新Analytics控制面板應用程式（行動應用程式）的首頁畫面** | 全新更新的首頁畫面可讓您在一個整合的計分卡清單中檢視所有計分卡。  如果您透過一次登入存取多個組織，組織中的所有計分卡都將可在單一清單中使用。 | 不適用 | 2023 年 5 月 10 日 |
| **衍生欄位** | 這表示衍生欄位的初始發行。 衍生欄位可讓您透過可自訂的規則產生器，即時定義（通常是複雜的）資料處理。 您可以在「資料」檢視中進一步將衍生欄位定義為元件（量度或維度），然後在工作區中將衍生欄位用作元件。<p>此版本支援行銷管道範本和下列功能：</p><ul><li>串連</li><li>情況</li><li>尋找和取代</li><li>查詢</li><li>URL 剖析</li></ul> <p>[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 10 日 | 待定 |
| **Report BuilderCJA — 從儲存格選取資料檢視** | 此功能可讓使用者從儲存格中選取資料區塊的資料檢視。 如果您建立活頁簿，且有多個資料檢視具有類似的資料建構，而且您想要能夠重複使用活頁簿多次，且有不同的資料檢視，這個方法會很實用。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不適用 | 2023年5月24日 |
| **排序Analysis Workspace中的元件** | <p>在Analysis Workspace的左側邊欄或「資料字典」中檢視元件時，現在提供新的「排序」選項。 您可以依建議（最常使用的）、字母或類別（類型）來排序元件。</p><p>過去，您只能搜尋或篩選元件。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | 不適用 | 2023 年 5 月 10 日 |
| **從自由表格中刪除包含動態維度的列** | 在Analysis Workspace的自由表格中，您現在可以使用x圖示快速刪除包含動態維度的特定列。 執行此動作時，會自動套用「不等於」篩選規則。<p>以前，刪除包含動態維度的列的唯一方式是在「篩選」對話方塊中手動建立規則。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | 不適用 | 2023 年 5 月 10 日 |
| **在面板中新增視覺效果的新按鈕** | Analysis Workspace中每個面板底部現在都有新按鈕，可讓您快速新增視覺效果。 <p>過去，將視覺效果新增至面板的唯一方法是從左側邊欄拖曳視覺效果、複製或複製現有視覺效果，或建立空白麵板。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | 不適用 | 2023 年 5 月 10 日 |
| **深層連結（行動應用程式）** | 可讓使用者傳送計分卡的連結，以直接將他們導向至應用程式中的計分卡專案。 這可讓您更輕鬆共用專案，並提升技術水準較低的受眾的參與度。 | 不適用 | 2023年5月17日 |
| **智慧型字幕** | 透過線條視覺化的自然語言摘要，讓使用者更富說故事。 | 2023年5月17日 | 2023 年 6 月 1 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-316412、AN-317105、AN-318122、AN-317353

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
