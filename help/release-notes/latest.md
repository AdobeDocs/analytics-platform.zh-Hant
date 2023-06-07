---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 86b411ac28aaa78914c6f105af2716e1b3a4150c
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 67%

---

# 目前的 Customer Journey Analytics (CJA) 發行說明 (2023 年 6 月)

**上次更新日期**：2023 年 6 月 6 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 版本重點 {#highlights}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智慧型註解** | 透過的自然語言摘要，豐富使用者的敘事能力 [!UICONTROL 折線圖] 視覺效果。 [了解更多](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hant#share-public-link) <p>此功能預設為啟用，系統管理員可以停用。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=zh-Hant#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **衍生欄位** | 這代表衍生欄位的初始版本。衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。您可以進一步將衍生欄位定義為資料檢視中的元件 (量度或維度)，然後將衍生欄位用作工作區中的元件。<p>此版本支援行銷管道範本和以下功能：</p><ul><li>串連</li><li>情況</li><li>尋找和取代</li><li>查詢</li><li>URL 剖析</li></ul> <p>[了解更多](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 6 月 21 日 |
| **PowerBI與Tableau存取CJA資料檢視** | Customer Journey Analytics(CJA) SQL Connector可讓您以SQL存取您在CJA中定義的資料檢視。 更熟悉Power BI、Tableau或其他商業智慧和視覺化工具的資料工程師和分析師，現在可以根據CJA使用者在其Analysis Workspace專案中使用的相同資料檢視建立報告和儀表板。 [了解更多](/help/data-views/sql-connector.md) |  | 2023 年 6 月 30 日 |
| **Experience Edge地理查詢** | 為您的資料流啟用Experience Edge Geo Lookups後，您將能夠使用CJA中的地理位置資料建立報告。 |  | 2023 年 6 月 30 日 |
| **擴充對設定檔和查閱資料的查閱支援** | 您不僅可以將查詢資料集新增到事件資料集，還可以將查詢資料集新增到設定檔和查詢資料集。 | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **支援貨幣轉換** | CJA將支援貨幣轉換，作為格式化資料檢視中的量度元件的一部分。 | 2023 年 6 月 21 日 | 2023 年 7 月 19 日 |

{style="table-layout:auto"}

## 其他新功能或更新 {#other-new}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer資料檢視** | CJA管理員可以存取CJA中一些額外的資料檢視，標題為「AJO資料檢視(Sandbox-name)」。 這些資料檢視可用來支援Adobe Journey Optimizer (AJO)中的報表。 它們也可用來在CJA中執行更深入的AJO活動分析。 [了解更多](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html)。 |  | 2023 年 5 月 25 日 |
| **非生產沙箱的回填** | 在非生產沙箱中建立 Analytics 來源連接器資料流時，非生產沙箱中的回填將限制為 3 個月。生產沙箱將維持 13 個月。 | 不適用 | 2023 年 4 月 26 日 |
| **專案連結共用 (不需登入)** | 您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。這包括與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>此功能預設為啟用，系統管理員可以停用。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **更新 Analytics 儀表板應用程式 (行動應用程式) 的首頁** | 新更新的首頁可讓您在一個綜合計分卡清單中檢視所有計分卡。如果您一次登入可以存取多個組織，則單一清單會提供您所有組織的計分卡。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | 不適用 | 2023 年 5 月 10 日 |
| **衍生欄位** | 這代表衍生欄位的初始版本。衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。您可以進一步將衍生欄位定義為資料檢視中的元件 (量度或維度)，然後將衍生欄位用作工作區中的元件。<p>此版本支援行銷管道範本和以下功能：</p><ul><li>串連</li><li>情況</li><li>尋找和取代</li><li>查詢</li><li>URL 剖析</li></ul> <p>[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 10 日 | 2023年8月2日 |
| **CJA 的 Report Builder - 從儲存格中選取資料檢視** | 此功能可讓使用者從儲存格中選取資料區塊的資料檢視。如果您建立一個活頁簿且有多個資料結構類似的資料檢視，而且您想要多次重複使用一個活頁簿搭配不同資料檢視，這將很有幫助。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不適用 | 2023 年 5 月 24 日 |
| **在 Analysis Workspace 中排序元件** | <p>現在，在 Analysis Workspace 的左側邊欄或資料字典中查看元件時，可以使用新的「排序」選項。您可以按「建議」(最常用)、「字母順序」或「類別」(類型) 來排序元件。</p><p>以前，您只能搜尋或篩選元件。[了解更多](/help/components/overview.md)</p> | 不適用 | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修正

AN-318343；AN-319453

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | 不適用 | 不適用 |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉至AdobeIO OAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用AdobeIO JWT憑證的Adobe Analytics API、CJA API和Livestream客戶必須移轉至AdobeIO OAuth伺服器對伺服器憑證 **2025年1月1日**. 自2024年5月1日起，AdobeIO不允許建立新的JWT憑證。 使用JWT的客戶必須建立新的OAuth伺服器對伺服器認證，或將其現有的JWT認證移轉至OAuth伺服器對伺服器認證。 客戶也必須更新其使用者端應用程式，以使用新的OAuth伺服器對伺服器認證。 <ul><li>[從服務帳戶(JWT)憑證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth伺服器對伺服器認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## 相關資源

* [2023 年舊版 CJA 發行說明](/help/release-notes/2023.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
