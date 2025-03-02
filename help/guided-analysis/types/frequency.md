---
title: 頻率分析
description: 依照使用頻率來測量參與度。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 9%

---

# [!UICONTROL 頻率]分析 {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="頻率"
>abstract="檢視特定事件的重複使用者活動分佈。"

<!-- markdownlint-enable MD034 -->

![頻率](/help/assets/icons/Histogram.svg) **[!UICONTROL 頻率]**&#x200B;分析會依產品中發生事件的頻率來分組事件資料。 此分析的垂直軸包含代表事件頻率的貯體。 水平軸會測量每個時段的使用者或工作階段數量。

>[!VIDEO](https://video.tv.adobe.com/v/3428089/?quality=12&learn=on)

## 使用案例

此分析的使用案例包括：

* **參與**：追蹤參與使用者在您的產品中參與任何事件的情況。 您可以按一下長條圖的任何部分，將其儲存為區段。 低參與值區段的區段可協助您判斷使用者未以所需頻率與事件互動的原因。 高參與值區段的區段可協助您瞭解使用者為何經常與事件互動。 從那裡，您可以鼓勵其他使用者採取類似行為。
* **客戶忠誠度**：將事件設為「訂單」，並將量度設為「使用者」。 此分析可讓您依據使用者在指定日期範圍內在您的網站上購買次數，將使用者分組。
* **支援最佳化**：檢視使用者撥打的支援電話或未解決的案例數目，以深入瞭解哪些使用者遇到最多的問題。 然後，您可以建立區段來著重於他們的體驗，以協助識別並解決他們的問題。
* **訂閱服務**：參與度低的使用者更可能流失。 瞭解高度參與使用者的行為有助於鼓勵低參與使用者的類似行為，降低他們取消訂閱的可能性。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[趨勢](trends.md)之間切換。
* **[!UICONTROL 事件]**：您要測量的事件。每個選取的事件都會以個別的圖表呈現。 表格中會新增代表趨勢事件的列。 您最多可以包含五個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 使用者]、[!UICONTROL 工作階段]、[!UICONTROL 使用者百分比]和[!UICONTROL 工作階段百分比]。 此分析中百分比型量度的分母是執行所選事件的使用者或工作階段，而非產品的所有作用中使用者。
* **[!UICONTROL 區段]**：您要測量的區段。每個選取的區段都會將圖表中的橫條數和表格中的列數加倍。 您最多可以包含五個區段。

### 圖表設定

[!UICONTROL 頻率]分析提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 圖表型別]**：您要使用的視覺效果型別。 選項包括[!UICONTROL 橫條圖]和[!UICONTROL 棧疊橫條圖]。

### 分區設定

決定如何將事件分類為群組（貯體）。 在趨勢表格檢視中，使用者是根據總計的使用頻率以及在每個間隔中進行分組，這表示1個使用者可以在不同的間隔中計入不同的分組。

* **[!UICONTROL 自動貯體]**：根據資料分佈，自動識別最佳貯體大小。
* **[!UICONTROL 自訂值區]**：自訂將資料分組到值區的方式。
   * [!UICONTROL 從]：第一個貯體。 小於此值的頻率會從報表中排除。
   * [!UICONTROL 到]：大於此值的頻率會分組到最後一個貯體。
   * [!UICONTROL 大小]：貯體間隔。

### 時間比較

{{apply-time-comparison}}

### 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 圖表和表格預設會顯示彙總資料，並可以選擇將表格展開至趨勢檢視。 在趨勢檢視中，使用者是根據總計的使用頻率以及在每個間隔中分組的，這表示1個使用者可以在不同的間隔中計入不同的貯體。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
