---
description: 描述 Analysis Workspace 如何篩選及排序表格的文件。
title: 篩選和排序表格
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: a9976a053021b2b0ac26daaad2cfe89f8af61a96
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 42%

---

# 篩選和排序自由格式表格

Analysis Workspace 中的自由表格是互動式資料分析的基礎。因此，它們可包含數千列資訊。若要有效地展示最重要的資訊，對資料進行篩選和排序相當重要。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 篩選表格

Analysis Workspace 中的篩選器可協助您找出最重要的資訊。

>[!NOTE]
>
> 如本節所述，只能篩選動態維度專案。 無法篩選靜態維度專案。 如需詳細資訊，請參閱自由表格中的[動態與靜態維度專案](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。

您可以使用數種方法來篩選自由格式表格中的列。

- 從表格中排除特定列
- 套用篩選器至表格
- 使用對象篩選器

請務必閱讀每個方法如何影響[自由表格總計](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)。

### 從表格中排除特定列

您可以快速排除表格中的特定列，而不需要使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**。

>[!NOTE]
>
>如本節所述，當您排除資料列時，[!UICONTROL 進階]篩選對話方塊中會自動新增[!UICONTROL 永遠排除專案]規則。 您可以選取![篩選器](/help/assets/icons/Filter.svg)篩選器圖示，然後選取[**[!UICONTROL 顯示進階]**](#apply-a-simple-or-advanced-filter-to-a-table)，以檢視套用的規則。

若要從自由表格中排除特定列：

1. 將游標停留在要排除的列上，然後選取![關閉](/help/assets/icons/Close.svg)。

   按住Shift鍵以選取一定範圍的列，或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）以選取多個列。

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### 套用簡單或進階篩選器至表格

若要篩選自由表格中的資料：

1. 將游標停留在包含要篩選之資料的欄上。<!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 選取![篩選器](/help/assets/icons/Filter.svg) **篩選器** （出現時）。

   ![自由表格醒目提示篩選圖示。](assets/table-filter-icon.png)

   **[!UICONTROL 搜尋]**&#x200B;對話方塊中有下列選項：

   ![簡單篩選](assets/filter-simple.png){width="500"}

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **包含「沒有值」**] | 選取此選項以在資料表中針對選取的維度沒有值的資料顯示&#x200B;**[!UICONTROL 沒有值]**&#x200B;列。 取消選取此選項以隱藏&#x200B;**[!UICONTROL 沒有值]**&#x200B;列。 |
   | [!UICONTROL **搜尋字詞或片語**] | 指定您要用來篩選的字詞或片語。 只顯示包含指定字詞或確切片語的行。 |


1. (選用) 若要依不同條件或依多個條件篩選，請選取&#x200B;[!UICONTROL **顯示進階**]。

   下列進階篩選選項可供使用：

   ![簡單篩選](assets/filter-advanced.png){width=500}

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **包含「沒有值」**] | 選取此選項以在資料表中針對選取的維度沒有值的資料顯示&#x200B;**[!UICONTROL 沒有值]**&#x200B;列。 取消選取此選項以隱藏&#x200B;**[!UICONTROL 沒有值]**&#x200B;列。 |
   | [!UICONTROL **符合**] | 選擇&#x200B;[!UICONTROL **如果滿足所有條件**]&#x200B;即可僅顯示符合您指定之所有條件的資料。 此選項通常會產生更精細的資料。<br/><br/>選擇&#x200B;[!UICONTROL **如果符合任何條件**]&#x200B;以顯示符合您指定之任何篩選條件的資料。 此選項通常會產生較少精細的資料。 |
   | [!UICONTROL **標準**] | 從下列篩選選項中選取：<br/><ul><li>[!UICONTROL **包含片語**] （預設）：篩選結果中只會包含您指定的片語資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</li><li>[!UICONTROL **包含任何詞語**]：篩選結果中只會包含來自您所指定片語的一或多個字詞。 </li><li>[!UICONTROL **包含所有詞語**]：篩選結果中只會包含來自您所指定片語的所有字詞的資料。字詞不必按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</li><li>[!UICONTROL **不包含任何詞語**]：篩選結果中只會顯示不含您所指定片語的一或多個字詞。 </li><li>[!UICONTROL **不包含片語**]：篩選結果中只會顯示不含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</li><li>[!UICONTROL **等於**]：篩選結果中只會包含完全符合您指定之片語的資料。 </li><li>[!UICONTROL **不等於**]：篩選結果中只會包含與您所指定之片語不完全相符的資料。 </li><li>[!UICONTROL **開頭為**]：篩選結果中只會包含以您指定的字詞或確切片語開頭的資料。 </li><li>[!UICONTROL **結尾為**]：篩選結果中只會包含以您指定的字詞或確切片語結尾的資料。 </li></ul>選取![新增](/help/assets/icons/Add.svg) [!UICONTROL **新增列**]&#x200B;以新增多個篩選條件。 您為&#x200B;[!UICONTROL **符合**]&#x200B;選取的選項會決定&#x200B;**[!UICONTROL 如果符合所有條件]**&#x200B;或&#x200B;**[!UICONTROL 如果符合任何條件]**。 |
   | [!UICONTROL **永遠排除項目**] | 指定要從篩選資料中排除的任何項目的名稱。 |

1. 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以篩選資料。 選取&#x200B;**[!UICONTROL 清除]**&#x200B;以清除所有輸入。 選取&#x200B;**[!UICONTROL 取消]**&#x200B;以取消並關閉對話方塊。 <br/>將篩選器套用至表格時，彩色![篩選器](/help/assets/icons/FilterColored.svg) **篩選器**&#x200B;圖示會指出並顯示詳細資訊。

### 使用對象篩選器

如需詳細資訊，請參閱[篩選器總覽](/help/components/filters/filters-overview.md)。

## 排序表格

您可以依Analysis Workspace中維度或量度任一欄來排序自由表格的資料。 箭頭表示資料的排序方式(**↓**&#x200B;為遞減，或&#x200B;**↑**&#x200B;為遞增)。

![排序](assets/sorting.gif)
