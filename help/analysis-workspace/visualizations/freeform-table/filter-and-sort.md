---
description: 描述 Analysis Workspace 如何篩選及排序表格的文件。
title: 篩選和排序表格
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 1c11eb1b89eccf33fd66a0914b4beb1ab5dd6ff2
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 79%

---

# 篩選和排序表格

Analysis Workspace 中的自由表格是互動式資料分析的基礎。因此，它們可包含數千列資訊。若要有效地展示最重要的資訊，對資料進行篩選和排序相當重要。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 篩選表格 {#section_36E92E31442B4EBCB052073590C1F025}

Analysis Workspace 中的篩選器可協助您找出最重要的資訊。

>[!NOTE]
>
> 只能依本節所述篩選動態維度項目。 無法篩選靜態維度項目。 如需詳細資訊，請參閱 [自由表格中的動態與靜態維度項目](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### 快速從表格中排除特定列

您無需開啟「篩選」對話方塊，即可從表格中快速排除特定列。

>[!NOTE]
>
>如本節所述，排除列時， [!UICONTROL **一律排除項目**] 規則會自動套用至進階篩選對話方塊。 (您可以選取「篩選」圖示，然後 [**[!UICONTROL 顯示高級]**](#apply-a-simple-or-advanced-filter-to-a-table).)

若要從自由表格中快速排除特定列：

1. 將滑鼠指標暫留在您要排除的列上，然後選取x圖示。

   按住Shift鍵以選取範圍列，或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）以選取多個列。

### 將簡單或高級篩選器應用於表

若要篩選自由表格中的資料：

1. 將滑鼠移至包含您要篩選之資料的欄上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 選取出現的&#x200B;**篩選**&#x200B;圖示。

   ![表格中的篩選器圖示](assets/table-filter-icon.png)

   提供下列選項：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **搜尋字詞或片語**] | 指定要篩選的字詞或片語。 只顯示包含指定字詞或確切片語的行。 |
   | [!UICONTROL **包含未指定 (無)**] | 選擇此選項可在表格中顯示不屬於任何表格維度的資料。<!--what is this?--> |

1. (選用) 若要依不同條件或依多個條件篩選，請選取&#x200B;[!UICONTROL **顯示進階**]。

   提供下列選項：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **包含未指定 (無)**] | 選擇此選項可在表格中顯示不屬於任何表格維度的資料。<!--what is this?--> |
   | [!UICONTROL **符合**] | <p>選擇&#x200B;[!UICONTROL **如果滿足所有條件**]&#x200B;即可僅顯示符合您指定之所有條件的資料。 此選項通常會產生更精細的資料。</p> <p>選擇&#x200B;[!UICONTROL **如果符合任何條件**]&#x200B;即可顯示符合您指定之任何篩選條件的資料。 此選項通常會產生較少精細的資料。</p> |
   | [!UICONTROL **標準**] | <p>從下列篩選選項中選取：</p><p>(選擇&#x200B;[!UICONTROL **新增列**]&#x200B;新增多個篩選條件。 您在&#x200B;[!UICONTROL **符合**]&#x200B;區段選擇的選項決定是否必須滿足您新增的全部或任何條件。)</p><ul><li><p>[!UICONTROL **包含片語**]：篩選結果中只會包含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。<p>這是執行簡單搜尋時的預設設定。</p></p></li><li><p>[!UICONTROL **包含任何詞語**]：篩選結果中只會包含來自您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **包含所有詞語**]：篩選結果中只會包含來自您所指定片語的所有字詞的資料。字詞不必按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</p></li><li><p>[!UICONTROL **不包含任何詞語**]：篩選結果中只會顯示不含您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **不包含片語**]：篩選結果中只會顯示不含您指定之確切片語的資料。 字詞必須按照&#x200B;[!UICONTROL **搜尋字詞或片語欄位**]&#x200B;中指定的順序排列。</p></li><li><p>[!UICONTROL **等於**]：篩選結果中只會包含與您所指定之片語完全相符的資料。 </p></li><li><p>[!UICONTROL **不等於**]：篩選結果中只會包含與您所指定之片語不完全相符的資料。 </p></li><li><p>[!UICONTROL **開頭為**]：篩選結果中只會包含以您指定的字詞或確切片語開頭的資料。 </p></li><li><p>[!UICONTROL **結尾為**]：篩選結果中只會包含以您指定的字詞或確切片語結尾的資料。 </p></li></ul> |
   | [!UICONTROL **永遠排除項目**] | 指定要從篩選資料中排除的任何項目的名稱。 |

1. 選擇&#x200B;[!UICONTROL **套用**]&#x200B;以篩選資料。

   在將篩選器套用至表格時，此&#x200B;**篩選器**&#x200B;圖示![藍色篩選器圖示篩選表格](assets/table-filter-blue-icon.png)會變成藍色。

## 排序表格

您可以依照 Analysis Workspace 中屬於維度或量度的任何欄位，來排序自由格式的資料。

向下箭頭圖示![向下箭頭圖示排序表格欄](assets/table-sort-arrow-icon.png)會顯示在目前依資料排序的欄標題中。

1. 在 Analysis Workspace 中的任意自由表格中，按一下維度或量度名稱旁的箭頭。

   排序時，請考慮以下情況 :

   * 向下箭頭會以降序排列，而向上箭頭 (預設值) 則以升序排列。
   * 您可以依字母順序或數值排序維度。例如，您可能在工作流程中有編號的步驟，而且可能想要依步驟編號排序。您可以依日期排序與日期相關的維度。或者，您也可以依字母順序排序資料來源，如下圖所示。

   ![](assets/sort-dimensions.png)


