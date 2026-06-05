---
title: 母體報表總數
description: 在Customer Journey Analytics中使用母體總計報告來分析資料集中的設定檔和帳戶，不受事件活動或面板日期範圍影響。
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 774ac76b0a49d8172b31dc97563c13debb0858a7
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---


# 母體報表總數

母體總計報表可讓您分析和報告設定檔和查詢資料集中定義的實體，並超越事件資料集中以時間為基礎的事件序列。 此功能可啟用新類別的查詢、量度和對象定義，以反映企業客戶群的完整範圍。

Customer Journey Analytics是圍繞事件建置的。 每個量度、每個視覺效果、每個面板、每個報表都錨定至一個日期時間範圍，以及該日期時間範圍內發生的事件。 您可以提出解決方案的問題，例如：

| 問題 | 事件 | 日期時間範圍 |
|---|---|---|
| 上週有多少人購買產品？ | 購買 | 上週 |
| 第1季有多少帳戶造訪定價頁面？ | 造訪 | Q1 |

工作區面板的日期時間範圍會篩選資料，而您的維度和量度會說明在該日期時間範圍中發生的事情。

但並非您的企業需要回答的所有問題都與所發生的事件有關。 有時您需要瞭解母體本身。

| 問題 | 事件 | 日期時間範圍 |
|---|---|---|
| 我們現在有多少活躍客戶？ | 不適用 | 不適用 |
| 我們的資料庫中有多少帳戶？ | 不適用 | 不適用 |
| 有多少會員在過去30天內未購買產品？ | 不適用 | 過去30天 |

這些問題與事件無關，而是關於存在的人和帳戶，無論這些人或帳戶最近是否做過任何事。

總母體報表引入了一類新的量度，用於報表設定檔資料。 設定檔資料集中可能包含人員和帳戶，該設定檔資料與面板的日期範圍無關。 有了總母體報表，您可以將母體型量度和事件型量度混合納入相同的分析中，更全面地瞭解您的客戶身分和客戶所做的事。

母體總計報表可讓Customer Journey Analytics針對設定檔和查詢資料集中定義的所有實體製作報表，而不論事件活動為何。 此報告包括：

* **以設定檔為基礎的查詢**：分析設定檔的屬性（無論事件為何） （所有人員、帳戶、商機及購買群組）。
* **設定檔減事件查詢**：識別在報告期間未執行特定動作或體驗的設定檔（所有人員、帳戶、商機及購買群組）。
* **共用的查詢**：支援在多個實體間重複使用查詢資料集，以降低擷取成本並改善效能。

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## 母體報表量度總數

母體總計報表量度的行為與Customer Journey Analytics中通常使用的量度不同：

* 母體報表量度總計未繫結至面板日期範圍。 總母體報表量度(例如&#x200B;**[!UICONTROL 總人數（設定檔）]**)會從您的設定檔資料集傳回目前母體，無論套用至面板的日期範圍為何。 日期篩選器和日期範圍比較不會像這些篩選器和比較影響事件量度那樣影響母體報表量度總計。
* 總體母體報表需要連線上的設定檔資料集。 只有當您的連線包含至少一個設定檔資料集以及至少一個事件資料集時，總母體報表量度才會出現。 只有事件資料集的連線仍舊與之前完全相同，不會顯示母體報告量度總計。

在Workspace中，總人口量度會以不重複圖示(TBD)標示，以便您快速識別哪些量度會遵循面板的日期範圍，哪些量度不會。 在大多數地方，母體總數量度可以和事件量度一起使用，但是相依於事件序列的視覺效果型別（例如流失和流量）不受支援。

### 標準總母體報表量度

依預設，系統包含三個標準的總人口報告量度，可用於連線包含設定檔資料集的任何資料檢視：

* **總人數（設定檔）**：設定檔資料集中的總人數。
* **帳戶總數（設定檔）**：設定檔資料集中的帳戶總數。 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **總人數（設定檔+事件）**：結合設定檔範圍人員與事件範圍人員的聯合計數。

您也可以使用設定檔資料集中的欄位，以這三個範圍的任何一個建立自訂量度。

## 需求、必要條件和考量事項

為了讓總母體報表正常運作，應考量先決條件、需求及考量事項。

### 連線需求

若要使用連線來支援總母體報表：

* 連線至少需要一個事件資料集。 不支援僅設定檔連線。
* 必須至少將一個設定檔資料集新增到連線。 在只包含事件資料的連線上建置的資料檢視中，總母體報表量度不會顯示。
* 必須為每個設定檔資料集設定共用查詢。 共用查閱會指定比對索引鍵、名稱空間（適用於身分對應欄位）和聯結路徑，藉此定義如何將每個設定檔資料集聯結至您連線中的事件。

#### 設定檔資料集組態

將設定檔資料集新增至連線時，Customer Journey Analytics會根據資料集型別填入預設的共用查詢設定：

* 針對人員設定檔資料集：預設為依容器比對設為[!UICONTROL 人員]，以身分對應作為索引鍵欄位。 您可以編輯此預設值。 例如，從身分對應中選擇特定的名稱空間，而不是主索引鍵。 或者，指定第二個名稱空間，用於未填入第一個名稱空間的情況（與拼接資料集很常見）。
* 帳戶設定檔資料集[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：預設值是依容器比對，設定為[!UICONTROL 帳戶] （或者[!UICONTROL 全域帳戶]，如果連線已啟用全域帳戶）。 帳戶欄位可以是單一識別碼或身分對應。 當帳戶欄位為身分對應時，請選取要使用的名稱空間。

您可以在單一設定檔資料集上設定多個共用查詢，以支援事件的多個聯結路徑。 當跨多個共用查閱將相同的身分對應用作關鍵欄位時，名稱空間選擇必須一致。

### 資料檢視需求

若要讓總母體報表量度在資料檢視上正常運作：

* 連線必須包含設定檔資料集（請參閱[連線需求](#connection-requirements)）。 如果您從連線中移除最後剩餘的設定檔資料集，則從其中建立的資料檢視將無法使用母體總計報告量度。
* [資料檢視層級區段](/help/data-views/create-dataview.md#settings-segments)不能是事件明確的。 如果直接套用至資料檢視的區段完全是以事件範圍的條件（例如，`hit where page = X`）來定義，則無法在該資料檢視上產生母體總計報表。 在依賴母體總計報表量度之前，請先驗證任何資料檢視層級區段是否與設定檔範圍報表相容。
* 量度範圍必須正確設定。 在資料檢視產生器中建立自訂量度元件時，請根據欄位的資料集以及您想要量度的行為方式，選取適當的範圍（事件、設定檔或設定檔+事件）。 在對象或循環報表中使用量度後，如果不破壞這些相依性，就無法變更範圍。

### Workspace相容性

總母體報表量度可與大部分Workspace內容中的事件型量度搭配使用： [自由格式表格](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)、[行](/help/analysis-workspace/visualizations/line.md)、[橫條](/help/analysis-workspace/visualizations/bar.md)和[水準橫條](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果、[同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) （設定適當時）等。 有幾個視覺效果型別不受支援，因為它們原本就相依於事件順序：

* [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [流量](/help/analysis-workspace/visualizations/c-flow/flow.md)
* 其他不受支援的視覺效果型別，需要在發佈前確認。

當您將總母體報表量度新增到不受支援的視覺效果時，Workspace會指出該量度無法用於該內容。

### 對象考量事項

以總母體報表量度建立的對象取決於資料檢視中剩餘的量度：

* 如果從資料檢視中移除總母體報表量度，使用總母體報表量度的循環對象會失敗並移至「錯誤」狀態。
* Customer Journey Analytics介面可防止移除量度，而任何作用中的循環對象都取決於量度，且在您確認移除之前，會針對相依性顯示指引。

### 權限

待確認：在總母體報表量度可見之前，需先瞭解客戶IMS組織或產品設定檔的任何角色或功能存取需求。 值得在發佈前標幟到PM。
