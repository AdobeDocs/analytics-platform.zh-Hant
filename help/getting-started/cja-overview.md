---
title: Customer Journey Analytics 概觀
description: 了解 Customer Journey Analytics 可如何協助您將 Analysis Workspace 與 Experience Platform 的資料搭配使用。
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
source-git-commit: cd3747e0c9e041394db79d70fcd63294d0da9867
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 100%

---

# Customer Journey Analytics 概觀

Customer Journey Analytics 是 Adobe 的新一代 Analytics 解決方案，讓您可搭配 Adobe Experience Platform 的資料運用 Analysis Workspace 的強大功能。這能協助您劃分、篩選、查詢及視覺化多年累積的資料，並結合 Platform 掌握各種資料綱要和類型的能力。採用 **Experience Data Model (XDM)**，能以統一方式呈現和組織資料，可進行組合和探索。**Adobe Experience Platform Query Service** 可讓您使用相容於 SQL 的工具和架構來查詢及操控所有資料。

高層級 Customer Journey Analytics 架構如下所示：

![架構](assets/cja-architecture.png)

以下是 Customer Journey Analytics 的影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Customer Journey Analytics 與傳統 Adobe Analytics 的比較

Customer Journey Analytics 提供簡單易用的跨頻道功能，並移除舊版 Adobe Analytics 的限制，進一步擴展 Analytics 的應用範圍。幾個值得注意的改善項目如下：

* **不限數量的變數和事件**：eVar、prop 和事件的概念已不存在。資料主要聚焦於維度和量度。資料集可以有不限數量的不重複維度和量度。
* **不限數量的唯一值**：Adobe Experience Platform 不受任何獨特限制。
* **變更歷史資料**：您可以使用 Adobe Experience Platform 移除或修正資料。
* **跨報告套裝資料**：可在 Platform 中結合來自多個資料集的現有實作。

>[!TIP]
>
>如果您一直在使用 Adobe Analytics 並希望在 Customer Journey Analytics 中使用您的 Adobe Analytics 資料，請參閱[從傳統 Adobe Analytics 擷取和使用資料](../data-ingestion/analytics.md)快速入門指南；此指南為[資料擷取](../data-ingestion/data-ingestion.md)章節的一部分。

Customer Journey Analytics 的初始版本包含 Adobe Analytics 中的多項功能。如需完整清單，請參閱 [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。

## 主要使用案例

Customer Journey Analytics 可用來：

* **在歷程情境中了解客戶**：您可以跨多個管道依序檢視和分析資料。來自您客服中心、POS 系統和線上屬性的資料可合併成單一報表檢視。
* **讓每個人都能查看深入分析**：將資料存取大眾化，透過資料衍生的深入分析協助更多人進行商業決策。組織中負責任何客戶體驗相關事務的所有人，都可根據更完整的資料更快速做出真正的決策。
* **為您的分析師運用資料科學的力量**：Customer Journey Analytics 可讓一般人使用資料科學獲得深入見解及分析。
* **使用隨選報告將資料集視覺化並與其互動**：工作區可使用 Adobe Experience Platform 中符合某些基本規則的任何資料集。
* **檢視非 Web 資料**：工作區不再局限於「點擊」或「事件」的硬性定義。自訂綱要可完全控制資料和定義。
* **對資料操控發揮更大控制力**：變更已上傳的資料、建立新的資料集，並將其匯入工作區中。Adobe Experience Platform 透過 Experience Platform Query Service 提供查詢、擷取、轉換和載入工具。

## 先決條件

您必須符合下列必要條件，才能開始使用 Customer Journey Analytics：

* 貴組織具備有效的 Adobe Analytics Select、Prime 或 Ultimate 合約，且已有 Customer Journey Analytics 附加元件。如果您不確定已有的合約類型，或不確定您是否有 Customer Journey Analytics 附加元件，請洽 Adobe 帳戶團隊。
* 貴組織已佈建 Adobe Experience Platform。
* 您還能以獨立產品形式購買 Customer Journey Analytics，無需 Adobe Analytics。

## 存取控制

請參閱[存取控制](/help/admin/cja-access-control.md)主題。

## 術語更新

Customer Journey Analytics 中的數項功能已重新命名 (與傳統 Adobe Analytics 比較)，以便符合業界標準。一些更新的術語包括：

* 區段現在稱為「篩選器」。
* 虛擬報告套裝現在稱為「資料檢視」。
* 「分類」現在稱為「查詢資料集」。
* 客戶屬性現在稱為「設定檔資料集」。
* 點擊容器現在稱為「事件」容器。
* 造訪容器現在稱為「工作階段」容器。
* 訪客容器現在稱為「人員」容器。

## 以 Adobe Experience Platform 為基礎的其他功能

Customer Journey Analytics 是依賴 Adobe Experience Platform 的許多功能之一。同樣以 Experience Platform 為基礎的其他幾項功能可讓您充份運用您的資料。

Adobe Experience Platform 可讓您集中和標準化來自任何系統的客戶資料與內容，並運用資料科學和機器學習技術來改善個人化體驗的設計和傳遞。Platform 中的客戶資料以資料集形式儲存，而資料集是由綱要和資料批次組成。如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=zh-Hant)。

Experience Platform 的多個元件 (從資料擷取到直接 SQL 存取) 是 Customer Journey Analytics 的核心，且可對其進行補充：

* [Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant)：使用標準 SQL 從 Adobe Experience Platform 擷取資料，例如 Adobe 解決方案資料、客戶第一方資料或任何其他 Platform 資料。這是一種無伺服器工具，可用來加入任何資料集，以及將查詢結果擷取為新資料集，並用於報表、Data Science Workspace 或內嵌至 Profile Service。您可以使用 Experience Platform Query Service 來建立資料分析生態系統，進而瞭解消費者在不同互動管道中的行為。這些頻道可能包括銷售點系統、網路、行動裝置、CRM 系統等。
* [即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)：
* [Identity 服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)

## 影片

* 在 Customer Journey Analytics 中處理資料：

  >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Customer Journey Analytics 的架構和整合：

  >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

