---
description: 說明如何在Analysis Workspace中篩選和排序表格的檔案。
title: 篩選及排序表格
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 篩選及排序表格

Analysis Workspace中的自由表格是互動式資料分析的基礎。 因此，它們可包含數千列資訊。 對資料進行過濾和排序，是高效地呈現最重要資訊的關鍵部分。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 篩選表格 {#section_36E92E31442B4EBCB052073590C1F025}

Analysis Workspace中的篩選器可協助您找出最重要的資訊。

若要篩選自由表格中的資料：

1. 在自由表格中，將滑鼠移至包含您要篩選之資料的欄上。 <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 選取 **篩選** 圖示。

   ![表格中的篩選圖示](assets/table-filter-icon.png)

1. 在 [!UICONTROL **搜尋字詞或片語**] 欄位，指定要篩選的字詞或片語。 只顯示包含指定單詞或確切短語的行。

1. （選用）若要依不同條件或依多個條件篩選，請選取 [!UICONTROL **顯示高級**].

   可使用下列選項

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **包含未指定（無）**] | 選擇此選項可顯示不屬於表任何維的表中的資料。 <!--what is this?--> |
   | [!UICONTROL **符合**] | <p>選擇 [!UICONTROL **如果滿足所有條件**] 僅顯示符合您指定之所有條件的資料。 此選項通常會產生更精細的資料。</p> <p>選擇 [!UICONTROL **如果符合任何條件**] 顯示符合您指定之任何篩選條件的資料。 此選項通常會導致精細化的資料較少。</p> |
   | [!UICONTROL **標準**] | <p>從下列篩選選項中選取：</p><p>(選取 [!UICONTROL **新增列**] 新增多個篩選條件。 您在 [!UICONTROL **符合**] 區段會決定您新增的全部或任何條件必須符合。)</p><ul><li><p>[!UICONTROL **包含片語**]:篩選結果中只會包含您指定之確切片語的資料。 字詞必須按 [!UICONTROL **搜尋字詞或片語欄位**].<p>這是執行簡單搜索時的預設設定。</p></p></li><li><p>[!UICONTROL **包含任何詞語**]:篩選結果中只會包含來自您所指定片語的一或多個字詞。 </p></li><li><p>[!UICONTROL **包含所有詞語**]:篩選結果中只會包含來自您所指定片語的所有字詞的資料。 字詞不必按 [!UICONTROL **搜尋字詞或片語欄位**].</p></li><li><p>[!UICONTROL **不包含任何詞語**]:篩選結果中只會包含不含您所指定片語中任何單字的資料。 </p></li><li><p>[!UICONTROL **不包含片語**]:篩選結果中只會包含不含您指定之確切字句的資料。 字詞必須按 [!UICONTROL **搜尋字詞或片語欄位**].</p></li><li><p>[!UICONTROL **等於**]:篩選結果中只會包含與您所指定之片語完全相符的資料。 </p></li><li><p>[!UICONTROL **不等於**]:篩選結果中只會包含與您指定的片語不完全相符的資料。 </p></li><li><p>[!UICONTROL **開頭為**]:篩選結果中只會包含以您指定的字詞或確切字句開頭的資料。 </p></li><li><p>[!UICONTROL **結尾為**]:篩選結果中只會包含以您指定的字詞或確切字句結尾的資料。 </p></li></ul> |
   | [!UICONTROL **永遠排除項目**] | 指定要從篩選資料中排除的任何項目的名稱。 |

1. 選擇 [!UICONTROL **套用**] 來篩選資料。

   此 **篩選** 圖示 ![藍色篩選表徵圖篩選表](assets/table-filter-blue-icon.png) 將篩選器套用至表格時，會變成藍色。

## 對表進行排序

您可以依Analysis Workspace中屬於Dimension或量度的任何欄，來排序自由表格的資料。

向下箭頭表徵圖 ![向下箭頭表徵圖排序的表列](assets/table-sort-arrow-icon.png) 會顯示在目前依資料排序的欄標題中。

1. 在Analysis Workspace中的任何自由表格中，按一下Dimension或量度名稱旁的箭頭。

   排序時，請考量下列事項：

   * 向下箭頭會依遞減順序排序，而向上箭頭 (預設值) 則依遞增順序排序。
   * 您可以依字母或數字將Dimension排序。 例如，您可能在工作流程中有編號的步驟，而且可能想要依步驟編號排序。您可以依日期排序與日期相關的維度。或者，您可以依字母順序排序資料來源，如下圖所示。

   ![](assets/sort-dimensions.png)


