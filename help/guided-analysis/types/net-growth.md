---
title: 淨成長分析
description: 您正在獲得還是失去使用者?
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 6%

---

# [!UICONTROL 淨增長]分析 {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="淨增長"
>abstract="您正在獲得還是失去使用者?"

<!-- markdownlint-enable MD034 -->

「![淨增長](/help/assets/icons/NetGrowth.svg) **[!UICONTROL 淨增長]**」分析提供您特定期間內，使用者獲益或損失的比率的深入分析。 水平軸是時間間隔，垂直軸是增長的測量值。

每個資料點代表淨增長，其計算公式如下：

`([New users] + [Return users]) / [Dormant users]`

此公式的結果為比率。 `1`的淨成長代表平衡；產品獲得與它失去的使用者數量相同的數量。 淨成長大於`1`代表正成長；新增+回訪使用者多於休眠使用者。 同樣地，淨成長率小於`1`表示減少；休眠使用者多於新回訪使用者。

與[作用中](active-growth.md)分析類似，使用者的定義如下：

* **[!UICONTROL 新]**：使用者在目前期間處於作用中狀態，但先前未啟用。 檢視分析在圖表圖例中暫留在&#39;[!UICONTROL 新使用者]&#39;上以判斷新使用者的回顧範圍。 回顧範圍會根據選取的日期範圍和間隔動態決定。
* **[!UICONTROL Return]**：使用者在目前時段處於作用中狀態，在先前時段未處於作用中狀態，但在某個時間點之前處於作用中狀態。 檢視分析在圖表圖例中暫留在&#39;[!UICONTROL 回訪使用者]&#39;上以判斷回訪使用者的回顧範圍。 回顧範圍會根據選取的日期範圍和間隔動態決定。
* **[!UICONTROL 休眠]**：使用者在上一個時段處於作用中狀態，但在目前時段未處於作用中狀態。 休眠使用者不計入作用中使用者總數。

>[!NOTE]
>
>重複使用者不會納入此計算中，因為他們不代表任何使用者的收益或損失。

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?quality=12&learn=on)


## 使用案例

此分析的使用案例包括：

* **效能評估**：可讓您評估產品在取得新使用者方面的整體效能。 透過追蹤增長趨勢，您更能瞭解您的產品是否以所需的速度吸引和保留使用者。
* **使用者贏取分析**：可讓您評估使用者贏取策略的成效。 分析使用者成長的來源，例如搜尋引擎、行銷活動或其他行銷管道，可讓您找出最重要的成長來源，讓您據此分配資源。
* **流失分析**：淨成長在其公式中包含減少（休眠使用者）。 您可以評估使用者群在一段時間內的整體健康狀況。 如果淨增長持續低於`1`，則表示有大量的消耗可能促使實施保留策略。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[作用中成長](active-growth.md)之間切換。
* **[!UICONTROL 事件]**：您要測量的事件。 由於此分析是以使用者為基礎，在期間內與事件互動一次的使用者會計為作用中使用者。 您可以在查詢中包含一個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 使用者數目]和[!UICONTROL 使用者百分比]。
* **[!UICONTROL 區段]**：您要測量的區段。 您可以在查詢中包含一個區段。

### 時間比較

{{apply-time-comparison}}

### 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 有效的選項包括每小時、每日、每週、每月和每季。 相同日期範圍可以有不同的間隔，這會影響圖表中的資料點數以及表格中的欄數。 例如，以每日詳細程度檢視橫跨3天的分析只會顯示3個資料點，而以每小時詳細程度橫跨3天的分析則會顯示72個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
