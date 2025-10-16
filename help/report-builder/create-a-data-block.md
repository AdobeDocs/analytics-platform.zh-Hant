---
title: 如何在Customer Journey Analytics中使用Report Builder建立資料區塊
description: 說明如何建立資料區塊。
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 7d3300336a955facc230f335d1452096700ea98b
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 24%

---

# 建立資料區塊

*資料區塊*&#x200B;是由單一資料請求所建立的資料表。Report Builder 活頁簿可包含多個資料區塊。當您建立資料區塊時，請先設定資料區塊，然後再建置資料區塊。

## 設定資料區塊

為資料區塊位置、資料檢視和日期範圍設定初始資料區塊引數。

1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 建立]**。

   ![顯示[建立資料區塊]選項的熒幕擷圖](./assets/create-data-block.png){zoomable="yes"}


1. 設定&#x200B;**[!UICONTROL 資料區塊地點]**。

   資料區塊位置選項會定義Report Builder將資料新增至工作表的工作表位置。

   若要指定資料區塊位置，請在工作表中選取單一儲存格或輸入儲存格位址，例如`a3`、`\\\$a3`、`a\\\$3`或`sheet1!a2`。 擷取資料時，指定的儲存格會變成資料區塊的左上角。

   使用![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)從工作表中目前選取的儲存格中挑選資料區塊位置。

1. 選擇&#x200B;**[!UICONTROL 資料檢視]**。

   「資料檢視」選項可讓您從下拉式選單選擇資料檢視或是從儲存格位置引用資料檢視。

   選取![DataViewSelector](/help/assets/icons/DataViewSelector.svg)以從儲存格建立資料檢視。

1. 設定&#x200B;**[!UICONTROL 日期範圍]**。

   **[!UICONTROL 日期範圍]**&#x200B;選項可讓您選擇日期範圍。 日期範圍可以是固定或滾動式。

   選取「**[!UICONTROL 行事曆]**」以使用「![行事曆](/help/assets/icons/Calendar.svg)」挑選資料範圍，或手動輸入日期範圍。 您可以選擇從&#x200B;**[!UICONTROL _搜尋預設集_]**&#x200B;下拉式功能表中選取預設集。

   選取&#x200B;**[!UICONTROL 從儲存格]**&#x200B;以根據目前工作表中的儲存格定義開始和結束資料。

   如需日期範圍選項的詳細資訊，請參閱[選取日期範圍](select-date-range.md)。

1. 選取&#x200B;**[!UICONTROL 「下一步」]**。

   ![顯示日期範圍選項和作用中[下一步]按鈕的熒幕擷圖。](./assets/choose_date_data_view3.png)

   設定資料區塊後，您可以選取維度、量度和區段來建置資料區塊。 **[!UICONTROL 維度]**、**[!UICONTROL 量度]**&#x200B;和&#x200B;**[!UICONTROL 區段]**&#x200B;索引標籤會顯示在&#x200B;**[!UICONTROL 表格]**&#x200B;窗格上方。

## 建置資料區塊

若要建置資料區塊，請選取報表元件，然後自訂版面配置。

1. 新增&#x200B;**[!UICONTROL 維度]**、**[!UICONTROL 量度]**&#x200B;和&#x200B;**[!UICONTROL 區段]**&#x200B;元件。

   捲動元件清單或使用![搜尋](/help/assets/icons/Search.svg) **[!UICONTROL _搜尋元件_]**&#x200B;欄位來尋找元件。 將元件拖放至[!UICONTROL 表格]窗格，或在清單中重複選取元件名稱，以將元件新增至[!UICONTROL 表格]窗格。

   連按兩下元件，將該元件新增至表格的預設區段。

   - Dimension元件已新增至![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**&#x200B;區段，或新增至![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**&#x200B;區段（如果您在欄中已經有維度）。
   - 日期元件已新增至![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**&#x200B;區段。
   - 區段元件已新增至![區段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 區段]**&#x200B;區段。
   - 已將量度元件新增至![事件](/help/assets/icons/Event.svg) **[!UICONTROL 值]**&#x200B;區段。

1. 安排「表格」窗格中的項目，以自訂資料區塊的版面配置。

   拖放表格窗格中每個清單內的元件，以重新排序元件，或選取![MoreSmall](/help/assets/icons/MoreSmall.svg)，然後選取![向上箭頭](/help/assets/icons/ArrowUp.svg)、向上箭頭![、向下箭頭](/help/assets/icons/ArrowDown.svg)、以及更多以移動清單內的元件。

   當您將元件加入表格時，工作表中的「資料區塊」位置會顯示資料區塊的預覽。資料區塊預覽的版面配置會隨著您新增、移動或移除表格中的項目而自動更新。

   ![熒幕擷圖顯示新增的元件和更新的工作表。](./assets/image10.png)


1. 選擇性地將&#x200B;**[!UICONTROL 開始日期]**&#x200B;設定為維度，以識別資料區塊的開始日期。 如果您有週期性排程報表，且報表具有滾動式日期範圍，則新增開始資料為維度會很有幫助。 或者，如果您有非常規的日期範圍，並且您需要明確說明開始日期。

   ![熒幕擷圖顯示維度清單中的開始日期。](./assets/start-date-dimension.png)

1. 選擇性地顯示或隱藏列與欄標題。 若要進行此步驟：

   1. 選取&#x200B;**[!UICONTROL 表格]** ![設定](/help/assets/icons/Setting.svg)設定圖示。

      ![顯示[資料表設定]選項的熒幕擷圖。](./assets/table-settings.png)

   1. 核取或取消核取&#x200B;**[!UICONTROL 顯示列與欄標題]**&#x200B;的選項。 預設會顯示標題。

1. 或者，您也可以隱藏或顯示維度標籤和量度標題。 若要進行此步驟：

   1. 在維度標籤或欄標題上選取![MoreSmall](/help/assets/icons/MoreSmall.svg)以顯示內容功能表。

      ![列區段中的省略符號圖示。](./assets/row-heading.png)

   1. 選取![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]**&#x200B;或![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]**&#x200B;以切換維度標籤或欄標題。 預設會顯示所有標籤。

1. 選取&#x200B;**[!UICONTROL 完成]**&#x200B;以完成資料區塊的設定。

1. 擷取分析資料時，會顯示處理訊息&#x200B;**[!UICONTROL #BUSY]**。

   ![處理訊息。](./assets/image11.png)

1. Report Builder 會擷取資料，並在工作表中顯示已完成的資料區塊。

   ![完成的資料區塊。](./assets/image12.png)


>[!MORELIKETHIS]
>
>[選取資料檢視](select-data-view.md)
>&#x200B;>[選取日期範圍](select-date-range.md)
>&#x200B;>[篩選維度](filter-dimensions.md)
>&#x200B;>[使用區段](work-with-filters.md)
>
