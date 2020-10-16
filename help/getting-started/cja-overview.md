---
title: Customer Journey Analytics 概觀
description: 了解 Customer Journey Analytics 可如何協助您將 Analysis Workspace 與 Experience Platform 的資料搭配使用。
translation-type: tm+mt
source-git-commit: 8067bb355934f8f6f1d54776f44abfd853aee231
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 100%

---


# Customer Journey Analytics 概觀

Customer Journey Analytics 是 Analytics 的功能，讓您可搭配 Adobe Experience Platform 的資料運用 Analysis Workspace 的強大功能。這能協助您劃分、篩選、查詢及視覺化多年累積的資料，並結合 Platform 掌握各種資料結構和類型的能力。採用 **Experience Data Model (XDM)**，能以統一方式呈現和組織資料，可進行組合和探索。**Experience Query Services** 可讓您使用相容於 SQL 的工具和架構來查詢及操控所有資料。

## 比較 CJA 與傳統 Adobe Analytics

Customer Journey Analytics 提供簡單易用的跨管道功能，並移除舊版 Adobe Analytics 的限制，進一步擴展 Analytics 的應用範圍。幾個值得注意的改善項目如下：

* **不限數量的變數和事件**：eVar、prop 和事件的概念已不存在。資料主要聚焦於維度和量度。資料集可以有不限數量的不重複維度和量度。
* **不限數量的不重複值**：Adobe Experience Platform 不受限於任何不重複限制，例如傳統報表套裝中的 50 萬個不重複特值。
* **變更歷史資料**：您可以使用 Adobe Experience Platform 移除或修正資料。
* **跨報表套裝資料**：可在 Platform 中結合來自多個資料集的現有實作。

Customer Journey Analytics 的初始版本包含 Analysis Workspace 中的多項功能。如需完整清單，請參閱 [Customer Journey Analytics 功能支援](cja-aa.md)。

## 比較 CJA 與 Cross-Device Analytics

[Cross-Device Analytics](https://docs.adobe.com/content/help/zh-Hant/analytics/components/cda/cda-home.html) 與 Adobe Experience Platform Identity Service 整合，利用 Co-op 圖表或私密圖表來識別數位裝置與人員對應的方式。Adobe Analytics Ultimate 客戶可使用此功能。

另一方面，CJA 與 Adobe Experience Platform 資料集整合，並在 Analysis Workspace 中啟用跨管道分析。雖然 CJA 尚未與 Co-op 或私密身分圖表整合，但您可以「自攜 ID」將資料集合在一起，而且這些資料集可超出數位資料的範圍，同時包含線上和離線接觸點。下文將詳細說明 CJA 必要條件。

## 主要使用案例

Customer Journey Analytics 可用來：

* **在歷程情境中了解客戶**：您可以跨多個管道依序檢視和分析資料。來自您客服中心、POS 系統和線上屬性的資料可合併成單一報表檢視。
* **讓每個人都能查看深入分析**：將資料存取大眾化，透過資料衍生的深入分析協助更多人進行商業決策。組織中負責任何客戶體驗相關事務的所有人，都可根據更完整的資料更快速做出真正的決策。
* **為您的分析師運用資料科學的力量**：Customer Journey Analytics 可讓一般人使用資料科學獲得深入見解及分析。
* **使用臨機報表將資料集視覺化並與之互動**：工作區可使用 Adobe Experience Platform 中符合某些基本規則的任何資料集。
* **檢視非 Web 資料**：工作區不再局限於「點擊」或「事件」的硬性定義。自訂結構可完全控制資料和定義。
* **對資料操控發揮更大控制力**：變更已上傳的資料、建立新的資料集，並將其匯入工作區中。Adobe Experience Platform 透過 Experience Cloud Query Service 提供查詢、擷取、轉換和載入工具。

## 必要條件

您必須符合下列必要條件，才能開始使用 Customer Journey Analytics：

* 貴組織具備有效的 Adobe Analytics Select、Prime 或 Ultimate 合約，且已有 Customer Journey Analytics 附加元件。如果您不確定已有的合約類型，或不確定您是否有 CJA 附加元件，請洽貴組織的客戶經理。
* 貴組織已佈建 Adobe Experience Platform。

## 管理員存取權限

若要建立連線、新增資料集及執行其他作業，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中擁有下列權限：

* 自 2020 年 9 月 9 日起，若要存取 Customer Journey Analytics 或建立連線，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中將自己新增為 **Customer Journey Analytics 產品設定檔**&#x200B;的管理員。管理員需要下列權限：
   * 建立/更新/刪除連線或資料檢視
   * 更新/刪除其他使用者建立的專案、篩選器、計算量度或區段
   * 將 Analysis Workspace 專案共用給所有使用者
* 在 Customer Journey Analytics 中成為產品管理員後，仍無法建立、更新或刪除連線。若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：
   * 檢視結構
   * 管理結構
   * 檢視身分識別命名空間
   * 檢視資料集

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://docs.adobe.com/content/help/zh-Hant/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)。

### 使用者存取權

Customer Journey Analytics 中的非管理員 (使用者) 無法檢視資料檢視或連線，但可以建立篩選器、專案和計算量度。

## 術語更新

與傳統 Adobe Analytics 相比，CJA 中的數項功能已重新命名，以符合業界標準。一些更新的術語包括：

* 區段現在稱為「篩選器」。
* 虛擬報表套裝現在稱為「檢視」。
* 分類現在稱為「查找資料集」。
* 客戶屬性現在稱為「設定檔資料集」。
* 點擊容器現在稱為「事件」容器。
* 造訪容器現在稱為「工作階段」容器。
* 訪客容器現在稱為「人員」容器。

## 以 Adobe Experience Platform 為基礎的其他功能

Customer Journey Analytics 是依賴 Adobe Experience Platform 的許多功能之一。同樣以 Experience Platform 為基礎的其他幾項功能可讓您充份運用您的資料。

Adobe Experience Platform 可讓您集中和標準化來自任何系統的客戶資料與內容，並運用資料科學和機器學習技術來改善個人化體驗的設計和傳遞。Platform 中的客戶資料以資料集形式儲存，而資料集是由結構和資料批次組成。如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://docs.adobe.com/content/help/zh-Hant/experience-platform/landing/home.translate.html)。

Experience Platform 的多個元件 (從資料內嵌到直接 SQL 存取) 是 Customer Journey Analytics 的核心，且可與其搭配使用：

* [Query Service](https://docs.adobe.com/content/help/zh-Hant/experience-platform/query/home.translate.html)：使用標準 SQL 從 Adobe Experience Platform 擷取資料，例如 Adobe 解決方案資料、客戶第一方資料或任何其他 Platform 資料。這是一種無伺服器工具，可用來加入任何資料集，以及將查詢結果擷取為新資料集，並用於報表、Data Science Workspace 或內嵌至 Profile Service。您可以使用 Query Service 來建立資料分析生態系統，進而了解消費者在不同互動管道中的行為。這些管道可能包括銷售點系統、網路、行動裝置、CRM 系統等。
* [即時客戶設定檔](https://docs.adobe.com/content/help/zh-Hant/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)：
* [Identity Service](https://docs.adobe.com/content/help/zh-Hant/experience-platform/landing/home.translate.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md)：
* 「開發人員」選項中的 [Data Science Workspace](https://docs.adobe.com/content/help/zh-Hant/experience-platform/data-science-workspace/home.html)：您可以在 Adobe Experience Platform 中使用預先建立的人工智慧 (AI) 和機器學習模型來影響客戶歷程的各個階段。透過發掘隱藏的深入分析，您可以針對客戶歷程做出更有效的預測、提供建議的最佳後續步驟，或是將繁瑣的程序自動化。
