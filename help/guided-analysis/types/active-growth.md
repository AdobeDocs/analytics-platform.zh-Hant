---
title: 主動式成長分析
description: 識別哪些使用者是新的、保留的、回訪的或非活躍的。
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 7%

---

# [!UICONTROL 積極成長]分析 {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="積極成長"
>abstract="識別哪些使用者是新的、保留的、回訪的或非活躍的。"

<!-- markdownlint-enable MD034 -->


![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL 主動成長]**&#x200B;分析可提供特定期間使用者成長與贏取的相關資訊。 水平軸是時間間隔，而垂直軸是使用者的測量值。 使用者分為四個類別：

* **[!UICONTROL 新]**：使用者在目前期間處於作用中狀態，但先前未啟用。 將游標移至圖表圖例中的&#x200B;_[!UICONTROL 新使用者]_&#x200B;上方，檢視分析回顧的距離。 回顧範圍會根據選取的日期範圍和間隔動態決定。
* **[!UICONTROL Repeat]**：使用者在目前與上一個時段處於作用中狀態。
* **[!UICONTROL Return]**：使用者在目前時段處於作用中狀態，在先前時段未處於作用中狀態，但在某個時間點之前處於作用中狀態。 在圖表圖例中，將游標移至&#x200B;_[!UICONTROL 回訪使用者]_&#x200B;上方，檢視分析回溯的距離。 回顧範圍會根據選取的日期範圍和間隔動態決定。
* **[!UICONTROL 休眠]**：使用者在上一個時段處於作用中狀態，但在目前時段未處於作用中狀態。 休眠使用者不計入作用中使用者總數。

所有作用中的使用者（新的+重複+返回）會以藍綠色顯示在水平軸上方，而所有休眠的使用者會以橘色顯示在水平軸下方。


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## 使用案例

此分析的使用案例包括：

* **使用者保留率和流失率：**&#x200B;提供高或低使用者保留率的明確視覺效果。 瞭解這些高保留率或低保留率期間，有助於您做出產品決策，以鼓勵高保留率或協助將流失降至最低。
* **行銷活動評估**：檢視特定行銷活動可協助您瞭解它產生了多少流量，以及它協助使用者維持參與的程度。
* **使用者生命週期分析**：分析使用者在整個生命週期中的作用中使用者成長，有助於識別使用者參與度下降的特定階段。 例如，如果個人在入門階段有很高的休眠使用者比例，這可能表示可用性問題或需要更好的產品內指南。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析與[淨增長](net-growth.md)之間切換。
* **[!UICONTROL 事件]**：您要測量的事件。 由於此分析是以使用者為基礎，在期間內與事件互動一次的使用者會計為作用中使用者。 您可以在查詢中包含一個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 使用者數目]和[!UICONTROL 使用者百分比]。
* **[!UICONTROL 區段]**：您用來篩選資料的區段。 您可以在查詢中包含一個區段。

### 圖表設定

[!UICONTROL 作用中成長]分析提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 圖表型別]**：您要使用的視覺效果型別。 選項包括[!UICONTROL 棧疊長條圖]和[!UICONTROL 棧疊區域圖]。

### 時間比較

{{apply-time-comparison}}

### 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 有效的選項包括每小時、每日、每週、每月和每季。 相同日期範圍可以有不同的間隔，這會影響圖表中的資料點數以及表格中的欄數。 例如，以每日詳細程度檢視橫跨3天的分析只會顯示3個資料點，而以每小時詳細程度橫跨3天的分析則會顯示72個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
