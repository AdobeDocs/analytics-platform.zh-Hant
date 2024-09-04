---
description: 歷程畫布概觀
title: 歷程畫布
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 2f42c64443cc5798388287e6f84b125fb8694812
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 3%

---

# 歷程畫布概觀

{{release-limited-testing}}

Journey Canvas視覺效果可讓您分析和深入瞭解您提供給使用者和客戶的歷程。 它可讓您從頭開始定義歷程，或從Journey Optimizer檢視歷程，然後檢視人們如何離開（流失）或繼續通過（流過）歷程。

您可以[使用任何事件、維度專案、篩選器和日期範圍的組合，建立使用者歷程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)的分析，以建立歷程節點。 連線節點以建立歷程的流程，並包含多個路徑和決定點。 拖曳畫布上的節點以重新排列歷程的事件和條件。 變更時即時更新資料。

## 主要功能

Journey Canvas視覺效果的主要功能包括：

* 針對最複雜的使用者旅程進行的流失和流過深度分析。

* 對應和視覺化使用者歷程的各種入口點、節點和路徑的畫布。

* 以拖放互動方式將元件新增至畫布並重新定位現有節點。

* 在Journey Canvas中建立使用者歷程分析或根據Journey Optimizer歷程自動建立歷程的選項。

## 可能的深入分析

以下範例為Journey Canvas可協助提供的深入分析型別。 您可以選擇這些見解是根據資料檢視中的所有人員還是所有開始歷程的人。

**區間**

* 完成歷程（到達結束節點）的人數與百分比

* 到達歷程指定點（節點）的人數與百分比

* 在歷程的指定點（節點）之後或之前的最常見步驟

**流失**

* 人們最常離開歷程的點（節點）

**其他**

* 歷程中任何節點的其他資料（透過為節點新增劃分維度）


## 在歷程畫布和流失視覺效果之間選擇

歷程畫布視覺效果類似[流失視覺效果](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)，這兩個視覺效果都顯示人員從何處離開（流失）或繼續通過（流過）預先定義的頁面序列。

不過，兩者之間還是有重大差異。

### 瞭解差異

下表顯示「歷程」畫布視覺效果和「流失」視覺效果中支援的分析型別：

| 函數 | 歷程畫布視覺效果 | 流失視覺效果 |
|---------|----------|---------|
| 線性歷程 | 有 | 有 |
| 具有多個入口點和路徑的非線性歷程 | 有 | 無 |
| Adobe Journey Optimizer歷程 | 有 | 無 |
| 主要量度 | 任何量度，包括計算量度 | 只能使用「工作階段」或「使用者」量度 |
| 次要量度 | 是<p>任何量度，包括計算量度</p> | 否 |
| 比較篩選器 | 無 | 是<p>比較[不限數量的篩選器](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### 選擇要使用的視覺效果

在選擇使用歷程畫布或流失之前，請務必[瞭解兩者之間的差異](#understand-the-differences)。

如果您的流失分析只涉及具有單一已知開始和結束的線性歷程，請考慮使用[流失視覺效果](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)作為這些更直接的使用者歷程的更簡單選項。

歷程畫布對於包含具有多個入口點和路徑的歷程的流失分析，或對於分析在Journey Optimizer中建立的歷程至關重要。

## 分析Journey Optimizer歷程

>[!NOTE]
>
>如果貴組織沒有Journey Optimizer的存取權，您仍可[在Journey Canvas](#build-analyses-in-customer-journey-analytics)中建置分析。

在Journey Canvas中分析Journey Optimizer歷程可針對人們如何與歷程互動提供深入且可行的深入分析。

當您在Journey Canvas中分析Journey Optimizer歷程時，該歷程的顯示順序、順序和結構與Journey Optimizer中相同。 如果您可以在Journey Canvas內變更歷程，[變更將不再從Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas)同步處理。

### 使用歷程畫布分析Journey Optimizer歷程的好處

Journey Canvas提供在Journey Optimizer中無法提供的深入徹底分析。

使用歷程畫布來分析在Journey Optimizer中建立的歷程提供各種好處：

* 使用任何Customer Journey Analytics維度、量度、篩選器或日期範圍來建立事件。

  在Journey Optimizer中，技術使用者必須先建立事件，才能將其新增至歷程。

* 根據您建立的自訂節點建立對象(啟動Customer Journey Analytics對象產生器)。

  在Journey Optimizer中，您只能為預先定義的活動建立對象。

* 分析流過和流失

* 使用任何維度劃分事件

* 合併事件

* 連線事件

* 重新命名和刪除事件

* 更多內容

### Journey Optimizer和Journey Canvas之間的同步

在Journey Canvas中建立Journey Optimizer歷程的分析後，資料只會以一個方向同步，從Journey Optimizer到Journey Canvas。 這表示對Journey Canvas中的歷程所做的變更絕不會反映在Journey Optimizer中。

此外，只有在歷程在Journey Optimizer畫布中保持未修改狀態時，對歷程所做的變更才會同步至歷程畫布。 在您修改Journey Canvas中的歷程後，您在Journey Optimizer中對歷程所做的任何變更都不會反映在Journey Canvas中。 若要檢視反映在歷程畫布中的變更，您可以在Journey畫布中刪除並重新建立歷程[](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

### 在歷程畫布中修改歷程後的差異 {#differences-after-modifying}

在歷程畫布中修改Journey Optimizer歷程後，資料處理、可用功能和同步行為可能會變更。

>[!NOTE]
>
>若要將歷程恢復為原始狀態，您可以在歷程畫布中進行首次變更後按下Ctrl+z。 或者，您可以在歷程畫布中刪除並[重新建立歷程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 資料處理差異

在Journey Canvas中修改Journey Optimizer歷程後，如果您的歷程包含具有非預設歸因模型的量度，您可能會注意到資料變更。

這是因為Journey Optimizer不同，歷程畫布可讓您在單一歷程中套用多個維度。 此功能表示不支援[量度歸因](/help/data-views/component-settings/attribution.md)。

#### 功能差異

在歷程畫布中修改Journey Optimizer歷程後，[!UICONTROL **節點型別**]&#x200B;下拉式欄位將不再可用。

如需此欄位的詳細資訊，請參閱[設定設定](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

#### 同步化差異

對Journey Optimizer中的歷程所做的變更，只有在歷程在Journey Canvas中保持未修改狀態時，才會同步至Journey Canvas。

在歷程畫布中修改Journey Optimizer歷程後，您對Journey Optimizer中的歷程所做的任何變更都不會反映在歷程畫布中。 若要檢視反映在歷程畫布中的變更，您可以在Journey畫布中刪除並重新建立歷程[](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

### Journey Optimizer和Customer Journey Analytics之間的術語差異

Journey Optimizer中代表一件事的特定辭彙在Customer Journey Analytics中代表其他意義。 使用歷程畫布時，會使用Customer Journey Analytics詞語。

| 詞語 | 歷程畫布 | Journey Optimizer |
|---------|----------|---------|
| **事件** | Customer Journey Analytics提供的數個標準量度之一。 此量度會計入收入、訂閱或產生的潛在客戶等。 | 觸發個人化歷程（例如線上購買）的活動類別。 |

### 在歷程畫布中分析Journey Optimizer歷程

如需有關在Journey Canvas中分析Journey Optimizer歷程的資訊，請參閱[設定Journey Canvas視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

## 在Journey Canvas中建立分析

您可以在Journey Canvas中建立以Analysis Workspace中可用的任何維度或量度為基礎的分析。 或者，您也可以分析在Journey Optimizer中建立的歷程。 如需詳細資訊，請參閱[設定Journey Canvas視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。
