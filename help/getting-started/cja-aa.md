---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
translation-type: tm+mt
source-git-commit: c70662468126279110f14291c135a3f60dd919db
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 75%

---


# Customer Journey Analytics 功能支援

下表列出 Adobe Analytics 中支援、部分支援或不支援的 Customer Journey Analytics (CJA) 功能。這些清單會隨著 CJA 新增功能而變更。

## 完全支援的功能/元件

| Adobe Analytics功能 | 附註 |
| --- | --- |
| 量度 | CJA 採用 Experience Data Model (XDM) 並支援不限數量的量度，且不會與傳統 Analytics 的自訂成功事件繫結。請注意，傳統 Analytics 的部分標準量度已重新命名：訪客 = 人員，造訪 = 工作階段，點擊 = 事件。 |
| 維度 | CJA 採用 XDM 並支援不限數量的維度，且不會與傳統 Analytics 的自訂成功事件繫結。 |
| 清單變數/清單 Prop | CJA 採用 XDM 並支援不限數量的清單變數 |
| 日期範圍 | 已規劃提供自訂行事曆支援。 |
| 計算量度 | 請注意，傳統 Analysis Workspace 中的任何現有計算量度都不會移植至 CJA。 |
| 區段 | 現在稱為「篩選器」- 請注意，傳統 Analysis Workspace 中的任何現有區段都不會移植至 CJA。 |
| 異常偵測 | 完全支援 |
| 歸因 IQ | 完全支援 |
| 專案策劃 | 完全支援 |
| 專案連結 | 完全支援 |
| 日期比較 | 完全支援 |
| 虛擬報表套裝 | 現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| VRS 元件策劃 | 現在是資料檢視的一部分。 |
| 報表時間處理功能 | CJA 僅依賴「報表時間處理」功能。 |
| 刪除 GDPR | 請注意，GDPR現在與[!UICONTROL Adobe Experience Platform]協作處理- CJA繼承[!UICONTROL Experience Platform]對基礎資料集所做的資料變更。 |
| 使用者權限/資料存取控制 | CJA 可區分 Adobe Admin Console 產品管理員和使用者。只有產品管理員可以 1) 建立/更新/刪除連線或資料檢視；2) 更新/刪除其他使用者建立的專案、篩選器或計算量度；以及 3) 與所有使用者共用 Analysis Workspace 專案 |
| 立即可用的分析工作區維度（例如瀏覽器類型、反向連結類型、作業系統等） | 只要填入基本XDM欄位（例如使用者代理或裝置ID）,CJA就會以原生方式提供這些維度。 客戶若有使用 Analytics Data Connector (ADC)，部分維度可供使用，但並非全部。請參閱[相關文件，了解可透過 ADC 支援的 Analytics 變數](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 報表 API 存取 | 目前可使用Analytics API 2.0。 |

## 支援警告功能

| 功能 | 附註 |
| --- | --- |
| 產品變數 | 在Experience Platform中，使用者可在資料集架構中使用物件類型欄位陣列，以符合此使用案例。 在CJA中，客戶可以使用任何數量的產品變數，而且不會像Adobe Analytics中那樣限制為單一變數。 |
| 行銷管道 | 行銷管道資料透過Analytics資料連接器流入CJA。 如果您是使用舊版 Adobe Analytics，仍需設定行銷管道規則。舊版未支援部分規則。如需詳細資訊，請參閱 [CJA 行銷管道文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant#cja-usecases)。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |
| 專案共用 | 專案共用功能僅支援在 CJA 的使用者之間使用 - CJA 與傳統 Analysis Workspace 之間不支援專案共用。 |
| 自訂工作階段化 | 支援除行動背景點擊以外的所有自訂工作階段化功能。 |
| eVar 持續性設定 | eVar 不再是 CJA 的一部分。不過持續性設定現在是資料檢視的一部分，可用於所有維度。請記得，持續性是依據報表時間處理，而非資料收集處理。「資料檢視」中設定的維度上限為90天的永續性，不支援無限制的永續性。 |
| Classifications | 現在稱為「查閱資料集」。 Analytics中使用的分類可以使用Analytics分類資料連接器匯入至Experience Platform和CJA。 查閱資料集也可以直接上傳至AEP，並在CJA中提供。 |
| 客戶屬性 | 現在稱為「設定檔資料集」，系統不會自動從 Experience Cloud 匯入這類資料集，但必須先上傳到 AEP，才能在 CJA 中使用。 |
| 裝置、瀏覽器、技術維度 | 當 AEP 資料集內含特定 XDM 結構欄位，並符合 XDM 體驗事件類別時，系統就會自動納入這些維度。 |
| 登入、退出和逗留時間維度與量度 | 系統可支援 (「登入與退出」現在稱為「工作階段開始」和「工作階段結束」)，不過計算方式稍有不同。 |

## 部分支援

| 功能 | 附註 |
| --- | --- |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援「區段比較」、「Analytics for Target」(A4T) 和「媒體同時檢閱者」面板。 |
| 銷售 eVar | 如果銷售eVar未設定為使用永續性，則可使用物件陣列中的維度來達成銷售eVar的行為。 目前，銷售維度永續性不可用。 |
| 機器人篩選 | 針對以 Analytics Data Connector (ADC)為基礎的資料集，系統會套用機器人篩選。[!UICONTROL Experience Platform] 或 CJA 不會針對其他資料集執行一般機器人篩選邏輯。 |
| 處理規則 | 針對以 ADC 為基礎的資料集，仍會套用處理規則。 |
| 跨裝置身分識別彙整 | CJA支援持續進行跨裝置、跨通道身分拼接，包括定期重述歷史資料。 目前，您只能搭配使用單一客戶集身分和單一Cookie ID來完成此作業。 |
| Media Analytics | 媒體資料是Analytics資料連接器的一部分。 |

## 目前不支援，但已列入規劃

| 功能 | 附註 |
| --- | --- |
| 貢獻分析 | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 區段發佈 (將區段從 Analysis Workspace 傳送至 Experience Cloud) | 已規劃提供支援。 |
| CSV 下載 | 已規劃提供支援。 |
| 自訂行事曆 | 已規劃提供支援。 |
| 量度重複資料刪除 | 已規劃提供支援。 |
| 銷售變數持續性 | 已規劃提供支援。 |
| 排程報表/專案 | 已規劃提供支援。 |
| 警報 | 已規劃提供支援。 |
| PDF 匯出 | 已規劃提供支援。 |
| 透過裝置圖表進行 ID 彙整 | 已規劃提供支援。 |
| Report Builder (Excel 外掛程式) | 已規劃提供支援。 |
| 即時報表 | 已規劃提供支援。 |

## 尚未規劃提供支援

| 功能 | 附註 |
| --- | --- |
| A4T | 尚未規劃提供支援。 |
| Advertising Cloud | 尚未規劃提供支援。 |
| Activity Map | 尚未規劃提供支援。 |
| 分類規則產生器 | 尚未規劃提供支援。 |
| 摘要資料來源 | 尚未規劃提供支援。 |

## 永不受支援

* 使用 Cross-Device Coop 的人員量度
* Reports &amp; Analytics 控制面板
* Reports &amp; Analytics 書籤
* Reports &amp; Analytics 目標
* Reports &amp; Analytics 行事曆事件
* Ad Hoc Analysis
* Data Warehouse 報告 - [!UICONTROL Experience Platform Query Service] 會是 CJA 中這些使用案例的新介面。
* Mobile Services
* 資料饋送
