---
description: 設定Journey Canvas視覺效果時的範例
title: 歷程畫布範例
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: cbe713c08269fd3cc4e1076181020ff3fdc947b3
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 0%

---

# 歷程畫布疑難排解

{{release-limited-testing}}

Journey Canvas視覺效果可讓您分析和深入瞭解您提供給使用者和客戶的歷程。

若要深入瞭解歷程畫布，請參閱[歷程畫布總覽](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)和[設定歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

以下資訊可協助您疑難排解可能看到的非預期結果，例如稍後進入歷程的節點，其顯示的百分比或數量會高於先前進入歷程的節點。

## 百分比或值高於先前節點的節點

在Journey畫布中，對於歷程較晚進入的節點，可能會顯示比歷程中較早進入的節點更高的百分比或數量計數。

換句話說，和「流失」視覺效果不同，「流失」視覺效果總是漏斗形（參與率會隨著每個步驟而減少），「歷程」畫布視覺效果在歷程後續步驟中的參與率可能比在先前的步驟中更高。

這可能發生在以下情境中：

* 使用人員或工作階段以外的主要量度時

* 當多個路徑收斂到單一節點時

### 歷程使用人員或工作階段以外的主要量度

由於歷程畫布可讓您將任何量度當作主要量度，這可能會導致位於歷程較晚的節點顯示較高的百分比或數量計數，高於位於歷程較早的節點。

![包含百分比高於先前節點](assets/journey-canvas-higher-percentage.png)之節點的歷程

以下案例中使用的歷程已使用這些設定進行設定：

* **[!UICONTROL 人員]**&#x200B;已設定為容器

* **[!UICONTROL 事件]**&#x200B;已設定為主要量度

#### 案例1：使用者A會依循第一個工作階段的歷程路徑。 在後續的工作階段中，使用者有一個事件只符合較新的節點。

假設使用者A造訪網站並完成歷程（節點1：「造訪網站」>節點2：「檢視產品A」>節點3：「結帳」）。 由於使用者A有一個事件依序符合歷程的每個節點，因此事件會計入歷程的每個節點上。

現在，假設使用者A在之後的工作階段中再次造訪網站。 由於使用者A已透過遵循歷程路徑而在先前的工作階段中完成歷程，這表示每當使用者A發生符合歷程中任何節點的事件（即使使用者A未在其目前工作階段中遵循歷程路徑）時，事件就會計入歷程中的相關節點上。 例如，如果使用者A取出，則事件會計入「取出」節點中。 這會導致「出庫」節點上的百分比和數目高於前一個節點「檢視產品A」上的百分比和數目。

在此範例中，歷程的「人員」容器設定在判斷第三個節點上的事件（「取出」）是否計入後續工作階段中時，扮演關鍵角色。

或者，如果容器設定已設為「工作階段」，則後續造訪中僅發生在第三個節點上的事件將不會計入歷程中，因為歷程中顯示的統計資料將限製為給定人員的單一已定義工作階段。 若要深入瞭解容器設定，請參閱文章[設定歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)中的[開始建立歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### 案例2：使用者B離開歷程

假設使用者B造訪網站但未完成歷程（造訪網站、檢視產品B，然後結帳）。 在這種情況下，事件會計入歷程的開始節點「造訪網站」，但事件不會計入其餘節點，且使用者B會離開歷程。 即使使用者B已簽出，事件也不會計入第三個節點（「簽出」）上，因為使用者B在簽出前並未透過檢視產品A來完成歷程。

這是因為只有在使用者遵循歷程的「最終路徑」時，才會計算每個節點的事件。 也就是說，無論在這2個節點之間發生任何事件，人員最終都從某個節點移至另一個節點時，才會計算事件。

### 歷程有多個路徑會聚至單一節點

歷程畫布可讓您在單一歷程中包含多個開始節點，產生多個路徑。 這些路徑可以融合到通用節點中，導致在歷程中較晚出現的節點顯示比歷程中較早出現的節點更高的百分比或數量計數。

![有多個路徑會聚至單一節點的歷程](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### 歷程百分比

雖然無論在&#x200B;**[!UICONTROL 百分比值]**&#x200B;欄位中選取什麼，歷程每個節點上顯示的數字都保持不變，但百分比本身可能會變更。

下列區段會根據在&#x200B;**[!UICONTROL 百分比值]**&#x200B;欄位中選取的下列選項，顯示相同歷程的百分比如何變更：

+++開始節點的百分比

當&#x200B;**[!UICONTROL 百分比值]**&#x200B;欄位設定為起始節點&#x200B;]**的**[!UICONTROL &#x200B;百分比時，此歷程中的節點包含下列統計資料：

![包含百分比高於先前節點](assets/journey-canvas-higher-percentage.png)之節點的歷程

| 節點 | 統計資料 |
|---------|----------|
| 節點1 - 「造訪網站」 | 在此歷程中，在報告日期範圍內的網站上有354,147個事件，如歷程的開始節點「造訪網站」所示。 |
| 節點2 - 「檢視產品A」 | 在開始節點中顯示的事件總數中，有14% (48,394)符合歷程第二個節點「檢視產品A」的條件。 |
| 節點3 - 「取出」 | 在開始節點中顯示的事件總數中，有32% (113,782)符合歷程的第三個節點「結帳」的條件。 |

+++

+++上一個節點的百分比

當&#x200B;**[!UICONTROL 百分比值]**&#x200B;欄位設定為先前節點的&#x200B;**[!UICONTROL 百分比]**&#x200B;時，此歷程中的節點包含下列統計資料：

![包含百分比高於先前節點](assets/journey-canvas-percentage-previous.png)之節點的歷程

| 節點 | 統計資料 |
|---------|----------|
| 節點1 - 「造訪網站」 | 在此歷程中，在報告日期範圍內的網站上有354,147個事件，如歷程的開始節點「造訪網站」所示。 |
| 節點2 - 「檢視產品A」 | 在上一個節點中顯示的事件總數中，有14% (48,394)符合歷程第二個節點「檢視產品A」的條件。 |
| 節點3 - 「取出」 | 在上一個節點中顯示的事件總數中，超過100% (113,782)符合歷程的第三個節點「結帳」的條件。 |

+++

總數的+++百分比

當&#x200B;**[!UICONTROL 百分比值]**&#x200B;欄位設定為總數的&#x200B;**[!UICONTROL 百分比]**&#x200B;時，此歷程中的節點包含下列統計資料：

![包含百分比高於先前節點](assets/journey-canvas-percentage-total.png)之節點的歷程

| 節點 | 統計資料 |
|---------|----------|
| 節點1 - 「造訪網站」 | 在此歷程中，在報告日期範圍內的網站上有354,147個事件，如歷程的開始節點「造訪網站」所示。 |
| 節點2 - 「檢視產品A」 | 在事件總數中，不到1% (48,394)符合歷程第二個節點「檢視產品A」的條件。 |
| 節點3 - 「取出」 | 在事件總數中，有1% (113,782)符合歷程的第三個節點「結帳」的條件。 |

+++

## 容器量度和主要量度之間的相容性

您可以將「歷程畫布」容器設定為「人員」（使用「人員」量度）或「工作階段」（使用「工作階段」量度）。

請務必選擇與目前所選容器量度相容的主要量度。 大部分的量度都與可用的容器量度相容。 不過，應避免容器量度和主要量度的某些組合。

例如，使用「人員」作為容器，而「工作階段」作為主要量度可能會導致意外的結果。

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
