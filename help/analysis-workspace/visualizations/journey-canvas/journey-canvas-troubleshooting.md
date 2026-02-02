---
description: 了解在設定歷程畫布視覺化圖表時如何進行疑難排解。
title: 歷程畫布疑難排解
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: ht
source-wordcount: '1290'
ht-degree: 100%

---

# 歷程畫布疑難排解

您可以利用歷程畫布視覺化圖表，針對您提供給使用者和客戶的歷程進行分析並獲取深入洞察。

若要了解更多關於歷程畫布的資訊，請參閱[歷程畫布概觀](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)和[設定歷程畫布視覺化圖表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

以下資訊可以協助您針對可能出現的非預期結果進行疑難排解，例如在歷程後段出現的節點所顯示的百分比或數量，高於在歷程前段出現的節點。

## 其百分比或值高於前一個節點的節點

在歷程畫布中，位於歷程後段的節點所顯示的百分比或數量，有可能高於位於歷程前段的節點。

換言之，與總是漏斗形狀 (參與率會隨著各步驟減少) 的流失視覺化圖表不同，歷程畫布視覺化圖表在歷程後段步驟中的參與率，可能會高於先前的步驟。

在以下情境中就可能發生這個現象：

* 使用「人員」或「工作階段」以外的主要量度時

* 當多個路徑聚合成單一節點時

### 歷程使用「人員」或「工作階段」以外的主要量度

由於在歷程畫布中您可以使用任何量度做為主要量度，這可能會導致位於歷程後端的節點所顯示的百分比或數量，高於位於歷程前段的節點。

![歷程中有些節點的百分比高於前一個節點](assets/journey-canvas-higher-percentage.png)

以下情境中使用的歷程採用下列設定：

* 將&#x200B;**[!UICONTROL 個人]**&#x200B;設定為容器

* 將&#x200B;**[!UICONTROL 事件]**&#x200B;設定為主要量度

#### 情境 1：使用者 A 依循第一個工作階段的歷程路徑。在後續的工作階段中，使用者發生只有後段節點符合的事件。

假設使用者 A 造訪網站並完成歷程 (節點 1：「造訪網站」> 節點 2：「檢視產品 A」> 節點 3：「結帳」)。由於使用者 A 有一個事件依照順序符合歷程的各個節點，因此事件會計入歷程的各個節點。

現在，假設使用者 A 在之後的工作階段中再次造訪網站。由於使用者 A 已依循歷程路徑而在先前的工作階段中完成歷程，因此每當使用者 A 發生符合歷程中任何節點的事件時，事件便會計入歷程中的相關節點，即便使用者 A 於其目前工作階段中並未依循歷程路徑。例如，如果使用者 A 結帳，則事件會計入「結帳」節點。這會造成「結帳」節點上的百分比和數量高於前一個節點「檢視產品 A」。

於此範例中，歷程的容器設定為「個人」發揮了關鍵作用，能依此判斷第三個節點 (「結帳」) 上的事件是否要計入後續工作階段中。

另一種情況是將容器設定為「工作階段」，則後續造訪中僅發生在第三個節點上的事件將不會計入歷程中，因為歷程中顯示的統計資料會限定為特定個人的單一已定義工作階段。若要了解更多關於容器設定的資訊，請參閱文章[設定歷程畫布視覺化圖表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)中的[開始建立歷程畫布視覺化圖表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### 情境 2：使用者 B 從歷程流失

假設使用者 B 造訪網站但未完成歷程 (造訪網站、檢視產品 B 然後結帳)。於此情況下，事件會計入歷程的開始節點「造訪網站」，但不會計入其餘節點，然後使用者 B 從歷程流失。即便使用者 B 已結帳，事件不會計入第三個節點 (「結帳」)，因為使用者 B 在結帳前並未透過檢視產品 A 來完成歷程。

這是因為只有在使用者依循歷程的「最終路徑」時，才會將事件計入各個節點中。也就是說，無論在這 2 個節點之間發生任何事件，個人最終都從某個節點移至另一個節點時，才會計入事件。

### 歷程將多個路徑聚合成單一節點

您可以使用歷程畫布將多個開始節點包含在單一歷程中，由此產生多個路徑。這些路徑可能會聚合成一個通用節點，導致在歷程中較晚出現的節點所顯示的百分比或數量，高於歷程中較早出現的節點。

![有多個路徑聚合成單一節點的歷程](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### 歷程百分比

雖然無論在「**[!UICONTROL 百分比值]**」欄位中選取什麼，歷程各個節點上顯示的數量都保持不變，但百分比本身可能會變動。

下列區段會顯示相同歷程的百分比如何根據在「**[!UICONTROL 百分比值]**」欄位中選取的選項而變更：

+++開始節點的百分比

當「**[!UICONTROL 百分比值]**」欄位設定為「**[!UICONTROL 開始節點的百分比]**」時，此歷程中的節點會包含下列統計資料：

![歷程中有些節點的百分比高於前一個節點](assets/journey-canvas-higher-percentage.png)

| 節點 | 統計資料 |
|---------|----------|
| 節點 1 -「造訪網站」 | 於此歷程中，網站上符合報告日期範圍的事件有 354,147 個，如歷程的開始節點「造訪網站」所示。 |
| 節點 2 -「檢視產品 A」 | 開始節點內顯示的事件總數中，有 14% (48,394 個) 符合歷程第二個節點「檢視產品 A」的條件。 |
| 節點 3 -「結帳」 | 開始節點內顯示的事件總數中，有 32% (113,782 個) 符合歷程第三個節點「結帳」的條件。 |

+++

+++前一個節點的百分比

當「**[!UICONTROL 百分比值]**」欄位設定為「**[!UICONTROL 前一個節點的百分比]**」時，此歷程中的節點會包含下列統計資料：

![歷程中有些節點的百分比高於前一個節點](assets/journey-canvas-percentage-previous.png)

| 節點 | 統計資料 |
|---------|----------|
| 節點 1 -「造訪網站」 | 於此歷程中，網站上符合報告日期範圍的事件有 354,147 個，如歷程的開始節點「造訪網站」所示。 |
| 節點 2 -「檢視產品 A」 | 在前一個節點顯示的事件總數中，有 14% (48,394 個) 符合歷程第二個節點「檢視產品 A」的條件。 |
| 節點 3 -「結帳」 | 在前一個節點顯示的事件總數中，有超過 100% (113,782 個) 符合歷程第三個節點「結帳」的條件。 |

+++

+++總數百分比

當「**[!UICONTROL 百分比值]**」欄位設定為「**[!UICONTROL 總數百分比]**」時，此歷程中的節點會包含下列統計資料：

![歷程中有些節點的百分比高於前一個節點](assets/journey-canvas-percentage-total.png)

| 節點 | 統計資料 |
|---------|----------|
| 節點 1 -「造訪網站」 | 於此歷程中，網站上符合報告日期範圍的事件有 354,147 個，如歷程的開始節點「造訪網站」所示。 |
| 節點 2 -「檢視產品 A」 | 在事件總數中，不到 1% (48,394 個) 符合歷程第二個節點「檢視產品 A」的條件。 |
| 節點 3 -「結帳」 | 在事件總數中，有 1% (113,782 個) 符合歷程第三個節點「結帳」的條件。 |

+++

## 容器量度和主要量度之間的相容性

您可以將「歷程畫布」容器設定為「個人」(使用「人員」量度) 或「工作階段」(使用「工作階段」量度)。

請務必選擇與目前所選取之容器量度相容的主要量度。大部分量度都與可供使用的容器量度相容。不過，有些容器量度和主要量度的組合應避免使用。

例如，使用「個人」做為容器，而「工作階段」做為主要量度，可能會導致非預期的結果。

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
