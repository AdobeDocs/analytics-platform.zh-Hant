---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新Customer Journey Analytics發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cf11fa76503e700c07de7872b5f6c8a73b1d94d1
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 69%

---

# 目前的Adobe Customer Journey Analytics發行說明（2023年6月）

**上次更新日期**：2023 年 6 月 22 日

Adobe Customer Journey Analytics發行版本會在 [持續傳遞模式](releases.md) 可讓您以更可擴充、分階段的方法部署功能。 因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 版本重點 {#highlights}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智慧型註解** | 使用[!UICONTROL 台詞]視覺效果自然語言摘要來增強使用者的故事講述效果。[了解更多](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hant#share-public-link) <p>此功能預設為啟用，系統管理員可以停用。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=zh-Hant#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **衍生欄位** | 這代表衍生欄位的初始版本。衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。您可以在資料檢視中進一步將衍生欄位定義為元件（量度或維度），然後在工作區中將衍生欄位用作元件。<p>此版本支援行銷管道範本和以下功能：</p><ul><li>串連</li><li>情況</li><li>尋找和取代</li><li>查詢</li><li>URL 剖析</li></ul> <p>[了解更多](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 6 月 14 日 |
| **貨幣轉換支援** | 在資料檢視中將量度元件格式化時，支援貨幣轉換。 [了解更多](../data-views/component-settings/format.md#currency) | 2023 年 6 月 7 日 | 2023 年 6 月 21 日 |
| **PowerBI與Tableau存取Customer Journey Analytics資料檢視** | Adobe Customer Journey Analytics SQL Connector可讓您以SQL存取您在Customer Journey Analytics中定義的資料檢視。 更熟悉Power BI、Tableau或其他商業智慧和視覺化工具的資料工程師和分析師，現在可以根據Customer Journey Analytics使用者用於其Analysis Workspace專案的相同資料檢視，建立報告和儀表板。 [了解更多](/help/data-views/sql-connector.md) |  | 2023 年 6 月 30 日 |
| **擴大了對設定檔和查詢資料的查詢支援** | 您不僅可以將查詢資料集新增到事件資料集，還可以將查詢資料集新增到設定檔和查詢資料集。 | 2023 年 6 月 28 日 | 2023 年 7 月 12 日 |
| **體驗 Edge 地理位置查詢** | 為您的資料流啟用Adobe Experience Edge地理查閱後，您將能夠使用Customer Journey Analytics中的地理位置資料建立報表。 |  | 2023 年 7 月 26 日 |

{style="table-layout:auto"}

## 其他新功能或更新 {#other-new}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer 資料檢視** | Customer Journey Analytics管理員可以存取Customer Journey Analytics中一些額外的資料檢視，標題為「AJO資料檢視(Sandbox-name)」。 這些資料檢視可用來支援Adobe Journey Optimizer中的報表。 它們也可用來在Customer Journey Analytics中對Adobe Journey Optimizer活動執行更深入的分析。 [了解更多](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html)。 | | 2023 年 5 月 25 日 |
| **非生產沙箱的回填** | 在非生產沙箱中建立 Analytics 來源連接器資料流時，會將非生產沙箱中的回填限制為 3 個月。生產沙箱將維持 13 個月。 | 不適用 | 2023 年 4 月 26 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>此功能預設為啟用，系統管理員可以停用。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **更新 Analytics 儀表板應用程式 (行動應用程式) 的首頁** | 新更新的首頁可讓您在一個綜合計分卡清單中檢視所有計分卡。如果您一次登入可以存取多個組織，則單一清單會提供貴組織的所有計分卡。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | 不適用 | 2023 年 5 月 10 日 |
| **Customer Journey AnalyticsReport Builder — 從儲存格選取資料檢視** | 此功能可讓使用者從儲存格中選取資料區塊的資料檢視。如果您建立一個活頁簿且有多個資料結構類似的資料檢視，而且您想要多次重複使用一個活頁簿搭配不同資料檢視，這將很有幫助。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不適用 | 2023 年 5 月 24 日 |
| **已更新Customer Journey Analytics的學習頁面** | Customer Journey Analytics登陸頁面上的「學習」標籤現在包含Customer Journey Analytics的特定內容，包括著重從Adobe Analytics轉換到Customer Journey Analytics的內容。<p>「學習」標籤上還提供下列其他增強功能：</p><ul><li>改進的設計可在單次頁面上顯示更多學習內容和改進的導覽功能</li><li>根據經驗等級 (初學者、中階和進階) 量身打造學習內容的能力</li></ul><p>之前，Customer Journey Analytics中的「學習」標籤包含與Adobe Analytics中的「學習」標籤相同的資訊。</p> [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | 不適用 | 2023 年 6 月 30 日 |
| **在 Analysis Workspace 中排序元件** | <p>現在，在 Analysis Workspace 的左側邊欄或資料字典中查看元件時，可以使用新的「排序」選項。您可以按「建議」(最常用)、「字母順序」或「類別」(類型) 來排序元件。</p><p>以前，您只能搜尋或篩選元件。[了解更多](/help/components/overview.md)</p> | 不適用 | 2023 年 6 月 7 日 |
| **從自由格式表格中刪除包含動態維度的列** | 在 Analysis Workspace 的自由格式表格中，您現在可以使用 x 圖示快速刪除包含動態維度的特定列。執行時，會自動套用「永遠排除項目」篩選規則。<p>以前，想要刪除包含動態維度的列，唯一的方法是在「篩選器」對話框中手動建立規則。[了解更多](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不適用 | 2023 年 5 月 17 日 |
| **在面板中新增視覺效果的新按鈕** | 現在，Analysis Workspace 每個面板的底部都有一個新按鈕，可讓您快速新增視覺效果。 <p>以前，將視覺效果新增到面板的唯一方法是從左側邊欄拖放視覺效果、複製現有的視覺效果，或者建立空白面板。[了解更多](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不適用 | 2023 年 5 月 17 日 |
| **深度連結 (行動應用程式)** | 可讓使用者傳送計分卡連結，這些連結會直接導向應用程式中的計分卡專案。這使得共用專案和提高技術能力較低對象的參與度變得更加容易。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | 不適用 | 2023 年 5 月 17 日 |
| **智慧型註解** | 使用[!UICONTROL 台詞]視覺效果自然語言摘要來增強使用者的故事講述效果。[了解更多](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-318343；AN-319453

## 給Customer Journey Analytics管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 變更Customer Journey Analytics處理資料的方式 | 2023 年 6 月 22 日 | 我們最近變更了處理Customer Journey Analytics中資料的方式。<ul><li>任何時間戳記少於24小時的事件資料都會串流進來。</li><li>任何時間戳記超過24小時前的事件資料（即使與較新資料位於相同批次中）都會被視為回填，並將以較低的優先順序擷取。</li></ul> |

## 生命週期結束 (EOL) 重要通知 {#eol}

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
