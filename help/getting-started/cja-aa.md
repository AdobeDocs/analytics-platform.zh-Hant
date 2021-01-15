---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 87%

---


# Customer Journey Analytics 功能支援

下表列出 Adobe Analytics 中支援、部分支援或不支援的 Customer Journey Analytics (CJA) 功能。這些清單會隨著 CJA 新增功能而變更。

## 完全支援的功能/元件

| 功能 | 附註 |
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

## 支援警告功能

| 功能 | 附註 |
| --- | --- |
| 產品變數 | 產品變數目前可用於報告符合「體驗事件」結構的資料 (具體而言是使用 productListItems 物件)。 |
| 行銷管道 | 行銷管道資料現在會透過Analytics資料連接器流入CJA。 行銷渠道規則仍必須在傳統Adobe Analytics中設定。 不支援某些規則。 如需詳細資訊，請參閱[CJA行銷管道檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases)。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |
| 專案共用 | 專案共用功能僅支援在 CJA 的使用者之間使用 - CJA 與傳統 Analysis Workspace 之間不支援專案共用。 |
| 自訂工作階段化 | 支援除行動背景點擊以外的所有自訂工作階段化功能。 |
| eVar 持續性設定 | eVar 不再是 CJA 的一部分。不過持續性設定現在是資料檢視的一部分，可用於所有維度。請記得，持續性是依據報表時間處理，而非資料收集處理。這表示所有持續性都將以報表日期範圍為基礎，而非資料整體。 |
| 分類 | 現在稱為「查找資料集」，系統不會自動從傳統 Analytics 匯入這類資料集，必須先上傳至 AEP，才能在 CJA 中使用。 |
| 客戶屬性 | 現在稱為「設定檔資料集」，系統不會自動從 Experience Cloud 匯入這類資料集，但必須先上傳到 AEP，才能在 CJA 中使用。 |
| 裝置、瀏覽器、技術維度 | 當AEP資料集包含特定XDM架構欄位並符合XDM體驗事件類別時，會自動包含這些維度。 |
| 登入點、退出點和逗留時間維度與量度 | 支援（「登入與退出」現在稱為「作業開始」和「作業結束」），計算方式稍有不同。 |

## 部分支援

| 功能 | 附註 |
| --- | --- |
| 現成可用的 Analysis Workspace 維度 (例如瀏覽器類型、反向連結類型、行銷管道、造訪次數等) | CJA 不會以原生方式提供這些維度。客戶若有使用 Analytics Data Connector (ADC)，部分維度可供使用，但並非全部。請參閱[相關文件，了解可透過 ADC 支援的 Analytics 變數](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 面板 | 全面支援空白面板、歸因面板、自由表格面板和快速深入分析。不支援「區段比較」、「Analytics for Target」(A4T) 和「媒體同時檢閱者」面板。 |
| 銷售 eVar | 只有當銷售 eVar 和 ADC 型資料集嚴格遵循相同的 XDM 結構時，兩者才能搭配使用 (類似上述產品清單限制)。 |
| 機器人篩選 | 針對以 Analytics Data Connector (ADC)為基礎的資料集，系統會套用機器人篩選。[!UICONTROL Experience Platform] 或 CJA 不會針對其他資料集執行一般機器人篩選邏輯。 |
| 處理規則 | 針對以 ADC 為基礎的資料集，仍會套用處理規則。 |
| 跨裝置身分識別拼接 | 客戶受限於只能透過 Query Service 對資料執行「一次性」拼接，或目前必須在 [!UICONTROL Experience Platform] 資料內嵌前將此邏輯套用至資料。 |

## 目前不支援，但已列入規劃

| 功能 | 附註 |
| --- | --- |
| 貢獻分析 | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 區段發佈 (將區段從工作區傳送至 Experience Cloud) | 已規劃提供支援。 |
| CSV 下載 | 已規劃提供支援。 |
| 量度重複資料刪除 | 已規劃提供支援。 |
| 自訂行事曆 | 已規劃提供支援。 |
| 量度重複資料刪除 | 已規劃提供支援。 |
| 銷售變數永續性 | 已規劃提供支援。 |
| 排程報表/專案 | 已規劃提供支援。 |
| 警報 | 已規劃提供支援。 |
| 自訂行事曆 | 已規劃提供支援。 |
| PDF 匯出 | 已規劃提供支援。 |
| 報表 API 存取 | 已規劃提供支援 - 僅針對 API 2.0 提供。 |
| 透過裝置圖表進行 ID 拼接 | 已規劃提供支援。 |
| Report Builder (Excel 外掛程式) | 已規劃提供支援。 |
| 即時報表 | 已規劃提供支援。 |

## 尚未規劃提供支援

| 功能 | 附註 |
| --- | --- |
| A4T | 尚未規劃提供支援。 |
| Media Analytics | 尚未規劃提供支援。 |
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
