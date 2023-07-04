---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '2055'
ht-degree: 41%

---

# Adobe Customer Journey Analytics功能支援

下表列出Adobe Analytics中支援、部分支援或不支援Customer Journey Analytics的功能，以及Adobe Analytics中不支援或不提供哪些Customer Journey Analytics功能。 這些清單會隨著功能新增到Customer Journey Analytics而改變。

## 完整支援的功能/元件 {#full-support}

| Adobe Analytics 功能 | 支援說明事項 |
| --- | --- |
| 異常偵測 | 完整支援 |
| Attribution IQ | 完整支援 |
| 計算量度 | 完整支援。 傳統Analysis Workspace中的任何現有計算量度都不會移轉到Customer Journey Analytics。 |
| 行事曆事件 | 完整支援。 已將行事曆活動實作為工作區內的[註解](/help/components/annotations/overview.md)。 |
| CSV 下載 | 完整支援 |
| 自訂行事曆 | 完整支援 |
| 日期比較 | 完整支援 |
| 日期範圍 | 所有資料範圍功能都受到支援。 |
| 維度 | 完整支援。 Customer Journey Analytics使用XDM並支援無限制維度。 Customer Journey Analytics並未繫結至傳統Adobe Analytics的自訂eVar或prop。 |
| 刪除 GDPR | 完整支援；請注意 GDPR 目前是協同 [!UICONTROL Adobe Experience Platform] 處理。 Customer Journey Analytics會繼承任何資料變更 [!UICONTROL Experience Platform] 對基礎資料集建立。 |
| 提升度和可信度報告 | 透過 [Experimentation 面板](/help/analysis-workspace/c-panels/experimentation.md)完全支援 |
| 清單變數/清單 Prop | 完整支援。 Customer Journey Analytics使用XDM並支援無限字串陣列（與listVars的用途類似）。 |
| 銷售 eVar | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=zh-Hant#binding-dimension)提供完整支援 |
| 量度 | 完整支援；Customer Journey Analytics使用Experience Data Model (XDM)，並支援不限數量的量度，且不會與Adobe Analytics的自訂成功事件繫結。 Adobe Analytics的部分標準量度已重新命名：訪客=人物、造訪=工作階段、點選=事件。 |
| 行動計分卡/儀表板 | 完整支援 |
| 面板 | 空白面板、歸因面板、自由表格面板和快速深入分析全都受到支援。 |
| 匯出 PDF | 完整支援 |
| 專案策劃 | 完整支援 |
| 專案連結 | 完整支援 |
| 報告時間處理 | 完整支援；Customer Journey Analytics僅仰賴報表時間處理。 |
| 報告 API 存取權 | 完整支援；可透過 [CUSTOMER JOURNEY ANALYTICSAPI](https://developer.adobe.com/cja-apis/docs/). |
| 排程報告/專案 | 完整支援 |
| 區段 | 完整支援。 現在稱為「篩選器」 — 請注意，傳統Analysis Workspace中的任何現有區段都不會移植至Customer Journey Analytics。 |
| 虛擬報告套裝 | 完整支援。 現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| 虛擬報表套裝元件組織 | 完整支援。 現在是資料檢視的一部分。 |
| 串流媒體 Analytics | 媒體資料可使用分析資料連接器當作工作區中的「媒體同時檢閱者」面板和「媒體播放時間」面板的一部分提供。 |

{style="table-layout:auto"}

## 以新方式提供支援 {#new-support}

| 功能 | 附註 |
| --- | --- |
| 對象發佈 (區段發佈) | 如果具有 Adobe 的 Customer Data Platform 或 Journey Optimizer 產品授權則提供支援。[對象發佈](/help/components/audiences/audiences-overview.md) 會將對象發佈到 Experience Platform 中的「即時客戶個人資料」。 |
| Classifications | 現在稱為「查閱資料集」。 Analytics中使用的分類可以使用Analytics分類來源聯結器匯入至Experience Platform和Customer Journey Analytics。 查詢資料集也可以直接上傳到Experience Platform，並在Customer Journey Analytics中使用。 |
| 分類規則產生器 | 支援使用 [子字串](/help/data-views/component-settings/substring.md) 在Customer Journey Analytics中。 在報告時間使用字串操控，而不是查詢資料集。 |
| 自訂工作階段化 | 支援所有自訂工作階段化功能，行動背景事件除外。 |
| 貨幣轉換 | 支援做為的一部分 [格式化量度元件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) 在資料檢視中。 |
| 銷售變數持續性 | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=zh-Hant#binding-dimension)提供完整支援 |
| 客戶屬性 | 現在稱為「設定檔資料集」，系統不會自動從Experience Cloud匯入這類資料集，但必須先上傳至Experience Platform，才能在Customer Journey Analytics中使用。 |
| 資料摘要 | 資料集的第一代資料匯出可透過 [Experience Platform資料存取API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) 和至 [Experience Platform目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). 這些選項可讓您匯出收集或擷取到Experience Platform資料湖的所有資料，以事件/列層級匯出。 後處理資料欄無法使用，因為後處理欄是在查詢時計算的。 可透過報告匯出後置欄。 |
| 量度去重複化 | 現在於資料檢視中的量度上設定。量度去重複化發生在人員或工作階段層級，而不是資料集、資料檢視或連接層級。 |
| 進入、退出及逗留的時間等維度和量度 | 系統可支援 (進入與退出現在稱為「工作階段開始」和「工作階段結束」)，不過計算方式稍有不同。 |
| eVar 持續性設定 | eVar不再是Customer Journey Analytics的一部分。 不過持續性設定現在是資料檢視的一部分，可用於所有維度。 請記得，持續性是依據報表時間處理，而非資料收集處理。 在「資料檢視」中設定的Dimension限製為最多90天的持續性，不支援無限制的持續性。 |
| IP 模糊化 | 對於使用Analytics來源聯結器將來自Adobe Analytics的資料填入到Customer Journey Analytics中的Customer Journey Analytics客戶：在Adobe Analytics中套用的IP模糊化設定會流入您的Customer Journey Analytics資料。 您可以視需要在 Adobe Analytics 中控制這些設定。<p>適用於使用Experience PlatformWeb SDK將資料填入平台並直接Customer Journey Analytics的Customer Journey Analytics客戶。 您可以在Platform中使用資料收集的資料準備，以設定根據您公司的需求模糊化IP位址的規則。 |
| 新工作階段與重複工作階段報告 | 先前使用造訪編號維度完成。新工作階段與重複工作階段支援 [13 個月的回溯期](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=zh-Hant)。 |
| 產品變數 | 在 Experience Platform 中，使用者可在資料集結構描述中使用物件類型欄位陣列，以符合此使用案例。 在Customer Journey Analytics中，客戶可以使用任意數量的產品變數，而且不限於Adobe Analytics中的單一變數。 |
| 專案共用 | 僅支援在Customer Journey Analytics使用者之間共用專案 — Customer Journey Analytics和傳統Analysis Workspace之間不支援專案共用。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |
| Report Builder (Excel 外掛程式) | 支援用於 Excel 的新 Office 365 外掛程式。 |
| 使用者權限/資料存取控制 | Customer Journey Analytics區分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hant) 產品管理員、產品設定檔管理員和使用者。 只有產品管理員可以建立/更新/刪除連線、專案、篩選器或由其他使用者建立的計算指標，而產品管理員和產品設定檔管理員可以編輯資料檢視。建立計算量度、篩選器或註解等作業均可使用其他使用者許可權。 |
| 處理規則、VISTA 規則、行銷管道處理規則 | Adobe Experience Platform資料準備功能支援WebSDK型資料集和Analytics Data Connector的資料。 |
| 行銷管道 | 使用Analytics來源聯結器時，行銷管道資料會通過該聯結器流入Customer Journey Analytics。 行銷管道規則是在傳統Adobe Analytics中設定，不支援某些規則。 如需詳細資訊，請參閱 [Customer Journey Analytics行銷管道檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>針對WebSDK實作，透過支援報告時間行銷管道處理規則 [衍生欄位](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## 部分支援 {#partial}

| 功能 | 附註 |
| --- | --- |
| 跨裝置/跨管道拼接 | 支援直接包含身分資訊的資料集 (也稱為「依欄位匯整」)。目前尚不支援圖表式匯整，但已規劃完成。另請參閱 [拼接](../../stitching/overview.md). |
| 機器人篩選 | 對於以 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)為基礎的資料集，則會套用機器人篩選。 其他資料集的一般機器人篩選邏輯不會由執行 [!UICONTROL Experience Platform] 或Customer Journey Analytics。 |
| 裝置、瀏覽器、推薦者、技術維度 | 支援 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)型資料集。請參閱 [透過ADC支援哪些Analytics變數的檔案](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant).<p>如果您使用Experience PlatformWeb SDK資料彙集，目前不支援根據裝置查詢的裝置和維度。 已規劃於未來支援。 |
| 地理細分維度 | 收集到Adobe AnalyticsCustomer Journey Analytics的所有GeoSegmentation/地理位置都會透過 [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant). 不使用Analytics來源聯結器，但仰賴Experience Platform Web SDK進行數位資料收集的實作，可以使用 [Experience Edge地理查閱服務](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant). |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援區段比較面板和 Analytics for Target (A4T) 面板。 |
| 處理規則 | 對於以 Analytics 來源連接器為基礎的資料集，仍會套用處理規則。 [Adobe Experience Platform 中的資料準備功能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)也可用來取代直接送到 Platform 的資料適用的處理規則。 |
| A4T | 透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)中的欄位提供部分支援。已規劃目標活動和體驗支援 A4T 易記名稱。 |

{style="table-layout:auto"}

## 不支援，但已規劃 {#planned}

| 功能 | 附註 |
| --- | --- |
| 警報 | 已規劃提供支援。 |
| 貢獻分析 | 已規劃提供支援。 |
| Data Warehouse 報告 | 規劃從 Analysis Workspace 介面提供支援。 Adobe Experience Platform [[!UICONTROL 查詢服務]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant>) 此外也提供適用於Customer Journey Analytics中這些使用案例的介面。 |
| 透過裝置圖表進行 ID 拼接 | 已規劃提供支援。 |
| 專案範本 | 已規劃提供支援。 |
| 即時報表 | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 交易 ID 資料來源 | 已規劃提供支援。 |
| 將專案/篩選器/計算量度從Adobe Analytics移轉至Customer Journey Analytics | 已規劃提供支援。 |
| 摘要層級資料來源 | 已規劃提供支援。 |

{style="table-layout:auto"}

## 無支援，尚未規劃 {#not-planned}

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

## Adobe Analytics中不提供Adobe Customer Journey Analytics功能 {#cja-not-aa}

下表列出Customer Journey Analytics中可用的功能，但Adobe Analytics中不支援的功能。

| 功能 | 更多詳情 |
| --- | --- |
| 適用於任何型別的資料 | Customer Journey Analytics結合Experience Platform儲存各種資料結構描述和型別的能力。 使用 [體驗資料模型(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant)，能以統一方式呈現和組織資料，可進行組合和探索。 Adobe Analytics主要針對網頁和行動分析資料，具備以下功能： [匯入資料](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=zh-Hant). |
| 不限數量的客戶Dimension和量度 | Customer Journey Analytics維度沒有限制；值可以是數值、文字、物件、清單或所有專案的混合。 Dimension可以是巢狀或階層式。 Analytics最多可支援75個prop和250個eVar。 |
| 無限制基數/唯一值 | Customer Journey Analytics支援可在單一維度中報告的無限唯一值或維度專案。 Adobe Analytics限製為500.000個不重複值。 無限的唯一值或維度會移除大規模Analytics實作目前存在的報表和分析限制。 |
| 報表時間轉換 | Customer Journey Analytics中的報表時間轉換（又稱為「資料檢視」）可讓您進一步解譯來自連線的資料。 您可以變更或移除資料而不需要重新實作；使用子字串來操作維度；從任何值建立量度；篩選子事件。 而轉換則全部是以非破壞性的方式完成。 Adobe Analytics透過虛擬報告套裝和作業化提供有限的功能。 |
| 實驗分析 | Customer Journey Analytics可從定義為連線一部分的任何資料來源評估任何實驗的提升度和信賴度。 此評估可讓您瞭解跨任何管道的客戶互動之間的因果關係。 Analytics僅限於透過Analytics for Target (A4T)整合進行Experimentation analytics。 |
| 跨裝置分析 | Customer Journey Analytics支援來自未經驗證和已驗證工作階段的裝置特定資料集無縫結合。 Customer Journey Analytics選件，以將歷史資料回填至已知裝置。 在Analytics中，此功能僅限於單一報表套裝和使用裝置圖表。 |
| SQL存取 | 使用Data Distiller選項，Customer Journey Analytics可移除在Adobe後端處理時收集資料的限制。 您可以使用SQL修改資料、建立貴公司專屬的值和資料集，並繼續探索。 Analytics不支援對其資料進行任何型別的SQL存取。 |
| 增強式安全性和隱私權選項 — HIPAA整備 | Customer Journey Analytics已符合HIPAA規範，並提供額外的法規遵循安全性選項。 Adobe Analytics尚未符合HIPAA標準。 |

{style="table-layout:auto"}
