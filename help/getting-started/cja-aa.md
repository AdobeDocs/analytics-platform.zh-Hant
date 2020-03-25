---
title: 客戶歷程分析功能支援
description: 客戶歷程分析功能與Adobe Analytics功能集的比較。
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# 客戶歷程分析功能支援

下表列出Adobe Analytics中支援、部分支援或不支援的Customer Journey Analytics(CJA)功能。 隨著功能新增至CJA，這些清單會隨著時間而變更。

## 完全支援的功能／元件

| 功能 | 附註 |
| --- | --- |
| 量度 | CJA運用體驗資料模型(XDM)並支援無限制的量度，且不會與傳統Analytics的自訂成功事件相關聯。 請注意，部分標準量度已從傳統Analytics重新命名：訪客=人員、瀏覽=工作階段、點擊=事件。 |
| 維度 | CJA運用XDM並支援無限制的維度，且不會與傳統Analytics的自訂成功事件相關聯。 |
| 清單變數／清單Prop | CJA運用XDM並支援不限數量的清單變數 |
| 日期範圍 | 已計畫自訂日曆支援。 |
| 計算量度 | 請注意，傳統分析工作區中的任何現有計算量度都不會移植至CJA。 |
| 區段 | 現在稱為「篩選」-請注意，傳統分析工作區中的任何現有區段都不會移植至CJA。 |
| 歸因 IQ | 完整支援 |
| 專案組織 | 完整支援 |
| 專案連結 | 完整支援 |
| 日期比較 | 完整支援 |
| 虛擬報表套裝 | 現在稱為 [資料檢視](/help/data-views/create-dataview.md)。 |
| VRS元件組織 | 現在是資料檢視的一部分。 |
| 報表時間處理 | CJA完全依賴「報表時間處理」。 |
| 刪除GDPR | 請注意，GDPR現在與Adobe Experience Platform協作處理- CJA繼承了Experience Platform對基礎資料集所做的任何資料變更。 |

## 支援多項注意事項

| 功能 | 附註 |
| --- | --- |
| 產品變數 | 產品變數目前可用於報告符合「體驗事件」架構的資料（特別是使用productListItems物件）。 |
| 視覺效果 | 除了地圖視覺化外，所有視覺化都受支援。 |
| AAM觀眾 | 如果客戶使用Analytics Data Connector資料集，此資料將是ADC資料的一部分。 |
| 專案共用 | 專案共用僅在CJA的使用者之間受支援- CJA與傳統分析工作區之間不支援專案共用。 |
| 自訂作業化 | 支援除行動背景點擊以外的所有自訂作業化功能。 |
| eVar永續性設定 | eVar不再是CJA的一部分。 不過，永續性設定現在是「資料檢視」的一部分，可用於所有維度。 請記住，永續性是以報告時間處理為基礎，而非資料收集處理。 這表示所有持續性都將以報告日期範圍為基礎，而非整個資料。 |
| 分類 | 現在稱為「查閱資料集」，不會自動從傳統Analytics匯入。 在CJA中提供之前，必須先上傳至AEP。 |
| 客戶屬性 | 現在稱為「描述檔資料集」，它們不會自動從Experience Cloud匯入，但必須先上傳到AEP，才能在CJA中使用。 |

## 部分支援

| 功能 | 附註 |
| --- | --- |
| 立即可用的分析工作區維度（例如瀏覽器類型、反向連結類型、行銷管道、瀏覽次數等） | CJA不以原生方式提供這些維度。 對於使用Analytics資料連接器(ADC)的客戶，有些維度是可用的，但並非全部。 請參閱我們的文 [件，其中Analytics變數可透過ADC獲得支援](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 面板 | 完全支援空白麵板、歸因面板和自由面板。 不支援區段比較。 |
| 銷售eVar | 銷售eVar只能與ADC型資料集搭配使用，除非它們嚴格符合相同的XDM架構（類似上述產品清單限制）。 |
| 機器人篩選 | 針對以Analytics Data Connector(ADC)為基礎的資料集，會套用機器人篩選。 其他資料集的一般機器人篩選邏輯不由Experience Platform或CJA執行。 |
| 處理規則 | 對於基於ADC的資料集，仍然應用處理規則。 |
| 跨裝置身分識別接合 | 客戶只能透過查詢服務「一次性」接線資料，或目前必須在Experience Platform資料擷取前將此邏輯套用至資料。 |

## 目前不支援，但已規劃

| 功能 | 附註 |
| --- | --- |
| 異常偵測 | 已計畫提供支援。 |
| 貢獻分析 | 已計畫提供支援。 |
| 區段 IQ | 已計畫提供支援。 |
| 區段發佈（從工作區傳送區段至Experience Cloud） | 已計畫提供支援。 |
| 使用者權限／資料存取控制 | CJA中的所有使用者都有相同的存取控制項——這表示所有使用者都可存取所有連線、資料檢視等。 基本上，所有使用者都是CJA中的管理員層級使用者。 計畫於2020年提供支援。 |
| CSV下載 | 已計畫提供支援。 |
| 排程報表／專案 | 已計畫提供支援。 |
| 警報 | 已計畫提供支援。 |
| 自訂日曆 | 已計畫提供支援。 |
| 行銷管道 | 已計畫提供支援。 |
| PDF匯出 | 已計畫提供支援。 |
| 報告API存取 | 已計畫提供支援——只有API 2.0才提供。 |
| 透過裝置圖形進行ID拼接 | 已計畫提供支援。 |

## 尚未計畫支援

| 功能 | 附註 |
| --- | --- |
| A4T | 尚未計畫提供支援。 |
| Video Analytics | 尚未計畫提供支援。 |
| Advertising Cloud | 尚未計畫提供支援。 |
| 報告建立工具（Excel外掛程式） | 尚未計畫提供支援。 |
| Activity Map | 尚未計畫提供支援。 |
| 分類規則產生器 | 尚未計畫提供支援。 |
| 摘要資料來源 | 尚未計畫提供支援。 |
| 即時報告 | 尚未計畫提供支援。 |

## 將不受支援

| 功能 | 附註 |
| --- | --- |
| 使用跨裝置合作基金的人員量度 |  |
| 報告與分析控制面板 |  |
| 報告與分析書籤 |  |
| 報告與分析目標 |  |
| 報告與分析日曆事件 |  |
| Ad Hoc Analysis |  |
| Data Warehouse 報表 | Adobe Experience Platform Query Service將是CJA中這些使用案例的新介面。 |
| Mobile Services |  |
| 資料摘要 |  |
