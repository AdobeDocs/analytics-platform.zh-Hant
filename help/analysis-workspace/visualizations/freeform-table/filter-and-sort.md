---
description: 描述 Analysis Workspace 如何篩選及排序表格的文件。
title: 篩選和排序表格
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 67%

---


# 篩選和排序自由格式表格

Analysis Workspace 中的自由表格是互動式資料分析的基礎。因此，它們可包含數千列資訊。若要有效地展示最重要的資訊，對資料進行篩選和排序相當重要。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 篩選表格

Analysis Workspace 中的篩選器可協助您找出最重要的資訊。

>[!NOTE]
>
> 如本節所述，只能篩選動態維度專案。 無法篩選靜態維度專案。 如需詳細資訊，請參閱 [自由表格中的動態與靜態維度專案](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## 篩選自由表格列

您可以使用數種方法來篩選自由格式表格中的列。 

- 按一下列中的「X」
- 按一下右鍵>刪除選取的列
- 表格篩選器
- 區段

請務必閱讀每種方法的影響 [自由格式表格總計](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### 從表格中快速排除特定列

您可以快速從表格中排除特定列，而無需開啟「篩選」對話方塊。

>[!NOTE]
>
>如本節所述排除列時， [!UICONTROL **永遠排除專案**] 規則會自動套用到進階篩選器對話方塊中。 (您可以選取「篩選」圖示，然後選取 [**[!UICONTROL 顯示進階]**](#apply-a-simple-or-advanced-filter-to-a-table).)

若要快速從自由格式表格中排除特定列：

1. 將游標停留在您要排除的列上，然後選取x圖示。

   按住Shift鍵以選取一定範圍的列，或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）以選取多個列。

### 按一下右鍵>刪除選取的列

1. 選取1或多個列。
1. 按一下右鍵並選取 **[!UICONTROL 刪除選取的列]**.

   此動作將從表格中移除列並套用表格篩選器。

### 套用簡單或進階篩選器至表格

若要篩選自由表格中的資料：

1. 將游標停留在包含要篩選之資料的欄上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 選取出現的&#x200B;**篩選**&#x200B;圖示。

   ![反白顯示「篩選」圖示的自由格式表格。](assets/table-filter-icon.png)

   提供下列選項：

   | 選項 | 功能 |
   |---------|----------|
   | [!UICONTROL **搜尋字詞或片語**] | 指定您要用來篩選的字詞或片語。 只顯示包含指定字詞或確切片語的行。 |
   | [!UICONTROL **包含未指定 (無)**] | 選擇此選項可在表格中顯示不屬於任何表格維度的資料。<!--what is this?--> |

1. (選用) 若要依不同條件或依多個條件篩選，請選取&#x200B;[!UICONTROL **顯示進階**]。

   下列進階篩選選項可供使用：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **包含未指定 (無)**] | 選擇此選項可在表格中顯示不屬於任何表格維度的資料。<!--what is this?--> |
   | [!UICONTROL **符合**] | <p>選擇&#x200B;[!UICONTROL **如果滿足所有條件**]&#x200B;即可僅顯示符合您指定之所有條件的資料。 此選項通常會產生更精細的資料。</p> <p>選擇&#x200B;[!UICONTROL **如果符合任何條件**]&#x200B;即可顯示符合您指定之任何篩選條件的資料。 此選項通常會產生較少精細的資料。</p> |
   | [!UICONTROL **標準**] | <p>從下列篩選選項中選取：</p><p>(選擇&#x200B;[!UICONTROL **新增列**]&#x200B;新增多個篩選條件。 您在&#x200B;[!UICONTROL **符合**]&#x200B;區段選擇的選項決定是否必須滿足您新增的全部或任何條件。)</p><ul><li><p>[!UICONTROL **包含片語**]：篩選結果中只會包含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。<p>這是執行簡單搜尋時的預設設定。</p></p></li><li><p>[!UICONTROL **包含任何詞語**]：篩選結果中只會包含來自您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **包含所有詞語**]：篩選結果中只會包含來自您所指定片語的所有字詞的資料。字詞不必按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</p></li><li><p>[!UICONTROL **不包含任何詞語**]：篩選結果中只會顯示不含您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **不包含片語**]：篩選結果中只會顯示不含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</p></li><li><p>[!UICONTROL **等於**]：篩選結果中只會包含與您所指定之片語完全相符的資料。 </p></li><li><p>[!UICONTROL **不等於**]：篩選結果中只會包含與您所指定之片語不完全相符的資料。 </p></li><li><p>[!UICONTROL **開頭為**]：篩選結果中只會包含以您指定的字詞或確切片語開頭的資料。 </p></li><li><p>[!UICONTROL **結尾為**]：篩選結果中只會包含以您指定的字詞或確切片語結尾的資料。 </p></li></ul> |
   | [!UICONTROL **永遠排除項目**] | 指定要從篩選資料中排除的任何項目的名稱。 |

1. 選擇&#x200B;[!UICONTROL **套用**]&#x200B;以篩選資料。

   在將篩選器套用至表格時，此&#x200B;**篩選器**&#x200B;圖示![藍色篩選器圖示篩選表格](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)會變成藍色。

### 篩選器

請參閱我們的 [篩選檔案](/help/components/filters/filters-overview.md) 以取得更多詳細資料。

## 排序表格

您可以依Analysis Workspace中維度或量度任一欄來排序自由表格的資料。

向下箭頭圖示![向下箭頭圖示排序表格欄](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)會顯示在目前依資料排序的欄標題中。

1. 在Analysis Workspace的任何自由表格中，按一下維度或量度名稱旁的箭頭。

   排序時，請考慮以下情況 :

   - 向下箭頭會以降序排列，而向上箭頭 (預設值) 則以升序排列。
   - 您可以依字母順序或數值排序維度。例如，您可能在工作流程中有編號的步驟，而且可能想要依步驟編號排序。您可以依日期排序與日期相關的維度。或者，您也可以依字母順序排序資料來源，如下圖所示。

   ![「資料來源」檢視會醒目顯示排序圖示。](assets/sort-dimensions.png)


