---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '2044'
ht-degree: 100%

---

# Customer Journey Analytics 功能支援

下表列出了 Customer Journey Analytics 支援、部分支援或不支援 Adobe Analytics 中的哪些功能，以及 Adobe Analytics 中不支援或不提供 Customer Journey Analytics 的哪些功能。這些清單會隨著 Customer Journey Analytics 新增功能而改變。

## 完整支援的功能/元件 {#full-support}

| Adobe Analytics 功能 | 支援說明事項 |
| --- | --- |
| 異常偵測 | 完整支援 |
| Attribution IQ | 完整支援 |
| 計算量度 | 完整支援。任何傳統 Analysis Workspace 中的現有計算量度都不會移植到 Customer Journey Analytics。 |
| 行事曆事件 | 完整支援。 已將行事曆活動實作為工作區內的[註解](/help/components/annotations/overview.md)。 |
| CSV 下載 | 完整支援 |
| 自訂行事曆 | 完整支援 |
| 日期比較 | 完整支援 |
| 日期範圍 | 所有日期範圍功能都受到支援。 |
| 維度 | 完整支援。Customer Journey Analytics 使用 XDM 並支援無限制維度。Customer Journey Analytics 並未繫結到傳統 Adobe Analytics 的自訂 eVar 或 props。 |
| 刪除 GDPR | 完整支援；請注意，GDPR 目前是協同 [!UICONTROL Adobe Experience Platform] 處理。Customer Journey Analytics 會繼承 [!UICONTROL Experience Platform] 對基礎資料集所做的任何資料變更。 |
| 提升度和可信度報告 | 透過[實驗面板](/help/analysis-workspace/c-panels/experimentation.md)完全支援 |
| 清單變數/清單屬性 | 完整支援。Customer Journey Analytics 使用 XDM 並支援無限制字串陣列，其使用方式與 listVars 類似。 |
| 銷售 eVar | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供完整支援 |
| 量度 | 完整支援；Customer Journey Analytics 使用 Experience Data Model (XDM) 並支援無限制的量度，且未繫結到 Adobe Analytics 的自訂成功事件。Adobe Analytics 的部分標準量度已重新命名：訪客 = 人員，造訪 = 工作階段，點擊 = 事件。 |
| 行動計分卡/儀表板 | 完整支援 |
| 面板 | 空白面板、歸因面板、自由表格面板和快速深入分析全都受到支援。 |
| PDF 匯出 | 完整支援 |
| 專案策劃 | 完整支援 |
| 專案連結 | 完整支援 |
| 報告時間處理功能 | 完整支援；Customer Journey Analytics 完全依靠報告時間處理。 |
| 報告 API 存取權 | 完整支援；可透過 [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/) 使用。 |
| 排程報告/專案 | 完整支援 |
| 區段 | 完整支援。現在稱為「篩選器」。請注意，傳統 Analysis Workspace 中任何現有的區段都不會移植至 Customer Journey Analytics。 |
| 虛擬報告套裝 | 完整支援。現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| 虛擬報表套裝元件策劃 | 完整支援。現在是資料檢視的一部分。 |
| 裝置、瀏覽器、推薦者、技術維度 | 支援 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)型資料集和 WebSDK 產生的資料集。請參閱[透過 ADC 支援 Analytics 變數的文件](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant)。如果您使用 Experience Platform Web SDK 資料收集，目前不支援根據裝置查詢的裝置和維度。已規劃於未來支援。若要將裝置和瀏覽器查詢新增至 Web SDK 資料流，請參閱[本文件](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) |
| 串流媒體 Analytics | 媒體資料可使用 Analytics 來源連接器當作工作區中的「媒體同時檢閱者」面板和「媒體播放時間」面板的一部分提供。 |

{style="table-layout:auto"}

## 以新方式提供支援 {#new-support}

| 功能 | 附註 |
| --- | --- |
| 對象發佈 | 如果具有 Adobe 的 Customer Data Platform 或 Journey Optimizer 產品授權則提供支援。[對象發佈](/help/components/audiences/audiences-overview.md)會將對象發佈到 Experience Platform 中的「即時客戶個人資料」。 |
| Classifications | 現在稱為「查閱資料集」。 Analytics 中使用的分類，可以使用 Analytics 分類來源連接器匯入至 Experience Platform 和 Customer Journey Analytics。查詢資料集也可以直接上傳到 Experience Platform，並在 Customer Journey Analytics 中使用。 |
| 分類規則產生器 | 支援在 Customer Journey Analytics 中使用[子字串](/help/data-views/component-settings/substring.md)。在報告時間使用字串操控，而不是查詢資料集。 |
| 自訂工作階段長度 | 工作階段長度可以透過資料檢視中的[「工作階段」設定](../../data-views/create-dataview.md#session-settings)進行設定。如需詳細資訊，請參閱[工作階段設定](../../data-views/session-settings.md)。<br/>使用 Adobe Experience Platform Mobile SDK 支援，處理行動背景事件。更多資訊，請參閱[邊緣網路的生命週期](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/)。 |
| 貨幣轉換 | 支援做為資料檢視中[量度元件格式](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=zh-Hant#currency)的一部分。 |
| 銷售變數持續性 | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供完整支援 |
| 客戶屬性 | 現在稱為「設定檔資料集」；這些資料不會自動從 Experience Cloud 匯入，但必須上傳到 Experience Platform，才能在 Customer Journey Analytics 中使用。 |
| 資料摘要 | 可透過 [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=zh-Hant) 和 [Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hant) 匯出資料集的第一代資料。這些選項提供收集或擷取至 Experience Platform Data Lake 中的所有資料事件/列層級匯出。後處理資料欄無法使用，因為後處理欄是在查詢時計算的。可透過報告匯出發佈欄。 |
| Data Warehouse 報告 | [Customer Journey Analytics 完整表格匯出](/help/analysis-workspace/export/export-cloud.md)是 Adobe Analytics 中 Data Warehouse 報告的演化，其中包含許多使用者經常要求且目前 Data Warehouse 目前尚未提供的新功能。 |
| 進入、退出及逗留的時間等維度和量度 | 系統可支援 (進入與退出現在稱為「工作階段開始」和「工作階段結束」)，不過計算方式稍有不同。 |
| eVar 持續性設定 | eVar 不再是 Customer Journey Analytics 的一部分。不過持續性設定現在是資料檢視的一部分，可用於所有維度。 請記得，持續性是依據報表時間處理，而非資料收集處理。 「資料檢視」中設定的維度上限為 90 天的持續性，不支援無限制的持續性。 |
| 地域劃分維度 | 收集到 Adobe Analytics 的所有地域劃分/地理位置都會透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)流入 Customer Journey Analytics。未使用 Analytics 來源連接器但依賴 Experience Platform Web SDK 進行數位資料收集的實作，可使用 [Experience Edge Geo Lookup 服務](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)。 |
| IP 模糊化 | 對於使用 Analytics 來源連接器將 Adobe Analytics 的資料填入到 Customer Journey Analytics 中的 Customer Journey Analytics 客戶：Adobe Analytics 中套用的 IP 模糊化設定也會套用至 Customer Journey Analytics 資料。您可以視需要在 Adobe Analytics 中控制這些設定。<p>對於使用 Experience Platform Web SDK 將資料直接填入 Platform 和 Customer Journey Analytics 中的 Customer Journey Analytics 客戶，您可以使用 Platform 中「資料收集」的「資料準備」，根據公司的要求設定模糊 IP 位址規則。 |
| 行銷管道 | 使用 Analytics 來源連接器時，行銷管道資料會透過該連接器流入 Customer Journey Analytics。行銷管道規則是在傳統 Adobe Analytics 中設定，且部分規則不受支援。如需更多資訊，請參閱 [Customer Journey Analytics 行銷管道](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html)。<br/>對於 WebSDK 實作，會透過[衍生欄位](../../data-views/derived-fields/derived-fields.md)支援報告時間行銷管道處理規則。 |
| 量度去重複化 | 現在於資料檢視中的量度上設定。量度去重複化發生在人員或工作階段層級，而不是資料集、資料檢視或連線層級。 |
| 新工作階段與重複工作階段報告 | 先前使用造訪編號維度完成。新工作階段與重複工作階段支援 [13 個月的回溯期](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=zh-Hant)。 |
| 處理規則、VISTA 規則、行銷管道處理規則 | 支援將 Adobe Experience Platform Data Prep 功能以及[衍生欄位](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)用於 WebSDK 式資料集和來自 Analytics 來源連接器的資料。 |
| Products 變數 | 在 Experience Platform 中，使用者可在資料集結構描述中使用物件陣列，以符合此使用案例。在 Customer Journey Analytics 中，客戶可以使用任意數量的產品變數，且不限於 Adobe Analytics 中的單一變數。 |
| 專案共用 | 專案共用功能僅支援在 Customer Journey Analytics 的使用者之間使用 - Customer Journey Analytics 和傳統 Analysis Workspace 之間沒有專案共用。 |
| Report Builder | 支援用於 Excel 的新 Office 365 外掛程式。 |
| 使用者權限/資料存取控制 | Customer Journey Analytics 會區分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) 產品管理員、產品設定檔管理員和使用者。只有產品管理員可以建立/更新/刪除連線、專案、篩選器或由其他使用者建立的計算量度，而產品管理員和產品設定檔管理員可以編輯資料檢視。其他使用者權限可用於多種功能，例如建立計算量度、篩選器或註解等。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |
| 跨裝置/跨管道拼接 | 支援直接包含身分資訊的資料集 (也稱為「依欄位匯整」)。目前尚不支援圖表式拼接，但已規劃完成。請參閱[拼接](../../stitching/overview.md)。 |

{style="table-layout:auto"}

## 部分支援 {#partial}

| 功能 | 附註 |
| --- | --- |
| 機器人篩選 | 對於以 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)為基礎的資料集，則會套用機器人篩選。[!UICONTROL Experience Platform] 或 Customer Journey Analytics 不會針對其他資料集執行一般機器人篩選邏輯。 |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援區段比較面板和 Analytics for Target (A4T) 面板。 |
| Analytics for Target (A4T) | 透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)中的欄位提供部分支援。已規劃目標活動和體驗支援 A4T 易記名稱。 |

{style="table-layout:auto"}

## 不支援，但已在規劃提供支援 {#planned}

| 功能 | 附註 |
| --- | --- |
| 警報 | 已規劃提供支援。 |
| 貢獻分析 | 已規劃提供支援。 |
| 使用裝置圖表進行 ID 拼接 | 已規劃提供支援。 |
| 專案範本 | 已規劃提供支援。 |
| 即時報告 | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 交易 ID 資料來源 | 已規劃提供支援。 |
| 將專案、篩選器與計算量度從 Adobe Analytics 移轉至 Customer Journey Analytics | 已規劃提供支援。 |
| 摘要層級資料來源 | 已規劃提供支援。 |

{style="table-layout:auto"}

## 不支援，且未規劃提供支援 {#not-planned}

| 功能 | 附註 |
| --- | --- |
| Activity Map | 尚未規劃提供支援。 |
| Advertising Cloud | 尚未規劃提供支援。 |

{style="table-layout:auto"}

## 從未支援 {#never}

* 使用 Cross-Device Coop 的人員量度
* Reports &amp; Analytics 儀表板
* Reports &amp; Analytics 書籤
* Reports &amp; Analytics 目標

## Adobe Analytics 中無法使用 Adobe Customer Journey Analytics 功能 {#cja-not-aa}

下表列出了可在 Customer Journey Analytics 中使用，但 Adobe Analytics 不支援的功能。

| 功能 | 更多詳細資料 |
| --- | --- |
| 可容納任何類型的資料 | Customer Journey Analytics 可結合 Experience Platform 的功能，儲存各種資料綱要和類型。使用 [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant)，能以統一方式呈現和組織資料，可進行組合和探索。Adobe Analytics 主要專注於 Web 和行動分析資料，並具有一些[匯入資料](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=zh-Hant)的功能。 |
| 無限制的客戶維度和量度 | Customer Journey Analytics 維度是無限制的；值可以是數值、文字、物件、清單或混合所有前項。維度可以是嵌套式或階層式。Analytics 最多支援 75 個 props 和 250 個 eVar。 |
| 無限制的唯一值 | Customer Journey Analytics 支援可在單一維度中報告的無限制唯一值或維度項目。Adobe Analytics 最多 500,000 個唯一值。無限制的唯一值或維度消除了大規模分析實施中目前存在的報告和分析限制。 |
| 報告時間轉換 | Customer Journey Analytics 中的資料檢視可讓您進一步詮釋來自連線的資料。您可以變更或移除資料而無需變更實作、使用子字串操作維度、從任何值建立量度，或是篩選子事件。以上所有轉換的進行都是非破壞性。Adobe Analytics 透過虛擬報告套裝和自訂工作階段長度提供有限的功能。 |
| 實驗分析 | 對於任何定義為連線一部分之資料來源的實驗，Customer Journey Analytics 都可以評估其提升度和可信度。透過此評估，您可以了解任意管道中客戶互動之間的因果關係。Analytics 僅限於透過 A4T 進行的實驗分析。 |
| 跨裝置分析 | Customer Journey Analytics 支援無縫組合來自未經身分驗證和經過身分驗證工作階段的特定裝置資料集。Customer Journey Analytics 可以將歷史資料回填到已知裝置。在 Analytics 中，此功能僅限於單一報告套裝和裝置圖使用。 |
| SQL 存取 | 使用 Data Distiller 選項，Customer Journey Analytics 可以移除 Adobe 後端處理中收集資料的限制。您可以使用 SQL 修改資料、建立適合您業務的值和資料集，並繼續探索。Analytics 不支援對其資料進行任何類型的 SQL 存取。 |
| 提升安全性和隱私權選項 - HIPAA 整備程度 | Customer Journey Analytics 符合 HIPAA 標準，並提供額外的安全性選項以實現法規合規性。Adobe Analytics 尚未符合 HIPAA 標準。 |
| 組合資料集的能力 (例如 Adobe Analytics 報告套件) | Customer Journey Analytics 可讓您組合多個報告套件的資料，如同 Adobe Analytics 中的單一報告套件。 |
| 衍生的欄位 | 衍生的欄位允許對您的資料進行報告時間轉換。資料可以動態組合、更正或建立，並追溯套用於所有的報告。 |
| 引導式分析 | 引導式分析是一種報告格式，可讓使用者快速自助滿足其資料需求，以便他們能夠快速獲得高品質的深入解析並做出更多資料導向的決策。引導式分析是 Adobe Product Analytics 的一部分，Adobe Product Analytics 是 Customer Journey Analytics 的附加元件。 |

{style="table-layout:auto"}
