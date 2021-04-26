---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
translation-type: tm+mt
source-git-commit: b149b4e95d8395c41242de7a2a3997315ba142a6
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 81%

---

# Customer Journey Analytics 功能支援

下表列出 Adobe Analytics 中支援、部分支援或不支援的 Customer Journey Analytics (CJA) 功能。這些清單會隨著 CJA 新增功能而變更。

## 完全支援的功能/元件

| Adobe Analytics 功能 | 支援說明事項 |
| --- | --- |
| 異常偵測 | 完全支援 |
| 歸因 IQ | 完全支援 |
| 計算量度 | 請注意，傳統 Analysis Workspace 中的任何現有計算量度都不會移植至 CJA。 |
| 跨裝置/跨管道彙整 | 請參閱[跨管道分析](/help/connections/cca/overview.md)。 |
| 日期比較 | 完全支援 |
| 日期範圍 | 已規劃提供自訂行事曆支援。 |
| 維度 | CJA 運用 XDM 並支援無限制維度，且不綁定傳統 Analytics 的自訂 eVar 或 prop。 |
| 內建 Analysis Workspace 維度 (例如瀏覽器類型、反向連結類型、作業系統等) | 只要填入基本 XDM 欄位 (例如使用者代理程式或裝置 ID)，CJA 就會以原生方式提供這些維度。客戶若有使用 Analytics Data Connector (ADC)，部分維度可供使用，但並非全部。請參閱[相關文件，了解可透過 ADC 支援的 Analytics 變數](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 刪除 GDPR | 請注意，現在系統已與 [!UICONTROL Adobe Experience Platform] 協調處理 GDPR - CJA 會繼承 [!UICONTROL Experience Platform] 對基礎資料集所做的所有資料變更。 |
| 清單變數/清單 Prop | CJA 運用 XDM 並支援無限字串陣列 (與 listVars 的用途類似)。 |
| 量度 | CJA 採用 Experience Data Model (XDM) 並支援不限數量的量度，且不綁定傳統 Analytics 的自訂成功事件。請注意，傳統 Analytics 的部分標準量度已重新命名：訪客 = 人員，造訪 = 工作階段，點擊 = 事件。 |
| PDF 匯出 | 完全支援 |
| 專案策劃 | 完全支援 |
| 專案連結 | 完全支援 |
| 報表時間處理功能 | CJA 僅依賴「報表時間處理」功能。 |
| 報表 API 存取 | 現在可使用[CJA API](https://www.adobe.io/cja-apis/docs/)使用。 |
| 排程報表/專案 | 完全支援 |
| 區段 | 現在稱為「篩選器」- 請注意，傳統 Analysis Workspace 中的任何現有區段都不會移植至 CJA。 |
| 使用者權限/資料存取控制 | CJA 可區分 Adobe Admin Console 產品管理員和使用者。只有產品管理員可以 1) 建立/更新/刪除連線或資料檢視；2) 更新/刪除其他使用者建立的專案、篩選器或計算量度；以及 3) 與所有使用者共用 Analysis Workspace 專案 |
| 虛擬報表套裝 | 現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| VRS 元件策劃 | 現在是資料檢視的一部分。 |

## 支援警告功能

| 功能 | 附註 |
| --- | --- |

|分類 |現在稱為「查閱資料集」。 Analytics 中使用的分類可以使用 Analytics Classifications Data Connector 匯入至 Experience Platform 和 CJA。查閱資料集也可以直接上傳至 AEP，並在 CJA 中提供。|
|自訂作業化 |支援除行動背景點擊以外的所有自訂作業化功能。 |
|客戶屬性 |現在稱為「描述檔資料集」，它們不會自動從Experience Cloud匯入，但必須先上傳到AEP，才能在CJA中使用。 |
|裝置、瀏覽器、技術維度 |當AEP資料集包含特定XDM架構欄位並符合XDM Experience Event類別時，會自動包含這些維度。 |
|登入點、退出點和逗留時間維度與量度 |支援（登入和退出現在稱為作業開始和作業結束），計算方式略有不同。 |
|eVar持久性設定 | eVar不再屬於CJA。 不過持續性設定現在是資料檢視的一部分，可用於所有維度。請記得，持續性是依據報表時間處理，而非資料收集處理。「資料檢視」中設定的維度上限為 90 天的持續性，不支援無限制的持續性。|
|行銷渠道 |行銷管道資料透過Analytics資料連接器流入CJA。 如果您是使用舊版 Adobe Analytics，仍需設定行銷管道規則。舊版未支援部分規則。如需詳細資訊，請參閱 [CJA 行銷管道文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant#cja-usecases)。|
|產品變數 |在Experience Platform中，使用者可以在資料集架構中使用物件類型欄位陣列，以符合此使用案例。 在 CJA 中，客戶可以使用任何數量的產品變數，而且不會像 Adobe Analytics 受限於單一變數。|
|專案共用 |專案共用僅在CJA使用者之間受支援- CJA與傳統Analysis Workspace之間不支援專案共用。 |
|視覺化 |除了地圖視覺化外，所有視覺化都受支援。 |

## 部分支援

| 功能 | 附註 |
| --- | --- |
| 機器人篩選 | 針對以 Analytics Data Connector (ADC)為基礎的資料集，系統會套用機器人篩選。[!UICONTROL Experience Platform] 或 CJA 不會針對其他資料集執行一般機器人篩選邏輯。 |
| Media Analytics | 媒體資料是 Analytics Data Connector 的一部分。 |
| 銷售 eVar | 如果銷售 eVar 未設定為使用持續性，則可使用物件陣列中的維度來達成銷售 eVar 的行為。目前，銷售維度持續性不可用。 |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援「區段比較」、「Analytics for Target」(A4T) 和「媒體同時檢閱者」面板。 |
| 處理規則 | 對於以 Analytics Data Connector 為基礎的資料集，仍會套用處理規則。 |

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
| A4T | 尚未規劃提供支援。 |
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
