---
title: Customer Journey Analytics 中有什麼元件？
description: 了解 CJA 提供哪些元件，以及如何在報表中使用這些元件。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: d431e781eb18eb3f4904094972c218a9e80980d9
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 62%

---

# 元件概觀

元件是 Customer Journey Analytics 中的功能，可用於報表或與報表功能搭配使用。您可以使用下列步驟管理這些元件：

1. 使用您的 Adobe ID 憑證登入 [analytics.adobe.com](https://analytics.adobe.com)。
2. 導覽至頁首功能表中的[!UICONTROL 元件] > [!UICONTROL 元件]。

您可以管理下列元件：

* [**註解**](/help/components/annotations/overview.md)：將內容相關的資料細微差別和深入解析傳達給您的組織。
* [**篩選器**](filters/filters-overview.md)：排除部分資料，以聚焦於常見的維度項目
* [**計算量度**](calc-metrics/calc-metr-overview.md)：將量度和公式作為新元件用於報告中
* [**日期範圍**](date-ranges/overview.md)：自訂和調整 Analysis Workspace 提供的日期範圍
* [**專案**](/help/analysis-workspace/home.md)：在 Analysis Workspace 中組織和維護專案

## Analysis Workspace 元件

Analysis Workspace 中的元件包含量度、維度、篩選器及時間粒度，您可將它們拖放至專案上。您建立的自訂元件會加入這些面板，例如自訂日期範圍。

若要存取「元件」面板，請按一下左側邊欄中的&#x200B;**[!UICONTROL 元件]**&#x200B;圖示。您可以利用左欄圖示或[快捷鍵](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)，在各面板 (空白面板、[自由表格面板](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)、[快速深入分析面板](/help/analysis-workspace/c-panels/quickinsight.md)或 [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) 面板)、[視覺化效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)和元件之間來回切換。

![](assets/components.png)

請參閱[建立專案](/help/analysis-workspace/home.md)，以了解在專案中使用元件的詳細資訊。

## 元件動作

您可以透過多種方式管理元件 (個別或選取多個元件)。以滑鼠右鍵按一下元件，或按一下元件清單頂端的&#x200B;**[!UICONTROL 動作]**。

>[!NOTE]
>
>此類動作不適用於「時間」元件。

| 元件動作 | 說明 |
| --- | --- |
| 標記 | 以套用標記的方式組織或管理元件。接著元件會在相關的元件管理器中顯示，例如 [!UICONTROL Analytics] > [!UICONTROL 元件] > [!UICONTROL 篩選器]，或 [!UICONTROL Analytics] > [!UICONTROL 元件] > [!UICONTROL 專案] |
| 我的最愛 | 新增元件至我的最愛清單。接著元件會在相關的元件管理器中顯示，例如「[!UICONTROL Analytics]」 > 「[!UICONTROL 元件]」 > 「[!UICONTROL 篩選器]」，或「[!UICONTROL Analytics]」 > 「[!UICONTROL 元件]」 > 「[!UICONTROL 專案]」。 |
| 核准 | 核准元件使其成為正式項目。接著元件會在相關的元件管理器中顯示，例如「[!UICONTROL Analytics]」 > 「[!UICONTROL 元件]」 > 「[!UICONTROL 篩選器]」，或 「[!UICONTROL Analytics]」 > 「[!UICONTROL 元件]」 > 「[!UICONTROL 專案]」 |
| 共用 | 僅適用於篩選器。 |
| 刪除 | 僅適用於篩選器。 |

觀看建立量度、篩選器和日期的說明影片：

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## 管理元件 {#actions}

您可以直接在左側邊欄中管理元件。

1. 以滑鼠右鍵按一下元件。

   或

   選取元件，然後選取 **動作** (3-dot)圖示。

   >[!TIP]
   >
   >   按住Shift鍵或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）可以選取多個元件。


   ![](assets/component-actions.png)

   | 元件動作 | 說明 |
   |--- |--- |
   | [!UICONTROL **標記**] | 以套用標記的方式組織或管理元件。然後，您可以按一下篩選或輸入 #，依左側欄中的標籤進行搜尋。標籤也會當作元件管理員中的篩選器。 |
   | [!UICONTROL **我的最愛**] | 新增元件至我的最愛清單。如同標籤，您可以依左側邊欄的「我的最愛」搜尋，並在元件管理員中這些條件篩選。 |
   | [!UICONTROL **核准**] | 將元件標示為「已核准」，向您的用戶表示此元件已獲得組織核准。如同標籤，您可以依左側邊欄的「已核准」搜尋，並在元件管理員中這些條件篩選。 |
   | [!UICONTROL **共用**] | 缃元件提供給組織中的用戶共用。此選項僅適用於自訂元件，例如篩選器或計算量度。 |
   | [!UICONTROL **刪除**] | 刪除您不再需要的元件。 此選項僅適用於自訂元件，例如篩選器或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。例如， [管理篩選器](/help/components/filters/manage-filters.md).

## 搜尋、篩選及排序元件清單

您可以在Analysis Workspace左側邊欄中搜尋、篩選及排序元件清單，以快速找到特定元件。

### 搜尋元件清單

1. 選取 **元件** 圖示 ![元件圖示](assets/components-icon.png) 在左側邊欄。

1. 在搜尋欄位中，開始輸入您要在專案中使用的元件名稱。

   元件類型可透過顏色和圖示來識別。 **Dimension** ![Dimension圖示](assets/dimension-icon.png) 是橙色的， **篩選器** ![篩選圖示](assets/segment-icon.png) 是藍色的， **日期範圍** ![日期範圍圖示](assets/date-range-icon.png) 是紫色的， **量度** ![量度圖示](assets/default-metric-icon.png) 為綠色。 Adobe圖示 ![Adobe圖示](assets/default-calc-metric-icon.png) 指出計算量度範本或篩選範本，以及計算器圖示 ![計算器表徵圖](assets/calculated-metric-icon-created.png) 指出貴組織中的Analytics管理員所建立的計算量度。

1. 當元件出現在下拉式清單中時，請選取該元件。

### 篩選元件清單

1. 選取 **元件** 圖示 ![元件圖示](assets/components-icon.png) 在左側邊欄。

1. 選取 **篩選** 圖示 ![資料字典篩選器圖示](assets/components-filter-icon.png).

   或

   在搜尋欄位中輸入井字型大小(#)。

1. 選取下列任一篩選選項，以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
   | [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件添加到收藏夾清單的資訊，請參閱 [管理元件](#manage-components). |
   | [!UICONTROL **維度**] | 僅顯示維度的元件。 |
   | [!UICONTROL **量度**] | 僅顯示量度的元件。 |
   | [!UICONTROL **篩選條件**] | 僅顯示屬於「篩選」的元件。 |
   | [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。 |
   | [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |

1. （選用）若要進一步磨練清單，您可以依照 [排序元件清單](#sort-the-component-list).

### 排序元件清單

1. （選用）將任何篩選器套用至元件清單，如 [篩選元件清單](#filter-the-component-list).

1. 選取 **元件** 圖示 ![元件圖示](assets/components-icon.png) 在左側邊欄。

1. 選取 **排序** 圖示 ![「排序元件」圖示](assets/component-sort-icon.png)，然後選取下列任一篩選選項，以排序元件清單：

   {{components-sort-options}}

## 元件存取權限

在 Analysis Workspace 中，管理員可以[管理](/help/analysis-workspace/curate-share/curate.md)在報表中向使用者公開的元件。
