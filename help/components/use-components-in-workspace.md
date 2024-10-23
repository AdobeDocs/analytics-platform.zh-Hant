---
description: 瞭解如何在Analysis Workspace中新增元件至專案
title: 在 Analysis Workspace 中使用元件
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# 在 Analysis Workspace 中使用元件

元件構成Analysis Workspace中任何專案的實際資料。 元件包含維度、量度、篩選器和日期範圍。 您可以將元件拖曳至視覺效果或面板中，藉此新增元件至專案。

如需您可以新增之元件型別的詳細資訊，請參閱[元件概觀](/help/components/overview.md)。

>[!TIP]
>
>如需有關每個元件的資訊，請使用![資訊大綱](/help/assets/icons/InfoOutline.svg)。 如需詳細資訊，請參閱[元件資訊](#component-info)

## 將元件新增至專案

1. [在Analysis Workspace中建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)。

1. [新增面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)或[新增視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)至Analysis Workspace中的專案。 如果您將元件新增至空白專案，系統會為您建立自由表格視覺效果。

1. 從按鈕面板選取![組織](/help/assets/icons/Curate.svg) **[!UICONTROL 元件]**。 您會在左側面板中看到所有可用的元件。 如需詳細資訊，請參閱[介面](/help/analysis-workspace/home.md#interface)。

1. 捲動至或搜尋您要新增的元件，然後將其拖曳至專案中的面板或視覺效果。

1. 您可以選擇將元件拖曳至面板標頭的篩選器拖放區域。 這個拖放動作會將元件定義為篩選器，並將篩選器套用至面板內的所有內容。
如需如何在面板上使用篩選器拖放區域來篩選面板的相關資訊，請參閱[面板概觀](/help/analysis-workspace/c-panels/panels.md)中的[拖放區域](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

1. 如需詳細資訊，請參閱下列章節：

   * [將維度新增至專案](#add-dimensions-to-a-project)

   * [將量度新增至專案](#add-metrics-to-a-project)

   * [將篩選器新增至專案](#add-filters-to-a-project)

   * [新增日期範圍至專案](#add-date-ranges-to-a-project)

### 將維度新增至專案

[Dimension](/help/components/dimensions/overview.md)是Customer Journey Analytics中的變數，通常包含字串值。 相對地，[量度](/help/components/calc-metrics/calc-metr-overview.md)包含繫結至維度的數值。基本報表會針對一個數值 (量度) 欄顯示字串值 (維度) 列。

1. 開始將維度新增至您在Analysis Workspace中的專案，如[將元件新增至專案](#add-components-to-a-project)中所述。

1. 選擇下列其中一種方法來新增維度，並決定您要分析的資料型別：

   ![新增維度](/help/components/assets/add-dimension.gif)

   * 將維度拖曳至Analysis Workspace中的視覺效果（例如自由表格）。

   * 從左側面板將一或多個維度拖曳至篩選器拖放區域以建立快速篩選器，如[將篩選器新增至專案](#add-filters-to-a-project)中所述。

1. 您可以選擇使用其他元件在Analysis Workspace中劃分維度和維度專案。 如需詳細資訊，請參閱[在Workspace中劃分維度](/help/components/dimensions/t-breakdown-fa.md)。

如需有關如何在Analysis Workspace中使用維度的詳細資訊，請參閱[預覽維度](/help/components/dimensions/view-dimensions.md)、[劃分維度](/help/components/dimensions/t-breakdown-fa.md)和[時間分段維度](/help/components/dimensions/time-parting-dimensions.md)。

### 將量度新增至專案

量度可讓您量化 Analysis Workspace 中的資料點。它們最常用作視覺效果中的欄，並和維度相連結。

若要在Analysis Workspace中新增量度至專案：

1. 開始將量度新增至您在Analysis Workspace中的專案，如[將元件新增至專案](#add-components-to-a-project)中所述。



1. 選擇下列其中一種方法，在Analysis Workspace中新增量度：

   ![正在新增量度](/help/components/assets/add-metric.gif)

   * 將量度拖曳至空白自由表格中的量度拖放區域，可檢視專案日期期間的量度趨勢。

   * 出現維度時拖曳量度，以檢視每個維度專案的量度。

   * 將量度拖移到現有量度標頭的頂部，即可將其取代。

   * 拖曳現有量度標頭右側左側的量度，以新增量度。

   * 將量度拖曳至現有量度標題上方或下方，以建立量度重疊。


如需量度的詳細資訊，請參閱[量度](/help/components/apply-create-metrics.md)。

### 將篩選器新增至專案

[篩選器](/help/components/filters/filters-overview.md)可讓您根據特性或特定互動來識別人員、工作階段或事件的子集。

您可以透過下列任何方式在Analysis Workspace中使用篩選器：

* 將篩選器新增至面板
將篩選器新增至面板時，篩選器會套用至面板內的所有內容。
如需如何在面板上使用篩選器拖放區域來篩選面板的相關資訊，請參閱[面板概觀](/help/analysis-workspace/c-panels/panels.md)中的[拖放區域](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

* 新增篩選器至視覺效果
當您將篩選器新增至自由格式表格中的欄時，篩選器會套用至表格欄內的所有內容。 您也可以新增篩選器作為流失視覺效果的一部分。

* 在元件中使用篩選器
當您定義[計算量度](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)、[註解](/help/components/annotations/create-annotations.md#annotation-builder)或甚至[篩選器](/help/components/filters/filter-builder.md)等元件時，可以使用篩選器作為定義的一部分。


### 新增日期範圍至專案

[日期範圍](/help/components/date-ranges/overview.md)決定了Analysis Workspace中的報告時間範圍，可套用至專案中一或多個面板，也可套用至某些視覺效果（例如自由表格）。

依預設，每個面板都包含日期範圍。 更新面板的日期範圍有多種方式。 在Analysis Workspace中更新面板日期範圍的一種方法是從左側面板拖曳日期範圍元件：

1. 選擇性地將日期範圍新增至Analysis Workspace中的專案，如[將元件新增至專案](#add-components-to-a-project)中所述。

1. 將日期範圍從左側面板拖放至：

   * 目前的日期範圍，可修改面板的日期範圍。

     ![卸除日期範圍](assets/add-date-range.gif)

   * 自由表格視覺效果中的量度或維度。 如需詳細資訊，請參閱[使用日期範圍](/help/components/date-ranges/overview.md#use-date-ranges)。

如需有關如何在Analysis Workspace中使用和管理日期範圍的詳細資訊，請參閱[日期範圍概觀](/help/components/date-ranges/overview.md)。

## 元件資訊

您可以暫留在任何元件上以顯示![更多資訊](/help/assets/icons/InfoOutline.svg)。 選取後，會顯示快顯視窗，內含元件的其他資訊。

![元件資訊](assets/component-info.png)

根據您的存取控制，您可以：

* 存取元件的![書籤](/help/assets/icons/Bookmark.svg) [!UICONTROL 資料字典]定義。
* 存取定義元件的![Edit](/help/assets/icons/Edit.svg)元件產生器或資料檢視。
