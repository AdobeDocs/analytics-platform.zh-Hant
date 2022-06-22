---
title: Customer Journey Analytics 總覽
description: 了解 Customer Journey Analytics 可如何協助您將 Analysis Workspace 與 Experience Platform 的資料搭配使用。
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 64cd3983f58f1f0de1d8639e5cb1e705dd72ef44
workflow-type: tm+mt
source-wordcount: '1149'
ht-degree: 81%

---

# Customer Journey Analytics 總覽

Customer Journey Analytics 是 Analytics 的功能，讓您可搭配 Adobe Experience Platform 的資料運用 Analysis Workspace 的強大功能。這能協助您劃分、篩選、查詢及視覺化多年累積的資料，並結合 Platform 掌握各種資料結構描述和類型的能力。採用 **Experience Data Model (XDM)**，能以統一方式呈現和組織資料，可進行組合和探索。**Experience Query Services** 可讓您使用相容於 SQL 的工具和架構來查詢及操控所有資料。

高層級 CJA 架構顯示於此處：

![架構](assets/cja-architecture.png)

以下是 Customer Journey Analytics 的影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## 比較 CJA 與傳統 Adobe Analytics

Customer Journey Analytics通過提供易於使用的跨渠道功能和消除以前版本的Adobe Analytics限制，擴展了Adobe Analytics的範圍。 幾個值得注意的改善項目如下：

* **不限數量的變數和事件**：eVar、prop 和事件的概念已不存在。資料主要聚焦於維度和量度。資料集可以具有無限數量的唯一維度和度量。
* **不限數量的唯一值**：Adobe Experience Platform 不受任何獨特限制。
* **變更歷史資料**：您可以使用 Adobe Experience Platform 移除或修正資料。
* **跨報表套裝資料**：可在 Platform 中結合來自多個資料集的現有實作。

Customer Journey Analytics 的初始版本包含 Analysis Workspace 中的多項功能。如需完整清單，請參閱 [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。

## 主要使用案例

Customer Journey Analytics 可用來：

* **在歷程情境中了解客戶**：您可以跨多個管道依序檢視和分析資料。來自您客服中心、POS 系統和線上屬性的資料可合併成單一報表檢視。
* **讓每個人都能查看深入分析**：將資料存取大眾化，透過資料衍生的深入分析協助更多人進行商業決策。組織中負責任何客戶體驗相關事務的所有人，都可根據更完整的資料更快速做出真正的決策。
* **為您的分析師運用資料科學的力量**：Customer Journey Analytics 可讓一般人使用資料科學獲得深入見解及分析。
* **使用按需報告可視化和與資料集交互**:工作區可以使用符合某些基本規則的來自Adobe Experience Platform的任何資料集。
* **檢視非 Web 資料**：工作區不再局限於「點擊」或「事件」的硬性定義。自訂結構描述可完全控制資料和定義。
* **更好地控制資料操作**:更改已上載的資料、建立資料集並將其導入到Workspace中。 Adobe Experience Platform 透過 Experience Cloud Query Service 提供查詢、擷取、轉換和載入工具。

## 先決條件

您必須符合下列必要條件，才能開始使用 Customer Journey Analytics：

* 貴組織具備有效的 Adobe Analytics Select、Prime 或 Ultimate 合約，且已有 Customer Journey Analytics 附加元件。如果您不確定已有的合約類型，或不確定您是否有 CJA 附加元件，請洽貴組織的客戶經理。
* 貴組織已佈建 Adobe Experience Platform。

## 管理員存取權限

要建立連接、添加資料集等，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/):

* 要訪問Customer Journey Analytics或建立連接，必須將您作為管理員添加到 **Customer Journey Analytics產品** 的 [Admin Console](https://adminconsole.adobe.com/enterprise/)。 產品管理員可獲得下列權限：
   * 建立/更新/刪除連線或資料檢視
   * 更新/刪除由其他用戶建立的項目、篩選器、計算度量或篩選器
   * 與所有使用者共用「工作區」專案
* 僅在Customer Journey Analytics內成為產品管理員是不夠的，無法建立、更新或刪除連接。 若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：
   * 檢視結構描述
   * 管理結構描述
   * 檢視身分識別命名空間
   * 檢視資料集

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

>[!NOTE]
>
>您不能像在傳統的Adobe AnalyticsCustomer Journey Analytics中那樣，授予或拒絕對單個度量或維的權限。 量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，所以可能會在 CJA 中有所變動，這樣也會回溯性地變更報告。

### 使用者存取權

Customer Journey Analytics 中，產品管理員以外的使用者無法查看資料檢視或連線，但可以建立篩選器、專案和計算量度。

## 術語更新

與傳統 Adobe Analytics 相比，CJA 中的數項功能已重新命名，以符合業界標準。一些更新的術語包括：

* 區段現在稱為「篩選器」。
* 虛擬報告套裝現在稱為「資料檢視」。
* 「分類」現在稱為「查詢資料集」。
* 客戶屬性現在稱為「設定檔資料集」。
* 點擊容器現在稱為「事件」容器。
* 造訪容器現在稱為「工作階段」容器。
* 訪客容器現在稱為「人員」容器。

## 以 Adobe Experience Platform 為基礎的其他功能

Customer Journey Analytics 是依賴 Adobe Experience Platform 的許多功能之一。同樣以 Experience Platform 為基礎的其他幾項功能可讓您充份運用您的資料。

Adobe Experience Platform 可讓您集中和標準化來自任何系統的客戶資料與內容，並運用資料科學和機器學習技術來改善個人化體驗的設計和傳遞。Platform 中的客戶資料以資料集形式儲存，而資料集是由結構描述和資料批次組成。如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html)。

從資料接收到直接SQL訪問，Experience Platform的幾個元件是Customer Journey Analytics的核心，並補充它：

* [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html)：使用標準 SQL 從 Adobe Experience Platform 擷取資料，例如 Adobe 解決方案資料、客戶第一方資料或任何其他 Platform 資料。這是一種無伺服器工具，可用來加入任何資料集，以及將查詢結果擷取為新資料集，並用於報表、Data Science Workspace 或內嵌至 Profile Service。 您可以使用 Query Service 來建立資料分析生態系統，進而了解消費者在不同互動管道中的行為。這些渠道可能包括銷售點系統、 Web 、移動、 CRM系統等。
* [即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)：
* [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html)：
* 「開發人員」選項中的 [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html)：您可以在 Adobe Experience Platform 中使用預先建立的人工智慧 (AI) 和機器學習模型來影響客戶歷程的各個階段。透過發掘隱藏的深入分析，您可以針對客戶歷程做出更有效的預測、提供建議的最佳後續步驟，或是將繁瑣的程序自動化。

## 影片

* 在 Customer Journey Analytics 中處理資料：

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Customer Journey Analytics 的架構和整合:

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

