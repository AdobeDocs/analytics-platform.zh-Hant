---
description: 了解在 Analysis Workspace 中如何使用專案的元件
title: 使用專案的元件
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
TQID: https://experienceleague.adobe.com/kXVC79sHZMIdUELOC6KjtT7tJdh9pVySu-jApef-8lk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 954
ht-degree: 92%

---

# 使用專案中的元件

元件組成任何 Analysis Workspace 專案的實際資料。 元件由維度、量度、區段和日期範圍組成。 您可以將元件拖曳至視覺效果或面板中，將其加入專案。

查閱[元件概觀](/help/components/overview.md)，以進一步了解您可以新增的元件類型。

>[!TIP]
>
>如需各個元件的資訊，請使用 ![InfoOutline](/help/assets/icons/InfoOutline.svg)。 如需詳細資訊，請參閱[元件資訊](#component-info)。

## 將元件新增至專案中

1. [在 Analysis Workspace 中建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)。

1. 對 Analysis Workspace 中的專案[新增面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)或[新增視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。 如果您在空白專案中新增元件，系統將會自動建立自由格式表格視覺效果。

1. 從底部面板選取「![彙整](/help/assets/icons/Curate.svg) **[!UICONTROL 元件]**」。 您可以在左側面板中看到所有可用的元件。 如需詳細資訊，請參閱[介面](/help/analysis-workspace/home.md#interface)。

1. 捲動至或搜尋要新增的元件，然後將其拖曳到專案中的面板或視覺效果中。

1. 您可以選擇將元件拖曳到面板頁首中的區段放置區域。 此拖放動作將元件定義為一個區段，並將此區段套用至面板中的所有內容。
如欲了解如何使用面板上的區段放置區域將面板分段，請參閱[面板概觀](/help/analysis-workspace/c-panels/panels.md)中的[放置區域](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

1. 如需詳細資訊，請參閱下列章節：

   * [在專案中新增維度](#add-dimensions-to-a-project)

   * [在專案中新增量度](#add-metrics-to-a-project)

   * [在專案中新增區段](#add-segments-to-a-project)

   * [在專案中新增日期範圍](#add-date-ranges-to-a-project)

### 在專案中新增維度

[維度](/help/components/dimensions/overview.md)是 Customer Journey Analytics 中通常會包含字串值的變數。 相對地，[量度](/help/components/calc-metrics/calc-metr-overview.md)包含繫結至維度的數值。 基本報表會針對一個數值 (量度) 欄顯示字串值 (維度) 列。

1. 根據[在專案中新增元件](#add-components-to-a-project)的說明，開始為 Analysis Workspace 專案新增維度。

1. 選擇下列其中一項方法新增維度，並確定要分析的資料類型：

   ![新增維度](/help/components/assets/add-dimension.gif)

   * 將維度拖曳到 Analysis Workspace 的視覺效果 (例如自由格式表格) 中。

   * 根據[在專案中新增區段](#add-filters-to-a-project)的說明，從左側面板拖曳一或多個維度到區段放置區域，即可建立快速區段。

1. 您可以選擇使用其他元件劃分 Analysis Workspace 中的維度和維度項目。 如需詳細資訊，請參閱[在 Workspace 中劃分維度](/help/components/dimensions/t-breakdown-fa.md)。

如欲了解如何使用 Analysis Workspace 的維度，請參閱[預覽維度](/help/components/dimensions/view-dimensions.md)、[劃分維度](/help/components/dimensions/t-breakdown-fa.md)以及[時間分段維度](/help/components/dimensions/time-parting-dimensions.md)。

### 在專案中新增量度

量度可讓您量化 Analysis Workspace 中的資料點。 它們最常用作視覺效果中的欄，並和維度相連結。

若要將量度新增至 Analysis Workspace 中的專案：

1. 根據[在專案中新增元件](#add-components-to-a-project)的說明，開始為 Analysis Workspace 專案新增量度。



1. 選擇下列其中一項方法在 Analysis Workspace 中新增量度：

   ![新增量度](/help/components/assets/add-metric.gif)

   * 將量度拖曳到空白自由格式表格中的量度放置區域，以查看該量度在專案日期期間的趨勢。

   * 已有維度時，可拖曳量度以查看各個維度項目的量度。

   * 將量度拖曳到現有量度頁首的頂部，即可將其取代。

   * 將量度拖曳到現有量度頁首的左側或右側，即可新增量度。

   * 將量度拖曳到現有量度頁首的上方或下方，即可建立量度重疊。


如需關於量度的詳細資訊，請參閱[設定量度](/help/components/apply-create-metrics.md)。

### 在專案中新增區段

[區段](/help/components/segments/seg-overview.md)可讓您根據特性或互動來識別人員、工作階段或事件的子集。

您可以透過以下任一方式使用 Analysis Workspace 區段：

* 新增區段至面板
將區段新增至面板時，區段會套用至面板內的所有內容。
如欲了解如何使用面板上的區段放置區域將面板分段，請參閱[面板概觀](/help/analysis-workspace/c-panels/panels.md)中的[放置區域](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

* 新增區段至視覺效果
將區段新增至自由表格中的欄時，區段會套用至表格欄中的所有內容。 您也可以新增區段作為流失視覺效果的一部分。

* 在元件中使用區段
當您定義[計算量度](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)、[註解](/help/components/annotations/create-annotations.md#annotation-builder)或甚至[區段](/help/components/segments/seg-builder.md)等元件時，您可以使用區段做為定義的一部分。


### 在專案中新增日期範圍

[日期範圍](/help/components/date-ranges/overview.md)確定 Analysis Workspace 中的報告時間段，並且可以套用至專案中一或多個面板，以及部分視覺效果 (例如自由格式表格)。

每個面板都包含一個預設的日期範圍。 有多種方法可以更新面板的日期範圍。 更新 Analysis Workspace 面板日期範圍的其中一種方法，是從左側面板拖曳日期範圍元件：

1. 或者，根據[在專案中新增元件](#add-components-to-a-project)的說明，將日期範圍新增至 Analysis Workspace 專案中。

1. 從左側面板拖放日期範圍至：

   * 目前日期範圍，可修改面板的日期範圍。

     ![放置日期範圍](assets/add-date-range.gif)

   * 自由格式表格視覺效果的量度或維度。 請參閱[使用日期範圍](/help/components/date-ranges/overview.md#use-date-ranges)，以了解更多資訊。

如欲了解如何在 Analysis Workspace 中使用和管理日期範圍，請參閱[日期範圍概觀](/help/components/date-ranges/overview.md)。

## 元件資訊

將游標停留在任何元件上，即可顯示![更多資訊](/help/assets/icons/InfoOutline.svg)。 選取後將會彈出一個視窗，其中包含有關該元件的附加資訊。

![元件資訊](assets/component-info.png)

根據存取控制，您可以：

* 存取元件的![書籤](/help/assets/icons/Bookmark.svg) [!UICONTROL 資料字典]定義。
* 存取定義元件的![編輯](/help/assets/icons/Edit.svg)元件產生器或資料視圖。
