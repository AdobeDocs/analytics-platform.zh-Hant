---
title: 在自由格式表格中包含多個維度
description: 瞭解如何在自由格式表格中包含多個維度
feature: Visualizations
role: User
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# 在自由格式表格中包含多個維度欄

{{release-limited-testing}}

您最多可以在自由表格中包含5個維度欄，讓您並排檢視多個維度專案。 每一列維度專案的行為類似於單一串連維度專案。

您可以將篩選器、排序、劃分等套用至具有多個維度欄的自由格式表格，以建立更深入、更自訂的分析。

## 串連的維度專案

當您[將多個維度欄](#add-multiple-dimension-columns)新增到自由格式表格時，每一列維度專案的行為就像單一串連維度專案。 此功能可讓您檢視特定維度組合的量度資料。

例如，假設自由表格，其維度欄為&#x200B;_城市_、_裝置型別_&#x200B;和&#x200B;_當月天數_，而量度為&#x200B;_事件_。 此表格第一列中的3個維度專案會成為單一串連維度專案，顯示每個月第30天在孟買透過行動電話發生的2,056個事件。

| Dimension：城市 | Dimension：裝置型別 | Dimension：日期 | 量度：事件 |
|---------|----------|---------|---------|
| 孟買 | 行動電話 | 30 | 2,056 |
| 紐約 | 平板電腦 | 31 | 1,761 |
| 班加羅爾 | 桌面 | 1 | 1,666 |
| 德里 | 行動電話 | 14 | 1,396 |

此表格在Analysis Workspace中的顯示方式如下：

![多重維度範例](assets/multi-dim-example.png)

## 新增多個維度欄

您可以一次新增一個維度欄或大量新增多個維度欄。

1. 在Analysis Workspace中建立自由表格。

   如需詳細資訊，請參閱[視覺效果概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)中的[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。

1. 新增維度至自由表格。 您可以一次新增一個維度，也可以一次新增多個維度。

   * 將維度一次拖曳一個至自由表格。 將其他維度欄放置在表格中現有維度欄的左側或右側。 將建立新資料行的位置顯示藍色垂直&#x200B;**[!UICONTROL 新增]**&#x200B;行。

     ![拖曳個別維度](assets/dimensions-add-individually.png)

   * 在元件選單中選取最多5個維度，然後將它們拖曳至自由表格。 維度會依照您選取它們的順序，從左到右新增至表格中。

     若要選取多個維度，請按住&#x200B;***命令***&#x200B;鍵(在Mac上)或&#x200B;***Ctrl***&#x200B;鍵（在Windows上）。

     ![拖曳多個維度](assets/dimensions-add-multiple.png)

1. 以單一維度專案的形式檢視表格的每一列。 如需詳細資訊，請參閱[串連維度專案](#concatenated-dimension-items)。

## 篩選和排序表格

您可以對自由格式表格中的欄套用篩選和排序。 您可以依任何欄排序自由表格的資料，無論該欄是維度或量度皆然。 您甚至可以同時依多個欄排序。

如需詳細資訊，請參閱[篩選和排序自由表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

## 多個維度欄和劃分

Analysis Workspace提供下列方式，讓您在自由表格中新增多個維度：

* 包含多個維度欄（如本文所述）

* [加入劃分](/help/components/dimensions/t-breakdown-fa.md)

這兩種方法都可讓您根據其他維度來分析維度。 不過，兩者有一些重要差異，在同一個表格中可使用這兩種方法，以進行更深入的分析。

### 維度欄和劃分之間的差異

多個維度欄可讓您：

* 將維度專案串連到多個維度間的不同資料列。

* 只有當維度專案套用至表格中的每個維度欄時，才可以將維度專案包含在串連列中。 若要完成此操作，請使用欄篩選器取消選取每個維度欄上的&#x200B;**[!UICONTROL 包含「沒有值」]**&#x200B;設定。

  如需詳細資訊，請參閱[依多個資料行排序資料表（進階排序）](#sort-tables-by-multiple-columns-advanced-sorting)。

* 依多個維度和量度欄排序資料，以檢視更多自訂資料。

  如需詳細資訊，請參閱[依多個資料行排序資料表（進階排序）](#sort-tables-by-multiple-columns-advanced-sorting)

劃分可讓您：

* 在自由表格中，依次要維度來劃分維度專案。 您最多可以顯示400個次要維度的維度專案。

### 在含有多個維度欄的表格中加入劃分

當您將劃分新增至具有多個維度欄的表格時，劃分會套用至您新增該表格的列上的串連維度專案（橫跨所有維度欄）。

![多重排序劃分範例](assets/dimensions-multiple-sort-breakdown.png)

此外，您可以在劃分中新增多個維度欄。 劃分中每一列維度專案的行為也類似單一串連維度專案。

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

如需如何新增劃分的詳細資訊，請參閱[劃分維度](/help/components/dimensions/t-breakdown-fa.md)。

## 根據跨越多個維度欄的維度專案建立區段

當您根據橫跨多個維度欄的維度專案建立區段時，每個維度專案都會包含在區段定義中，且And運運算元會聯結這些專案。

如需建立區段的詳細資訊，請參閱[建立區段](/help/components/segments/seg-create.md)。

## 不支援的維度 {#unsupported}

不支援下列維度組合，Analysis Workspace會禁止新增這些組合，或在新增後顯示錯誤訊息：

* 來自參考相同自由表格中一起使用的不同[物件陣列](/help/use-cases/object-arrays.md)之欄位的多個維度。

  如果多個維度參考相同的物件陣列，則可同時在相同的自由表格中。