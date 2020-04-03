---
title: Customer Journey Analytics 概觀
description: 客戶歷程分析簡介
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Customer Journey Analytics 概觀

「客戶歷程分析」是一項Analytics功能，可讓您搭配Adobe Experience Platform的資料使用分析工作區的強大功能。 它可以劃分、篩選、查詢及視覺化多年的資料價值，並結合Platform掌握各種資料架構和類型的能力。 使用 **Experience Data Model(XDM)**，資料可以統一呈現和組織，並可進行組合和探索。 **Experience Query Services可讓您** 使用SQL相容的工具和架構來查詢和控制所有資料。

## 比較CJA與傳統Adobe Analytics

客戶歷程分析提供簡單易用的跨通道功能，並移除舊版Adobe Analytics的限制，進一步擴展了Analytics的範圍。 一些值得注意的改進是：

* **無限制的變數和事件**:eVar、prop和事件的概念已不再存在。 資料主要針對維度和量度。 資料集可以有不限數量的獨特維度和度量。
* **不限數量的唯一值**:Adobe Experience Platform不受任何獨特限制，例如傳統報表套裝中的500k獨特值。
* **變更歷史資料**:使用Adobe Experience Platform，您可以移除或修正資料。
* **跨報表套裝資料**:來自多個資料集的現有實施可結合在平台中。

「客戶歷程分析」的初次發行包含分析工作區中的許多功能。 如需完整清單，請參閱客 [戶歷程分析功能支援](cja-aa.md)。

## 比較CJA與跨裝置分析

[跨裝置分析](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) (Cross-Device Analytics)與Adobe Experience Platform Identity Service整合，利用Co-op Graph或Private Graph來識別數位裝置如何與人對應。 Adobe Analytics Ultimate客戶可使用它。

CJA與Adobe Experience Platform資料集整合，並在Analysis Workspace中啟用跨通道分析。 雖然CJA尚未與Co-op或「私人」身分圖形整合，但您可以「攜帶您自己的ID」將資料集合在一起，而且這些資料集可超越數位資料，同時包含線上和離線觸點。 CJA必要條件將於下文詳述。

## 主要使用案例

客戶歷程分析可讓您：

* **在歷程情境中瞭解客戶**:您可以依序檢視和分析跨越多個通道的資料。 來自客服中心、POS系統和線上屬性的資料可結合為單一報告檢視。
* **讓每個人都能獲得見解**:透過資料衍生的見解，讓更多人民大眾化資料存取，並做出商業決策。 組織中任何負責客戶體驗任何方面的人員，都可以根據更完整的資料，更快地做出真正的決策。
* **為您的分析師利用資料科學的力量**:客戶歷程分析可讓正常人使用資料科學發掘深入見解和分析。
* **使用臨機報告視覺化資料集並與之互動**:工作區可使用Adobe Experience Platform中符合某些基本規則的任何資料集。
* **檢視非Web資料**:工作區不再局限於「點擊」或「事件」的剛性定義。 自訂結構可完整控制資料和定義。
* **對您的資料操控發揮更大控制力**:變更您上傳的資料、建立新的資料集，並將它們匯入工作區。 Adobe Experience Platform透過Experience Cloud查詢服務提供查詢、擷取、轉換和載入工具。

## 必要條件

您必須先符合下列先決條件，才能開始使用客戶歷程分析：

* 您的組織與Adobe Analytics透過Customer Journey Analytics附加元件與Select、Prime或Ultimate簽訂有效合約。 如果您不確定您擁有的合約類型，或不確定您是否擁有CJA附加元件，請連絡您組織的帳戶管理員。
* 您的組織已布建Adobe Experience Platform。

## 使用者存取權限

若要建立連線、新增資料集等，您需要在「管理控制台」中擁有下列 [權限](https://adminconsole.adobe.com/enterprise/):

* 要管理Experience Platform中的資料集，您必須是提供「管理資料集」權限的平台產品配置檔案的一部分。 如需詳細資訊，請參 [閱Adobe Experience Platform中的存取控制](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)。
* 若要建立與平台資料集的連線，您必須是提供下列權限的平台產品設定檔的一部分：
   * 檢視結構描述
   * 查看資料集
   * 管理身分名稱空間
   * 檢視沙盒
* 若要存取客戶歷程分析或建立連線，您還需要在「管理控制台」中新增至「客戶歷程分析產 [品設定檔」](https://adminconsole.adobe.com/enterprise/)。

### 術語更新

CJA中的幾項功能已更名為符合業界標準。 有些更新名稱包括：

* 區段現在稱為「篩選」。
* 虛擬報表套裝現在稱為「檢視」。
* 分類現在稱為「查閱資料集」。
* 客戶屬性現在稱為「描述檔資料集」。
* 點擊容器現在稱為「事件」容器。
* 瀏覽容器現在稱為「作業」容器。
* 訪客容器現在稱為「人員」容器。

## 其他以Adobe Experience Platform為基礎的功能

客戶歷程分析是許多依賴Adobe Experience Platform的功能之一。 另外幾項功能也建立在Platform上，讓您充份運用您的資料。

Adobe Experience Platform可讓您集中管理和標準化來自任何系統的客戶資料和內容，並套用資料科學和機器學習來改善個人化體驗的設計和傳遞。 平台中的客戶資料作為資料集儲存，資料集由模式和批資料組成。 如需有關此平台的詳細資訊，請參 [閱Adobe Experience Platform架構概觀](https://www.adobe.io/apis/experienceplatform/home/overview.html)。

從資料擷取到直接SQL存取，Experience Platform的數個元件是客戶歷程分析的核心，並與之搭配運作：

* [查詢服務](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html):使用標準SQL從Adobe Experience Platform擷取資料，例如Adobe解決方案資料、客戶第一方資料或任何其他平台資料。 它是一種無伺服器工具，可讓您加入任何資料集，並將查詢結果擷取為新資料集，以用於報告、資料科學工作區或擷取至描述檔服務。 您可以使用查詢服務來建立資料分析生態系統，以建立消費者在不同互動管道中的形象。 這些通道可能包括銷售點系統、網路、行動、CRM系統等。
* [即時客戶個人檔案](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Identity 服務](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [「開發人員](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) 」選項中的Data Science Workspace:您可以在Adobe Experience Platform中使用預先建立的人工智慧(AI)和機器學習模型來影響客戶旅程的各個點。 透過發掘隱藏的見解，您可以在客戶歷程中做出更好的預測、建議建議的最佳後續步驟，或自動化繁瑣的流程。
