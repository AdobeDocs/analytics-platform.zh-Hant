---
description: 歷程畫布概觀
title: 歷程畫布
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 27c76e5090e4dfcfc00fd11c7a67574dc6af1c63
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 1%

---

# 歷程畫布概觀

{{release-limited-testing}}

Journey Canvas視覺效果可讓您分析和深入瞭解您提供給使用者和客戶的歷程。 它可讓您從頭開始定義歷程，或從Journey Optimizer檢視歷程，然後檢視人們如何離開（流失）或繼續通過（流過）歷程。

您可以[使用任何事件、維度專案、篩選器和日期範圍的組合，建立使用者歷程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)的分析，以建立歷程節點。 連線節點以建立歷程的流程，並包含多個路徑和決定點。 拖曳畫布上的節點以重新排列歷程的事件和條件。 當您進行變更時，資料會即時更新。

[節點已連線](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)為「最終路徑」，這表示無論這2個節點之間發生任何事件，只要訪客最終從一個節點移至另一個節點即會計入訪客。 為使用者沿路徑移動所分配的時間取決於容器設定。

![歷程畫布](assets/journey-canvas.png)

## 主要功能

Journey Canvas視覺效果的主要功能包括：

* 針對最複雜的使用者旅程進行的流失和流過深度分析。

* 對應和視覺化使用者歷程的各種入口點、節點和路徑的畫布。

* 以拖放互動方式將元件新增至畫布並重新定位現有節點。

* 在Journey Canvas中建立使用者歷程分析或根據Journey Optimizer歷程自動建立歷程的選項。

## 可能的深入分析

歷程畫布為最複雜的歷程提供可操作的深入分析。

### 轉換率最高的路徑 {#conversion-rate-caption}

Journey畫布中最顯著的深入分析會顯示為畫布本身的頂端標題。

此註解會摘要歷程中的所有路徑中，哪些路徑的轉換率最高。

當歷程包含多個開始節點時，標題看起來像這樣：

![歷程畫布分析註解](assets/journey-canvas-caption.png)

當歷程包含單一開始節點時，標題看起來像這樣：

![歷程畫布分析註解單一開始節點](assets/journey-canvas-caption-singlestart.png)

解譯此註解時，請考量下列事項：

* _路徑_&#x200B;定義為起始節點，透過箭頭連線至結束節點，且節點之間連線任何數量的節點。

* 轉換率計算取決於歷程型別（歷程中包含的開始節點和結束節點數量，以及路徑是否相交）。

  下表說明如何根據歷程型別計算轉換率：

  | 歷程型別 | 轉換率計算 | 範例 |
  |---------|----------|---------|
  | **單一開始節點與單一結束節點** | 轉換率的計算方式是將結束節點的數量除以開始節點的數量。 | ![有多重開始之旅會聚至共同節點](assets/journey-canvas-single-path.png) |
  | **單一開始節點與多個結束節點** | 轉換率的計算方式是找出具有最高數目的結束節點，然後將該數目除以開始節點的數目。 | ![有多重開始之旅會聚至共同節點](assets/journey-canvas-singlestart-multiend.png) |
  | **多個獨立路徑，每個路徑包含單一開始節點和單一結束節點** | 轉換率的計算方式是將結束節點的數量除以開始節點的數量。 標題中會說明轉換率最高的路徑。 | ![有多重開始之旅會聚至共同節點](assets/journey-canvas-multi-start-separate.png) |
  | **歷程中任何時間點會聚成共同節點的多個開始節點** | 轉換率的計算方式是尋找具有最高編號的結束節點，然後將該編號除以具有最低編號的開始節點。 | ![有多重開始之旅會聚至共同節點](assets/journey-canvas-multi-start-converge.png) |

### 流過、流失等

以下是Journey Canvas可以協助提供的一些其他深入分析範例。 您可以選擇這些見解是根據資料檢視中的所有人員、所有開始歷程的人員，還是歷程先前節點的所有人員。

#### 區間

* 完成歷程（到達結束節點）的人數與百分比

* 到達歷程指定節點的人員數目和百分比

* 在歷程的指定節點之後或之前的最常見步驟

#### 流失

* 人們最常離開歷程的歷程節點（從未到達任何緊接的下一個節點）

#### 每個節點的其他資料

* 在歷程的任何節點上新增劃分維度，以檢視該特定節點的其他資料

## 在歷程畫布、流失或流量視覺效果之間選擇

歷程畫布視覺效果與[流失視覺效果](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[流量視覺效果](/help/analysis-workspace/visualizations/c-flow/flow.md)有共同之處，但有重要的差異。

### 瞭解差異

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何時使用歷程畫布

歷程畫布對以下專案至關重要：

* 涉及具有多個進入點和路徑的歷程的流失分析。

* 具有多個入口點和路徑的非線性歷程，具有預先定義的頁面順序。

* 探索性的Ad Hoc Analysis，根據預先定義的歷程。

* 分析需要「工作階段」、「人員」或「發生次數」以外的主要量度。

* 對源自Adobe Journey Optimizer的歷程進行更深入的分析。

使用[上表](#understand-the-differences)來瞭解「歷程」畫布、「流失」和「流量」視覺效果之間的差異。

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

如果您對Journey Canvas中的Journey Optimizer歷程進行重大修改，資料處理、可用功能和同步行為可能會發生變更。 重大修改包括下列任一項作業：

* 新增或移除節點

* 在節點之間新增或移除箭頭

* 變更節點上的元件

如果您對「歷程」畫布中的Journey Optimizer歷程進行其他變更，例如拖曳節點或新增劃分，則以下各節所述的差異不適用。

>[!NOTE]
>
>若要將歷程恢復為原始狀態，您可以在歷程畫布中進行首次變更後按下Ctrl+z。 或者，您可以在歷程畫布中刪除並[重新建立歷程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 資料處理差異

在Journey Canvas中修改Journey Optimizer歷程後，如果您的歷程包含具有非預設歸因模型的量度，您可能會注意到資料變更。

這是因為Journey Optimizer不同，歷程畫布可讓您在單一歷程中套用多個維度。 此功能表示不支援[量度歸因](/help/data-views/component-settings/attribution.md)。

#### 功能差異

在歷程畫布中修改Journey Optimizer歷程後，[!UICONTROL **箭頭設定**]&#x200B;下拉式欄位中可用的選項會隨著您的修改而變更。 如需詳細資訊，請參閱[設定設定](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

[!UICONTROL **節點型別**]&#x200B;欄位只能在Journey Optimizer中使用。 無論您是否在Journey Canvas中修改歷程，在歷程畫布中檢視Journey Optimizer歷程時都無法使用此功能。

#### 同步化差異

對Journey Optimizer中的歷程所做的變更，只有在歷程在Journey Canvas中保持未修改狀態時，才會同步至Journey Canvas。

在歷程畫布中修改Journey Optimizer歷程後，您對Journey Optimizer中的歷程所做的任何變更都不會反映在歷程畫布中。 若要檢視反映在歷程畫布中的變更，您可以在Journey畫布中刪除並重新建立歷程[](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

### Journey Optimizer和Customer Journey Analytics之間的術語差異

Journey Optimizer中代表一件事的特定辭彙在Customer Journey Analytics中代表其他意義。 使用歷程畫布時，會使用Customer Journey Analytics詞語。

| 詞語 | 歷程畫布 | Journey Optimizer |
|---------|----------|---------|
| **Event** | Customer Journey Analytics提供的數個標準量度之一。 此量度會計入收入、訂閱或產生的潛在客戶等。 | 觸發個人化歷程（例如線上購買）的活動類別。 |

### 在歷程畫布中分析Journey Optimizer歷程

如需有關在Journey Canvas中分析Journey Optimizer歷程的資訊，請參閱[設定Journey Canvas視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

## 在Journey Canvas中建立分析

您可以在Journey Canvas中建立以Analysis Workspace中可用的任何維度或量度為基礎的分析。 或者，您也可以分析在Journey Optimizer中建立的歷程。 如需詳細資訊，請參閱[設定Journey Canvas視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。
