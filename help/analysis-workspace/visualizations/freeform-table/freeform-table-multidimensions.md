---
title: 在自由格式表格中包含多個維度
description: 瞭解如何在自由格式表格中包含多個維度
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: bff352181392c19b6c4fe70893a016179fb77f06
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 2%

---

# 在自由格式表格中包含多個維度

{{release-limited-testing}}

您最多可以在自由表格中包含5個維度欄，讓您並排檢視多個維度專案。 每一列維度專案都會當作單一串連專案。

您可以排序維度欄（連同量度欄），以獲得更完整和自訂的分析。

## 多個維度欄和劃分

Analysis Workspace提供下列方式，讓您在自由表格中新增多個維度：

* 包含多個維度欄（如本文所述）

* [加入劃分](/help/components/dimensions/t-breakdown-fa.md)

這兩種方法都可讓您根據其他維度來分析維度。 不過，兩者有一些重要差異，在同一個表格中可使用這兩種方法，以進行更深入的分析。

多個維度欄可讓您：

* 跨多個維度和量度將資料列建立關聯。

* 只有在資料套用至表格中的每個維度欄時，才顯示資料。 若要完成此操作，請使用欄篩選器取消選取每個維度欄上的&#x200B;**[!UICONTROL 包含「沒有值」]**&#x200B;設定。

  如需詳細資訊，請參閱[篩選及排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

* 依多個維度和量度欄排序資料。

  如需詳細資訊，請參閱[篩選及排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

劃分可讓您：

* 僅顯示一個的維度專案

* 顯示單一排名最前的維度專案

## 新增維度欄

您可以一次新增一個維度欄或大量新增維度欄。

1. 在Analysis Workspace中建立自由表格。

   如需詳細資訊，請參閱[視覺效果概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)中的[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。

1. 新增維度至自由表格。 您可以一次新增一個維度，也可以一次新增多個維度。

   * 將維度一次拖曳一個至自由表格。 將其他維度欄放置在表格中現有維度欄的左側或右側。 將建立新資料行的位置顯示藍色垂直&#x200B;**[!UICONTROL 新增]**&#x200B;行。

     ![拖曳個別維度](assets/dimensions-add-individually.png)

   * 在元件選單中選取最多5個維度，然後將它們拖曳至自由表格。 維度會以您選取的順序從左到右新增至表格中。

     若要選取多個維度，請按住&#x200B;***命令***&#x200B;鍵(在Mac上)或&#x200B;***Ctrl***&#x200B;鍵（在Windows上）。

     ![拖曳多個維度](assets/dimensions-add-multiple.png)

## 篩選表格

如需篩選表格的資訊，請參閱[篩選及排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables)中的[篩選表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

## 排序表格 {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails article. -->

您可以依Analysis Workspace中維度或量度任一欄來排序自由表格資料。

依預設，維度會依遞增順序排序，量度則依遞減順序排序。

### 依單一欄排序表格

依照本節所述排序單一資料行的資料時，套用至資料表的所有[進階排序](#sort-tables-by-multiple-columns-advanced-sorting)都會被移除。

若要依單一欄排序表格中的資料，請執行下列動作：

1. 將游標移至您要排序的資料行標頭上，然後選取&#x200B;**排序**&#x200B;圖示![排序](/help/assets/icons/SortOrderDown.svg) （當它出現時）。

   ![排序下拉式功能表](assets/sort-dropdown-menu.png)

1. 選取&#x200B;**[!UICONTROL 遞增]**&#x200B;或&#x200B;**[!UICONTROL 遞減]**。

   將排序套用至欄時，排序圖示保持可見。 箭頭表示資料的排序方式（![排序](/help/assets/icons/SortOrderUp.svg)為遞增或![排序](/help/assets/icons/SortOrderDown.svg)為遞減）。

### 依多個欄排序表格（進階排序）

{{release-limited-testing-section}}

#### 將排序套用至多個欄

若要依多欄排序表格中的資料，請執行下列動作：

1. 將游標移至您要排序之任何資料行的標頭上，然後選取&#x200B;**排序**&#x200B;圖示![排序](/help/assets/icons/SortOrderDown.svg) （當它出現時）。

   ![排序下拉式功能表](assets/sort-dropdown-menu.png)

1. 選取&#x200B;**[!UICONTROL 進階排序]**。

   ![進階排序對話方塊](assets/sort-advanced-dialog.png)

1. 在進階排序對話方塊中，執行下列任一項作業：

   * 選取&#x200B;**[!UICONTROL 新增排序資料行]**&#x200B;按鈕，以新增尚未排序的資料行。

   * 選取&#x200B;**移除**&#x200B;圖示![移除](/help/assets/icons/Close.svg)，移除您不再想要排序的欄。

   * 在清單中上下拖曳欄，以調整排序優先順序。

     如需詳細資訊，請參閱[排序優先順序](#sort-priority)。

   * 在下拉式功能表中選取&#x200B;**[!UICONTROL 遞增]**&#x200B;或&#x200B;**[!UICONTROL 遞減]**，以變更排序值。

   * 選取欄名稱下拉式功能表，以選取不同的欄。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

將排序套用至欄時，排序圖示仍會保持可見。 箭頭表示資料的排序方式（![排序](/help/assets/icons/SortOrderUp.svg)為遞增或![排序](/help/assets/icons/SortOrderDown.svg)為遞減）。

![多重排序範例](assets/dimensions-multiple-sort.png)

#### 排序優先順序

當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序排序。 優先順序編號會顯示在排序圖示![排序優先順序圖示](assets/sort-priority-icon.png)旁邊。

具有主要優先順序的欄決定主要順序，具有次要優先順序的欄決定主要欄中列具有相同值的順序，具有第三優先順序的欄決定主要欄和次要欄中列具有相同值的順序，依此類推。

例如，假設表格中包含下列資料欄：

* 日期（維度）

* 小時（維度）

* 事件（量度）

您可以為每個欄指派排序優先順序，如下所示：

| 欄（元件）名稱 | 元件類型 | 排序優先順序 |
|---------|----------|---------|
| 當月日期 | 維度 | 1 |
| 小時 | 維度 | 2 |
| 活動 | 量度 | 3 |

藉由為每一欄指定排序優先順序，您可以精確控制資料在表格中的顯示方式。 在此範例中，資訊會先依月中的日排序，再依日中的小時排序，最後依事件排序。

![多重排序範例](assets/dimensions-multiple-sort.png)

## 在含有多個維度欄的表格中加入劃分

當您將劃分新增至具有多個維度欄的表格時，劃分會跨越新增所在的列上的所有維度專案。

您可以新增劃分，如[劃分維度](/help/components/dimensions/t-breakdown-fa.md)中所述。

## 不支援的維度 {#unsupported}

不支援下列維度組合，Analysis Workspace會禁止新增這些組合，或在新增後顯示錯誤訊息：

* 來自參考相同自由表格中一起使用的不同[物件陣列](/help/use-cases/object-arrays.md)之欄位的多個維度。

  如果多個維度參考相同的物件陣列，則可同時在相同的自由表格中。