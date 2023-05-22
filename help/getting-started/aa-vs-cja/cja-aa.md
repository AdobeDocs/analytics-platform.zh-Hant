---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '2003'
ht-degree: 74%

---

# Customer Journey Analytics 功能支援

下表列出了在Adobe Analytics(AA)中哪些功能在Customer Journey Analytics(CJA)中受支援、部分支援或不支援，以及在AA中哪些功能不受支援或不可用。 這些清單會隨著 CJA 新增功能而變更。

## 完整支援的功能/元件 {#full-support}

| Adobe Analytics 功能 | 支援說明事項 |
| --- | --- |
| 異常偵測 | 完整支援 |
| Attribution IQ | 完整支援 |
| 計算量度 | 完整支援；請注意，在傳統 Analysis Workspace 中任何現有的計算量度將不會移前往 CJA。 |
| 行事曆事件 | 完整支援。 已將行事曆活動實作為工作區內的[註解](/help/components/annotations/overview.md)。 |
| CSV 下載 | 完整支援 |
| 自訂行事曆 | 完整支援 |
| 日期比較 | 完整支援 |
| 日期範圍 | 所有資料範圍功能都受到支援。 |
| 維度 | 完整支援；CJA 運用 XDM 並支援無限制維度。 CJA 並未繫結到傳統 Adobe Analytics 的自訂 eVars 或 props。 |
| 刪除 GDPR | 完整支援；請注意 GDPR 目前是協同 [!UICONTROL Adobe Experience Platform] 處理。 CJA 會繼承 [!UICONTROL Experience Platform] 對基礎資料集所做的任何資料變更。 |
| 提升度和可信度報告 | 透過 [Experimentation 面板](/help/analysis-workspace/c-panels/experimentation.md)完全支援 |
| 清單變數/清單 Prop | 完整資源；CJA 運用 XDM 並支援使用方式與 listVars 相似的無限制字串陣列。 |
| 銷售 eVar | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供完整支援 |
| 量度 | 完整支援；CJA 運用 Experience Data Model (XDM) 並支援無限制的量度，且未繫結到傳統 Analytics 的自訂成功事件。 請注意，傳統 Analytics 的部分標準量度已重新命名：訪客 = 人員，造訪 = 工作階段，點擊 = 事件。 |
| 行動計分卡/儀表板 | 完整支援 |
| 面板 | 空白面板、歸因面板、自由表格面板和快速深入分析全都受到支援。 |
| 匯出 PDF | 完整支援 |
| 專案策劃 | 完整支援 |
| 專案連結 | 完整支援 |
| 報告時間處理 | 完整支援；CJA 僅仰賴報告時間處理。 |
| 報告 API 存取權 | 完整支援；透過 [CJA API](https://www.adobe.io/cja-apis/docs/) 提供。 |
| 排程報告/專案 | 完整支援 |
| 區段 | 完整支援；現在稱為「篩選器」- 請注意，在傳統 Analysis Workspace 中任何現有的區段將不會移前往 CJA。 |
| 虛擬報告套裝 | 完整支援；現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| VRS 元件策劃 | 完整支援；現在是資料檢視的一部分。 |
| 串流媒體 Analytics | 媒體資料可使用分析資料連接器當作工作區中的「媒體同時檢閱者」面板和「媒體播放時間」面板的一部分提供。 |

{style="table-layout:auto"}

## 以新方式提供支援 {#new-support}

| 功能 | 附註 |
| --- | --- |
| 對象發佈 (區段發佈) | 如果具有 Adobe 的 Customer Data Platform 或 Journey Optimizer 產品授權則提供支援。[對象發佈](/help/components/audiences/audiences-overview.md) 會將對象發佈到 Experience Platform 中的「即時客戶個人資料」。 |
| Classifications | 現在稱為「查閱資料集」。 Analytics 中使用的分類，可以使用 Analytics 分類來源連接器匯入至 Experience Platform 和 CJA。 查閱資料集也可以直接上傳至 AEP，並在 CJA 中提供。 |
| 分類規則產生器 | 支援在 CJA 中使用[子字串](/help/data-views/component-settings/substring.md)。在報告時間使用字串操控，而不是查詢資料集。 |
| 自訂工作階段化 | 支援除移動後台事件之外的所有自定義會話功能。 |
| 銷售變數持續性 | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供完整支援 |
| 客戶屬性 | 現在稱為「描述檔資料集」，它們不會自動從 Experience Cloud 匯入，但必須上傳到 AEP，才能在 CJA 中使用。 |
| 資料摘要 | 通過 [AEP資料存取API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) 通過 [AEP目標](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en)。 這些選項提供了收集或接收到AEP資料湖中的所有資料的事件/行級導出。 後處理資料列不可用，因為後處理列是在查詢時計算的。 可以通過報告導出帖子列。 |
| 量度去重複化 | 現在於資料檢視中的量度上設定。量度去重複化發生在人員或工作階段層級，而不是資料集、資料檢視或連接層級。 |
| 進入、退出及逗留的時間等維度和量度 | 系統可支援 (進入與退出現在稱為「工作階段開始」和「工作階段結束」)，不過計算方式稍有不同。 |
| eVar 持續性設定 | eVar 不再是 CJA 的一部分。 不過持續性設定現在是資料檢視的一部分，可用於所有維度。 請記得，持續性是依據報表時間處理，而非資料收集處理。 「資料檢視」中設定的維度上限為 90 天的持續性，不支援無限制的持續性。 |
| IP 模糊化 | 對於使用 Analytics 來源連接器將來自 Adobe Analytics 的資料填入 CJA 的 CJA 客戶：在 Adobe Analytics 流程中套件的 IP 模糊化設定流向 CJA 資料。您可以視需要在 Adobe Analytics 中控制這些設定。<p>對於使用 Adobe Experience Platform Web SDK 將資料直接填入 Platform 和 CJA 的 CJA 客戶：您可以使用 Platform 中資料彙集的資料準備，來設定將根據您公司的需求模糊化 IP 位址的規則。 |
| 新工作階段與重複工作階段報告 | 先前使用造訪編號維度完成。新工作階段與重複工作階段支援 [13 個月的回溯期](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hant#new-repeat)。 |
| 產品變數 | 在 Experience Platform 中，使用者可在資料集結構描述中使用物件類型欄位陣列，以符合此使用案例。 在 CJA 中，客戶可以使用任意數量的產品變數，且不限於 Adobe Analytics 中的單一變數。 |
| 專案共用 | 專案共用功能僅支援在 CJA 的使用者之間使用 - CJA 與傳統 Analysis Workspace 之間不支援專案共用。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |
| Report Builder (Excel 外掛程式) | 支援用於 Excel 的新 Office 365 外掛程式。 |
| 使用者權限/資料存取控制 | CJA 會區分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) 產品管理員、產品設定檔管理員與使用者。只有產品管理員可以建立/更新/刪除連線、專案、篩選器或由其他使用者建立的計算指標，而產品管理員和產品設定檔管理員可以編輯資料檢視。其他使用者權限可建立計算量度、篩選器或附註等。 |
| 處理規則、VISTA 規則、行銷管道處理規則 | Adobe Experience Platform Data Prep 功能支援 WebSDK 式資料集和 Analytics Data Connector 資料。 |

{style="table-layout:auto"}

## 部分支援 {#partial}

| 功能 | 附註 |
| --- | --- |
| 行銷頻道 | 行銷頻道資料會透過 Analytics 來源連接器傳輸至 CJA。 如果您是使用舊版 Adobe Analytics，仍需設定行銷管道規則，且不支援部分規則。如需詳細資訊，請參閱 [CJA 行銷管道文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant#cja-usecases)。此外，對於 WebSDK 實作，外掛程式可用於定義用戶端行銷管道。未來計劃支援報告時間行銷管道處理規則。 |
| 跨裝置/跨管道拼接 | 支援直接包含身分資訊的資料集 (也稱為「依欄位匯整」)。目前尚不支援圖表式匯整，但已規劃完成。請參閱[跨管道分析](/help/cca/overview.md)。 |
| 機器人篩選 | 對於以 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)為基礎的資料集，則會套用機器人篩選。 [!UICONTROL Experience Platform] 或 CJA 不會執行其他資料集的一般機器人篩選邏輯。 |
| 裝置、瀏覽器、推薦者、技術維度 | 支援 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)型資料集。請參閱我們的[文件，了解透過 ADC 支援的 Analytics 變數](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant)。<p>如果您未使用 Adobe 來源連接器將資料從 Adobe Analytics 填入到 CJA，而是使用 Experience Platform Web SDK 資料彙集，目前不支援根據裝置查詢的裝置和維度。 已規劃於未來支援。 |
| 地理細分維度 | 收集到 Adobe Analytics 的所有 GeoSegmentation/地理位置都會透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)流入 CJA。 未使用 Analytics 來源連接器的實作 (例如仰賴 AEP Web SDK 進行數位資料收集的實作) 將不會具有自動執行的完整地理位置查詢：支援國家/地區和美國州別，但不支援城市和郵遞區號。 |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援區段比較面板和 Analytics for Target (A4T) 面板。 |
| 處理規則 | 對於以 Analytics 來源連接器為基礎的資料集，仍會套用處理規則。 [Adobe Experience Platform 中的資料準備功能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)也可用來取代直接送到 Platform 的資料適用的處理規則。 |
| A4T | 透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)中的欄位提供部分支援。已規劃目標活動和體驗支援 A4T 易記名稱。 |

{style="table-layout:auto"}

## 目前不支援，但已列入規劃 {#planned}

| 功能 | 附註 |
| --- | --- |
| 警報 | 已規劃提供支援。 |
| 貢獻分析 | 已規劃提供支援。 |
| Data Warehouse 報告 | 規劃從 Analysis Workspace 介面提供支援。 Adobe Experience Platform [[!UICONTROL 查詢服務]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant)也會提供適用於在 CJA 中這些使用案例的介面。 |
| 透過裝置圖表進行 ID 拼接 | 已規劃提供支援。 |
| 專案範本 | 已規劃提供支援。 |
| 即時報表 | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 貨幣轉換 | 已規劃提供支援。 |
| 交易 ID 資料來源 | 已規劃提供支援。 |
| 將專案/篩選器/計算量度從 AA 移轉到 CJA | 已規劃提供支援。 |
| 摘要層級資料來源 | 已規劃提供支援。 |

{style="table-layout:auto"}

## 尚未規劃提供支援 {#not-planned}

| 功能 | 附註 |
| --- | --- |
| Activity Map | 尚未規劃提供支援。 |
| Advertising Cloud | 尚未規劃提供支援。 |

{style="table-layout:auto"}

## 永遠不提供支援 {#never}

* 使用 Cross-Device Coop 的人員量度
* Reports &amp; Analytics 儀表板
* Reports &amp; Analytics 書籤
* Reports &amp; Analytics 目標

## CJA功能在Adobe Analytics不可用 {#cja-not-aa}

下表列出了在Customer Journey Analytics(CJA)中可用但在Adobe Analytics(AA)中不受支援的功能。

| 功能 | 更多詳情 |
| --- | --- |
| 適用於任何類型的資料 | CJA與Experience Platform保存各種資料模式和類型的能力相結合。 使用 [體驗資料模型(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant)資料可以統一表示和組織，便於組合和探索。 Adobe Analytics主要專注於Web和移動分析資料，並具備一些功能 [導入資料](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=zh-Hant)。 |
| 無限的客戶Dimension和指標 | CJA維度是無限的；值可以是數字、文本、對象、清單或所有的混合。 Dimension可以是嵌套的或分層的。 分析最多支援75個道具和250個eVar。 這將消除使用維和事件的當前測量限制。 |
| 無限基數/唯一值 | CJA支援在單個維中報告的無限個唯一值或維項。 AA限於500K唯一值。 這消除了當前大規模分析實施中存在的報告和分析限制。 |
| 報告時間轉換 | 在CJA中報告時間轉換（更稱為資料視圖）允許您進一步解釋連接中的資料。 您可以更改或刪除資料，而無需重新實施；使用子字串來操縱維；根據任何值建立度量；篩選子事件。 這些都可以非破壞性地完成。 Adobe Analytics通過虛擬報告套件和會話提供有限的功能。 |
| 實驗分析 | CJA可以從定義為連接一部分的任何資料源評估任何實驗的提升和置信度。 這使您能夠瞭解跨越任何渠道的客戶交互之間的因果關係。 分析僅限於通過目標分析(A4T)整合進行實驗分析。 |
| 跨裝置分析 | CJA支援來自未經驗證和經過驗證的會話的設備特定資料集的無縫組合。 您還可以將歷史資料回填到已知設備。 在分析中，此功能僅限於單個報告套件和設備圖形的使用。 |
| SQL訪問 | 使用「資料Distiller」選項，CJA可以消除在Adobe後端處理中收集的資料的限制。 您可以使用SQL修改資料，建立新值和業務獨有的資料集，並繼續探索。 分析不支援對其資料的任何類型的SQL訪問。 |
| 增強的安全和隱私選項 — HIPAA就緒性 | CJA已準備好HIPAA ，並為法規合規性提供了其他安全選項。 Adobe Analytics還沒準備好HIPAA。 |

{style="table-layout:auto"}
