---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: c23b172fd4dc5d0303723c4e8ccfeaa251257bfd
workflow-type: ht
source-wordcount: '1188'
ht-degree: 100%

---

# Customer Journey Analytics 功能支援

下表列出 Adobe Analytics 中支援、部分支援或不支援的 Customer Journey Analytics (CJA) 功能。這些清單會隨著 CJA 新增功能而變更。

## 完整支援的功能/元件

| Adobe Analytics 功能 | 支援說明事項 |
| --- | --- |
| 異常偵測 | 完整支援 |
| 歸因 IQ | 完整支援 |
| 計算量度 | 完整支援；請注意，在傳統 Analysis Workspace 中任何現有的計算量度將不會移轉到 CJA。 |
| 跨裝置/跨管道彙整 | 完整支援；請參閱[跨管道分析](/help/connections/cca/overview.md)。 |
| 日期比較 | 完整支援 |
| 維度 | 完整支援；CJA 運用 XDM 並支援無限制維度。CJA 並未繫結到傳統 Adobe Analytics 的自訂 eVars 或 props。 |
| 內建 Analysis Workspace 維度 (例如瀏覽器類型、反向連結類型、作業系統等) | 只要填入基本 XDM 欄位 (例如使用者代理程式或裝置 ID)，CJA 就會以原生方式提供這些維度。客戶若有使用 Analytics Data Connector (ADC)，部分維度可供使用，但並非全部。請參閱[相關文件，了解可透過 ADC 支援的 Analytics 變數](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 刪除 GDPR | 完整支援；請注意 GDPR 目前是協同 [!UICONTROL Adobe Experience Platform] 處理。CJA 會繼承 [!UICONTROL Experience Platform] 對基礎資料集所做的任何資料變更。 |
| 清單變數/清單 Prop | 完整資源；CJA 運用 XDM 並支援使用方式與 listVars 相似的無限制字串陣列。 |
| 量度 | 完整支援；CJA 運用 Experience Data Model (XDM) 並支援無限制的量度，且未繫結到傳統 Analytics 的自訂成功事件。請注意，傳統 Analytics 的部分標準量度已重新命名：訪客 = 人員，造訪 = 工作階段，點擊 = 事件。 |
| 匯出 PDF | 完整支援 |
| 專案策劃 | 完整支援 |
| 專案連結 | 完整支援 |
| 報告時間處理 | 完整支援；CJA 僅仰賴報告時間處理。 |
| 報告 API 存取權 | 完整支援；透過 [CJA API](https://www.adobe.io/cja-apis/docs/) 提供。 |
| 排程報告/專案 | 完整支援 |
| 區段 | 完整支援；現在稱為「篩選器」- 請注意，在傳統 Analysis Workspace 中任何現有的區段將不會移轉到 CJA。 |
| 使用者權限/資料存取控制 | 完整支援；CJA 會區分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hant) 產品管理員與用戶。只有產品管理員可以 <ul><li>建立/更新/刪除連線或資料檢視</li><li>更新/刪除其他使用者建立的專案、篩選或計算量度，以及</li><li>與所有使用者共用 Workspace 專案。</li></ul> |
| 虛擬報表套裝 | 完整支援；現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| VRS 元件策劃 | 完整支援；現在是資料檢視的一部分。 |

## 支援警告功能

| 功能 | 附註 |
| --- | --- |
| A4T | 透過 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)中的欄位提供支援。 |
| Classifications | 現在稱為「查閱資料集」。Analytics 中使用的分類可以使用 Analytics Classifications Data Connector 匯入至 Experience Platform 和 CJA。查閱資料集也可以直接上傳至 AEP，並在 CJA 中提供。 |
| 自訂工作階段化 | 支援除行動背景點擊以外的所有自訂工作階段化功能。 |
| 客戶屬性 | 現在稱為「描述檔資料集」，它們不會自動從 Experience Cloud 匯入，但必須上傳到 AEP，才能在 CJA 中使用。 |
| 日期範圍 | 支援所有日期範圍功能，但不包括自訂行事曆支援 (已在規劃中)。 |
| 裝置、瀏覽器、技術維度 | 當 AEP 資料集內含特定 XDM 結構欄位，並符合 XDM 體驗事件類別時，系統就會自動納入這些維度。 |
| 進入、退出及逗留的時間等維度和量度 | 系統可支援 (進入與退出現在稱為「工作階段開始」和「工作階段結束」)，不過計算方式稍有不同。 |
| eVar 持續性設定 | eVar 不再是 CJA 的一部分。不過持續性設定現在是資料檢視的一部分，可用於所有維度。請記得，持續性是依據報表時間處理，而非資料收集處理。「資料檢視」中設定的維度上限為 90 天的持續性，不支援無限制的持續性。 |
| GeoSegmentation 維度 | 收集到 Adobe Analytics 的所有 GeoSegmentation/地理位置都會透過 Analytics Data Connector 流入 CJA。未使用 Analytics Data Connector 的實作 (例如仰賴 AEP Web SDK 進行數位資料收集的實作) 將不會具有自動執行的完整地理位置查詢 (支援國家和州，但不支援城市和郵遞區號)。 |
| 行銷管道 | 行銷管道資料會透過 Analytics Data Connector 傳輸至 CJA。如果您是使用舊版 Adobe Analytics，仍需設定行銷管道規則。舊版未支援部分規則。如需詳細資訊，請參閱 [CJA 行銷管道文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant#cja-usecases)。 |
| 產品變數 | 在 Experience Platform 中，使用者可在資料集結構中使用物件類型欄位陣列，以符合此使用案例。在 CJA 中，客戶可以使用任何數量的產品變數，而且不會像 Adobe Analytics 受限於單一變數。 |
| 專案共用 | 專案共用功能僅支援在 CJA 的使用者之間使用 - CJA 與傳統 Analysis Workspace 之間不支援專案共用。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |

## 部分支援

| 功能 | 附註 |
| --- | --- |
| 機器人篩選 | 針對以 Analytics Data Connector (ADC)為基礎的資料集，系統會套用機器人篩選。[!UICONTROL Experience Platform] 或 CJA 不會針對其他資料集執行一般機器人篩選邏輯。 |
| Media Analytics | 媒體資料是 Analytics Data Connector 的一部分。 |
| 銷售 eVar | 如果銷售 eVar 未設定為使用持續性，則可使用物件陣列中的維度來達成銷售 eVar 的行為。目前，銷售維度持續性不可用。 |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援「區段比較」、「Analytics for Target」(A4T) 和「媒體同時檢閱者」面板。 |
| 處理規則 | 對於以 Analytics 資料連接器為基礎的資料集，仍會套用處理規則。 [Adobe Experience Platform 中的資料準備功能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)也可用來取代直接送到 Platform 的資料適用的處理規則。 |

## 目前不支援，但已列入規劃

| 功能 | 附註 |
| --- | --- |
| 警報 | 已規劃提供支援。 |
| 貢獻分析 | 已規劃提供支援。 |
| CSV 下載 | 已規劃提供支援。 |
| 自訂行事曆 | 已規劃提供支援。 |
| Data Warehouse 報表 (100% 列匯出) | 規劃從 Analysis Workspace 介面提供支援。[!UICONTROL Experience Platform 查詢服務]還為 CJA 這些使用案例提供一個介面。 |
| 透過裝置圖表進行 ID 彙整 | 已規劃提供支援。 |
| 量度重複資料刪除 | 已規劃提供支援。 |
| 銷售變數持續性 | 已規劃提供支援。 |
| 即時報表 | 已規劃提供支援。 |
| Report Builder (Excel 外掛程式) | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 區段發佈 (將區段從 Analysis Workspace 傳送至 Experience Cloud) | 已規劃提供支援。 |

## 尚未規劃提供支援

| 功能 | 附註 |
| --- | --- |
| Activity Map | 尚未規劃提供支援。 |
| Advertising Cloud | 尚未規劃提供支援。 |
| 分類規則產生器 | 尚未規劃提供支援。 |
| 資料摘要 | 尚未規劃提供支援。 |
| 摘要資料來源 | 尚未規劃提供支援。 |

## 永不受支援

* 使用 Cross-Device Coop 的人員量度
* Reports &amp; Analytics 控制面板
* Reports &amp; Analytics 書籤
* Reports &amp; Analytics 目標
* Reports &amp; Analytics 行事曆事件
* 行動服務
