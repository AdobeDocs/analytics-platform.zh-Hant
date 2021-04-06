---
description: 面板是表格和視覺化的集合
title: 面板概述
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 8%

---

# 面板概述

[!UICONTROL 面板]是表格和視覺化的集合。 您可以從工作區的左上角圖示或[空白麵板](/help/analysis-workspace/c-panels/blank-panel.md)存取面板。 當您想要根據時段、資料檢視或分析使用案例來組織專案時，面板會很有幫助。 Analysis Workspace提供下列面板類型：

| 面板名稱 | 說明 |
| --- | --- |
| [空白面板](/help/analysis-workspace/c-panels/blank-panel.md) | 從可用的面板和視覺化中選擇，以開始分析。 |
| [快速深入分析面板](quickinsight.md) | 快速建立自由格式表格和隨附的視覺效果，以更快速分析及揭秘深入分析。 |
| [歸因面板](attribution.md) | 使用任何維度和轉換度量，快速比較和視覺化任何數量的歸因模型。 |
| [自由表格面板](freeform-panel.md) | 執行不限次數的比較和劃分，然後新增視覺化來呈現豐富的資料故事。 |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights]、  Blank和  Freeformpanels是開始分析的絕佳場所，而 [!UICONTROL Attribution ] IQ則適用於更進階的分析。專案中也有 `"+"` 按鈕可供使用，讓您隨時都可以新增空白面板。

預設的起始面板是[!UICONTROL Freeform]面板，但您也可以將[空白麵板](/help/analysis-workspace/c-panels/blank-panel.md)設為預設面板。

## 日曆 {#calendar}

面板日曆控制面板中表格和視覺化的報告範圍。

注意：如果在表格、視覺化或面板Dropzone中使用（紫色）日期範圍元件，則會覆寫面板日曆。

![](assets/panel-calendar.png)

## Dropzone {#dropzone}

面板下拉區可讓您將篩選和下拉式篩選套用至面板內的所有表格和視覺化。 您可以套用一或多個篩選器至面板。 您可以按一下編輯鉛筆來修改每個濾鏡上方的標題，或以滑鼠右鍵按一下以完全移除。

### 篩選條件

從左側導軌將任何濾鏡拖放至面板拖放區，開始篩選面板。

![](assets/segment-filter.png)

### 臨機篩選

您也可以將非篩選元件直接拖曳至dropzone中，以建立臨機篩選，為您省下前往篩選產生器的時間和心力。 以此方式建立的篩選器會自動定義為點擊層級篩選器。 按一下篩選旁的資訊圖示(i)，然後鉛筆形編輯圖示，然後在「篩選產生器」中編輯，即可修改此定義。

臨機篩選器是專案的本機篩選器，除非您公開，否則不會顯示在左側導軌中。

![](assets/adhoc-segment-filter.png)

### 下拉式篩選器{#dropdown-filter}

除了篩選之外，下拉式篩選還可讓您以控制方式與資料互動。 例如，您可以新增「行動裝置類型」的下拉式篩選，以便依平板電腦、行動電話或案頭來篩選面板。

下拉式篩選器也可用來將許多專案合併為一個專案。 例如，如果您有許多版本的相同專案已套用不同的「國家」篩選條件，則可以將所有版本合併為單一專案，並新增「國家」下拉式篩選條件。

![](assets/dropdown-filter-intro.png)

若要建立下拉式篩選：

1. 若要使用[!UICONTROL Dimension項目]建立下拉式篩選，例如[!UICONTROL 行銷管道]維度中的值，請按一下左側導軌中維度旁的右箭頭圖示。 這會公開所有可用項目。 從左側導軌中選取一或多個元件項目，並在按住Shift鍵的同時將其拖放至面板拖放區域&#x200B;**。**&#x200B;這會將元件轉換為下拉式篩選，而非單一篩選。
1. 若要使用其他元件（例如度量、篩選器或日期範圍）建立下拉式篩選，請從左側導軌中的一個元件類型中選取，然後拖曳至面板下拉區&#x200B;**，同時按住Shift鍵**。
1. 從下拉式清單中選取其中一個選項，以變更面板中的資料。 您也可以選擇&#x200B;**[!UICONTROL 無篩選器]**，選擇不篩選任何面板資料。

![](assets/create-dropdown.png)

[觀看影](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) 片，進一步瞭解如何將下拉式篩選器新增至專案。

## 按一下右鍵菜單{#right-click}

以滑鼠右鍵按一下面板標題，即可使用面板的其他功能。

![](assets/right-click-menu.png)

可使用下列設定：

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 插入複製的面板／視覺化] | 可讓您將複製的面板或視覺化貼到（「插入」）專案內的其他位置，或貼到完全不同的專案中。 |
| [!UICONTROL 複製面板] | 可讓您按一下滑鼠右鍵並複製面板，以便將面板插入專案內的其他位置，或插入完全不同的專案。 |
| [!UICONTROL 複製面板] | 請精確複製目前的面板，然後您可加以修改。 |
| [!UICONTROL 收合／展開所有面板] | 折疊並展開所有專案面板。 |
| [!UICONTROL 收合／展開面板中的所有視覺化] | 折疊並展開目前面板中的所有視覺化。 |
| [!UICONTROL 編輯描述] | 新增（或編輯）面板的文字說明。 |
| [!UICONTROL 取得面板連結] | 讓您可將使用者直接導向專案中的特定面板。點按連結時，收件者必須先登入，才能被導向到連結的確切面板。 |
