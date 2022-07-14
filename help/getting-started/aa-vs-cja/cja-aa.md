---
title: Customer Journey Analytics 功能支援
description: Customer Journey Analytics 功能與 Adobe Analytics 功能集的比較。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 434695e87a0b342da9c17c94b93e0253cf1e621e
workflow-type: tm+mt
source-wordcount: '1399'
ht-degree: 100%

---

# Customer Journey Analytics 功能支援

下表列出 Adobe Analytics 中支援、部分支援或不支援的 Customer Journey Analytics (CJA) 功能。 這些清單會隨著 CJA 新增功能而變更。

## 完整支援的功能/元件

| Adobe Analytics 功能 | 支援說明事項 |
| --- | --- |
| 異常偵測 | 完整支援 |
| Attribution IQ | 完整支援 |
| 計算量度 | 完整支援；請注意，在傳統 Analysis Workspace 中任何現有的計算量度將不會移前往 CJA。 |
| 行事曆事件 | 完整支援。 已將行事曆活動實作為工作區內的[註解](/help/components/annotations/overview.md)。 |
| 分類規則產生器 | 完整支援。已呼叫 CJA 中的[字子串](/help/data-views/component-settings/substring.md)。 在報表時間使用字串操控，而不是查詢資料集。 |
| 跨裝置/跨管道拼接 | 完整支援；請參閱[跨管道分析](/help/connections/cca/overview.md)。 |
| CSV 下載 | 完整支援 |
| 自訂行事曆 | 完整支援 |
| 日期比較 | 完整支援 |
| 日期範圍 | 所有資料範圍功能都受到支援。 |
| 日光節約時間 | 完整支援 |
| 裝置、瀏覽器、推薦者、技術維度 | 當 AEP 資料集內含特定 XDM 結構描述欄位，並符合 XDM 體驗事件類別時，系統就會自動納入這些維度。 請參閱我們的[文件，了解透過 ADC 支援的 Analytics 變數](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant)。<p>如果您未使用 Adobe 來源連接器將資料從 Adobe Analytics 填入到 CJA，而是使用 Experience Platform Web SDK 資料彙集，目前不支援根據裝置查詢的裝置和維度。 但我們很快將支援這些裝置和維度。 |
| 維度 | 完整支援；CJA 運用 XDM 並支援無限制維度。 CJA 並未繫結到傳統 Adobe Analytics 的自訂 eVars 或 props。 |
| 刪除 GDPR | 完整支援；請注意 GDPR 目前是協同 [!UICONTROL Adobe Experience Platform] 處理。 CJA 會繼承 [!UICONTROL Experience Platform] 對基礎資料集所做的任何資料變更。 |
| 清單變數/清單 Prop | 完整資源；CJA 運用 XDM 並支援使用方式與 listVars 相似的無限制字串陣列。 |
| 銷售變數持續性 | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=zh-Hant#binding-dimension)提供完整支援 |
| 銷售 eVar | 透過[繫結維度和繫結量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供完整支援 |
| 量度 | 完整支援；CJA 運用 Experience Data Model (XDM) 並支援無限制的量度，且未繫結到傳統 Analytics 的自訂成功事件。 請注意，傳統 Analytics 的部分標準量度已重新命名：訪客 = 人員，造訪 = 工作階段，點擊 = 事件。 |
| 量度重複資料刪除 | 完整支援 |
| 行動計分卡/儀表板 | 完整支援 |
| 面板 | 空白面板、歸因面板、自由表格面板和快速深入分析全都受到支援。 |
| 匯出 PDF | 完整支援 |
| 專案策劃 | 完整支援 |
| 專案連結 | 完整支援 |
| Report Builder (Excel 外掛程式) | 完整支援 |
| 報告時間處理 | 完整支援；CJA 僅仰賴報告時間處理。 |
| 報告 API 存取權 | 完整支援；透過 [CJA API](https://www.adobe.io/cja-apis/docs/) 提供。 |
| 排程報告/專案 | 完整支援 |
| 區段 | 完整支援；現在稱為「篩選器」- 請注意，在傳統 Analysis Workspace 中任何現有的區段將不會移前往 CJA。 |
| 使用者權限/資料存取控制 | 完整支援；CJA 會區分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hant) 產品管理員與使用者。 只有產品管理員可以 <ul><li>建立/更新/刪除連線或資料檢視</li><li>更新/刪除其他使用者建立的專案、篩選或計算量度，以及</li><li>與所有使用者共用「工作區」專案。</li></ul> |
| 虛擬報告套裝 | 完整支援；現在稱為[資料檢視](/help/data-views/create-dataview.md)。 |
| VRS 元件策劃 | 完整支援；現在是資料檢視的一部分。 |

{style="table-layout:auto"}

## 支援警告功能

| 功能 | 附註 |
| --- | --- |
| A4T | 透過 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)中的欄位提供支援。 |
| Classifications | 現在稱為「查閱資料集」。 Analytics 中使用的分類，可以使用 Analytics 分類來源連接器匯入至 Experience Platform 和 CJA。 查閱資料集也可以直接上傳至 AEP，並在 CJA 中提供。 |
| 自訂工作階段化 | 支援所有自訂工作階段化功能，行動背景點擊除外。 |
| 客戶屬性 | 現在稱為「描述檔資料集」，它們不會自動從 Experience Cloud 匯入，但必須上傳到 AEP，才能在 CJA 中使用。 |
| [!UICONTROL 裝置]、[!UICONTROL 瀏覽器]、[!UICONTROL 推薦者]、[!UICONTROL 技術]維度 | 當 AEP 資料集內含特定 XDM 結構描述欄位，並符合 XDM 體驗事件類別時，系統就會自動納入這些維度。 請參閱[相關文件，了解可透過 Analytics 來源連接器支援的 Analytics 變數](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hant)。 對於未使用來源連接器將資料從 Adobe Analytics 填入到 CJA，而是使用 AEP Web SDK 資料收集的 CJA 客戶，目前不支援[!UICONTROL 裝置]和基於裝置查詢的維度，但將在不久的未來予以支援。 |
| 進入、退出及逗留的時間等維度和量度 | 系統可支援 (進入與退出現在稱為「工作階段開始」和「工作階段結束」)，不過計算方式稍有不同。 |
| eVar 持續性設定 | eVar 不再是 CJA 的一部分。 不過持續性設定現在是資料檢視的一部分，可用於所有維度。 請記得，持續性是依據報表時間處理，而非資料收集處理。 「資料檢視」中設定的維度上限為 90 天的持續性，不支援無限制的持續性。 |
| GeoSegmentation 維度 | 收集到 Adobe Analytics 的所有 GeoSegmentation/地理位置都會透過 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)流入 CJA。 未使用 Analytics 來源連接器的實作 (例如仰賴 AEP Web SDK 進行數位資料收集的實作) 將不會具有自動執行的完整地理位置查詢：支援國家/地區和美國州別，但不支援城市和郵遞區號。 |
| 行銷頻道 | 行銷頻道資料會透過 Analytics 來源連接器傳輸至 CJA。 如果您是使用舊版 Adobe Analytics，仍需設定行銷管道規則。 舊版未支援部分規則。 如需詳細資訊，請參閱 [CJA 行銷管道文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hant#cja-usecases)。 |
| 產品變數 | 在 Experience Platform 中，使用者可在資料集結構描述中使用物件類型欄位陣列，以符合此使用案例。 在 CJA 中，客戶可以使用任意數量的產品變數，且不限於 Adobe Analytics 中的單一變數。 |
| 專案共用 | 專案共用功能僅支援在 CJA 的使用者之間使用 - CJA 與傳統 Analysis Workspace 之間不支援專案共用。 |
| 視覺效果 | 支援所有視覺效果，但地圖視覺效果除外。 |

{style="table-layout:auto"}

## 部分支援

| 功能 | 附註 |
| --- | --- |
| 機器人篩選 | 對於以 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)為基礎的資料集，則會套用機器人篩選。 [!UICONTROL Experience Platform] 或 CJA 不會執行其他資料集的一般機器人篩選邏輯。 |
| 面板 | 空白面板、歸因面板、自由表格面板和快速深入分析全都受到支援。 不支援「區段比較」、「Analytics for Target」(A4T) 和「媒體同時檢閱者」面板。 |
| 處理規則 | 對於以 Analytics 來源連接器為基礎的資料集，仍會套用處理規則。 [Adobe Experience Platform 中的資料準備功能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)也可用來取代直接送到 Platform 的資料適用的處理規則。 |
| 串流 Media Analytics | 媒體資料是 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)的一部分。 |

{style="table-layout:auto"}

## 目前不支援，但已列入規劃

| 功能 | 附註 |
| --- | --- |
| 警報 | 已規劃提供支援。 |
| 貢獻分析 | 已規劃提供支援。 |
| Data Warehouse 報表 (100% 列匯出) | 規劃從 Analysis Workspace 介面提供支援。 Adobe Experience Platform [[!UICONTROL 查詢服務]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant)也會提供適用於在 CJA 中這些使用案例的介面。 |
| 透過裝置圖表進行 ID 拼接 | 已規劃提供支援。 |
| 提升度和可信度報告 | 已規劃提供支援。 |
| 處理規則、VISTA 規則、行銷頻道處理規則 | 已規劃提供支援，但將在查詢時運作 (而不是在資料收集期間)，以達成更靈活、可回溯、非破壞性的資料操控。 |
| 專案範本 | 已規劃提供支援。 |
| 即時報表 | 已規劃提供支援。 |
| 區段 IQ | 已規劃提供支援。 |
| 新的與重複工作階段報告 | 已規劃提供支援，但有一些考量。 |

{style="table-layout:auto"}

## 尚未規劃提供支援

| 功能 | 附註 |
| --- | --- |
| Activity Map | 尚未規劃提供支援。 |
| Advertising Cloud | 尚未規劃提供支援。 |
| 貨幣轉換 | 尚未規劃提供支援。 |
| 資料摘要 | 尚未規劃提供支援。 |
| 摘要資料來源 | 尚未規劃提供支援。 |
| 交易 ID 資料來源 | 尚未規劃提供支援。 |

{style="table-layout:auto"}

## 永遠不提供支援

* 使用 Cross-Device Coop 的人員量度
* Reports &amp; Analytics 儀表板
* Reports &amp; Analytics 書籤
* Reports &amp; Analytics 目標
* 行動服務
