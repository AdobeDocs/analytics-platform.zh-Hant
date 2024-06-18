---
description: 瞭解如何在Analysis Workspace中新增元件至專案
title: 在 Analysis Workspace 中使用元件
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# 在 Analysis Workspace 中使用元件

元件構成Analysis Workspace中任何專案的實際資料。 元件包含維度、量度、篩選器和日期範圍。 您可以將元件拖曳至視覺效果或面板中，藉此新增元件至專案。

如需可新增之元件型別的概觀資訊，請參閱 [元件概觀](/help/components/overview.md).

>[!TIP]
>
>如需各個元件的詳細資訊，請在Analysis Workspace的左側邊欄中選取元件名稱旁的「資訊」圖示。

## 開始新增元件至專案

1. [在Analysis Workspace中建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md) 如果您尚未這樣做。

1. [新增面板](/help/analysis-workspace/c-panels/panels.md) 或 [新增視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) Analysis Workspace中的專案。

   如果您將元件新增至空白專案，則會自動建立自由表格視覺效果。

1. 選取左側邊欄中的「**[!UICONTROL 元件]**」圖示。

   ![](assets/build-components.png)

1. 捲動至或搜尋要新增的元件，然後將其拖曳到專案中的面板或視覺化效果中。

1. （可選）將元件拖曳至面板標頭中的篩選器拖放區域。

   篩選器會套用至面板中的所有內容。

   如需如何在面板上使用篩選器拖放區域來篩選面板的相關資訊，請參閱 [拖放區域](/help/analysis-workspace/c-panels/panels.md#drop-zone) 在 [面板概觀](/help/analysis-workspace/c-panels/panels.md).

   ![將篩選器放入放置區](assets/filter-dropzone.png)

1. 如需更多詳細資訊，請根據您新增的元件型別，繼續下列其中一節：

   * [將維度新增至專案](#add-dimensions-to-a-project)

   * [將量度新增至專案](#add-metrics-to-a-project)

   * [將篩選器新增至專案](#add-filters-to-a-project)

   * [新增日期範圍至專案](#add-date-ranges-to-a-project)

## 將維度新增至專案

[Dimension](/help/components/dimensions/overview.md) 是Adobe Analytics中通常包含字串值的變數。 相對地，[量度](/help/components/calc-metrics/calc-metr-overview.md)包含繫結至維度的數值。基本報表會針對一個數值 (量度) 欄顯示字串值 (維度) 列。

1. 如所述，開始將維度新增至Analysis Workspace中的專案 [開始新增元件至專案](#begin-adding-components-to-a-project).

1. 選擇下列其中一種方法來新增維度，並決定您要分析的資料型別：

   * 將維度拖曳至Analysis Workspace中的視覺效果（例如自由表格）。

     ![將維度新增至專案](assets/add-dimensions.png)

   * 從左側邊欄將一或多個維度拖曳至篩選器拖放區域以建立臨時篩選器，如所述 [將篩選器新增至專案](#add-filters-to-a-project).

1. （選用）您可以在Analysis Workspace中搭配其他元件來劃分維度和維度專案。

   如需詳細資訊，請參閱 [在工作區中劃分維度](/help/components/dimensions/t-breakdown-fa.md).

如需如何在Analysis Workspace中使用維度的詳細資訊，請參閱 [預覽維度](/help/components/dimensions/view-dimensions.md)， [劃分維度](/help/components/dimensions/t-breakdown-fa.md)、和 [時間分段維度](/help/components/dimensions/time-parting-dimensions.md).

## 將量度新增至專案

量度可讓您量化 Analysis Workspace 中的資料點。它們最常用作視覺效果中的欄，並和維度相連結。

若要在Analysis Workspace中新增量度至專案：

1. 開始在Analysis Workspace中將量度新增至您的專案，如所述 [開始新增元件至專案](#begin-adding-components-to-a-project).

1. 選擇下列其中一種方法，在Analysis Workspace中新增量度：

   * 將量度拖曳至空白自由表格中的量度拖放區域，可檢視專案日期期間的量度趨勢。

     ![將量度新增至專案](assets/add-metrics.png)

   * 存在維度時可將量度拖移，以查看該量度和每個維度項目的比較。

   * 將量度拖移到現有量度標頭的頂部，即可將其取代。

   * 將量度拖移到標頭旁邊，即可並排查看兩個量度。

如需量度的詳細資訊，請參閱 [計算量度概觀](/help/components/calc-metrics/calc-metr-overview.md).

## 將篩選器新增至專案

[篩選器](/help/components/filters/filters-overview.md) 可讓您根據特性或特定互動來識別訪客的子集。

您可以透過下列任何方式在Analysis Workspace中使用篩選器：

### 將篩選器新增至面板

將篩選器新增至面板時，篩選器會套用至面板內的所有內容。

如需如何在面板上使用篩選器拖放區域來篩選面板的相關資訊，請參閱 [拖放區域](/help/analysis-workspace/c-panels/panels.md#drop-zone) 在 [面板概觀](/help/analysis-workspace/c-panels/panels.md).

### 將篩選器新增至自由格式表格中的欄

當您將篩選器新增至自由格式表格中的欄時，篩選器會套用至表格欄內的所有內容。

### 建立計算量度時使用篩選器

在計算量度產生器中，您可以在量度定義中套用篩選器。

如需詳細資訊，請參閱 [篩選量度](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## 新增日期範圍至專案

[日期範圍](/help/components/date-ranges/custom-date-ranges.md) 決定Analysis Workspace中的報告時間範圍，並可套用至專案中一或多個面板。

依預設，每個面板都包含日期範圍。 更新面板的日期範圍有多種方式。 在Analysis Workspace中更新面板日期範圍的一種方法是從左側邊欄拖曳日期範圍元件：

1. 開始在Analysis Workspace中新增日期範圍至您的專案，如所述 [開始新增元件至專案](#begin-adding-components-to-a-project).

1. 從左側邊欄將日期範圍拖曳至面板右上角目前的日期範圍。

   ![放置日期範圍](assets/daterange-drop.png)

如需如何在Analysis Workspace中使用行事曆和日期範圍的詳細資訊，請參閱 [日曆和日期範圍概觀](/help/components/date-ranges/custom-date-ranges.md).
