---
title: 在Analysis Workspace中設定矩陣視覺效果
description: 瞭解如何在Customer Journey Analytics Analysis Workspace中設定矩陣視覺效果，包括其元件、顯示選項和設定。
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# 設定矩陣視覺效果

矩陣視覺效果是值的網格，顯示來自兩個維度的維度專案如何重疊或相互關聯。 每個儲存格會顯示列的維度專案與欄的維度專案的交集。

![矩陣視覺效果](assets/matrix-overview.png)

## 矩陣概述

請參閱[矩陣概述](/help/analysis-workspace/visualizations/matrix/matrix.md)，以進一步瞭解矩陣視覺效果，包括：

* 主要功能

* 潛在的洞察

* 矩陣、自由表格、文氏圖表和散佈圖視覺效果之間的差異

## 建立矩陣視覺效果

1. 新增空白面板至您的專案，選取左側邊欄中的&#x200B;[!UICONTROL **視覺效果**]&#x200B;圖示，然後將&#x200B;[!UICONTROL **矩陣**]&#x200B;視覺效果拖曳至面板。<!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   或

   以[視覺效果概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)的[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)區段中所述的任何方式新增矩陣視覺效果。

   <!-- add screenshot of the Matrix configuration fields -->

1. 指定下列資訊以設定矩陣視覺效果：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **列維度**] | 其專案在矩陣中顯示為列的維度。 |
   | [!UICONTROL **資料行維度**] | 其專案在矩陣中顯示為欄的維度。 <p>如果您為列維度和欄維度選取相同的維度，矩陣視覺效果會將維度專案相互比較。 例如，如果兩個維度都是&#x200B;_裝置型別_，則每個儲存格會顯示兩個裝置型別之間的重疊或相互關聯，例如&#x200B;_行動電話_&#x200B;和&#x200B;_平板電腦_。 對角線上方和下方的值會彼此映象。</p> |
   | [!UICONTROL **量度**] | 每個儲存格為其列維度專案和欄維度專案的組合顯示的量度。 |
   | [!UICONTROL **容器**] | 此容器可決定列維度專案與欄維度專案之間的重疊範圍。 (如果您的容器名稱與下方顯示的預設名稱不同，則這些是在您的資料釋圖中自訂的名稱。)<ul><li>**人員：** （預設）列維度專案和欄維度專案在同一個人員發生時，會在任何工作階段數中重疊。</li><li>**工作階段：**&#x200B;列維度專案與欄維度專案在相同工作階段中發生時重疊。</li><li>**事件：**&#x200B;列維度專案與欄維度專案在同一事件中發生時重疊。</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. （選用）變更下列任一設定：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **列限制**] | 矩陣視覺效果顯示的最大列數。 預設值為10。<!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **重疊調色盤**] | 矩陣顯示[重疊計數](#view-overlap-count-or-correlation-strength)時儲存格的色階。 |
   | [!UICONTROL **相互關聯調色盤**] | 當矩陣顯示[關聯強度](#view-overlap-count-or-correlation-strength)時，儲存格的色階。 負關聯和正關聯使用不同的顏色。 |
   | [!UICONTROL **相互關聯粒度**] | 用於計算[相互關聯強度](#view-overlap-count-or-correlation-strength)的時間粒度，例如&#x200B;**[!UICONTROL 天]**。 此值是根據面板日期範圍自動設定。 您無法加以變更。 <p>您會根據面板日期範圍選擇下列粒度：</p><ul><li>[!UICONTROL **小時**]：已針對7天或更短的日期範圍選擇</li><li>[!UICONTROL **天**]：針對超過7天（最長3個月）的日期範圍而選擇</li><li>[!UICONTROL **周**]：針對超過3個月的日期範圍而選擇，最多1年</li><li>[!UICONTROL **月**]：針對超過1年的日期範圍而選擇</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **對角儲存格值**] | 矩陣視覺效果如何顯示維度專案與其自身相遇的儲存格。 此設定僅在列維度和欄維度相同時可用。<ul><li>**[!UICONTROL 顯示]：**&#x200B;顯示值。</li><li>**[!UICONTROL 虛線]：**&#x200B;顯示虛線而非值。</li><li>**[!UICONTROL 空白]：**&#x200B;將儲存格保留空白。</li></ul> |

1. 選取「[!UICONTROL **建置**]」。

   <!-- add screenshot -->

1. 繼續下列區段，[檢視重疊計數或相互關聯強度](#view-overlap-count-or-correlation-strength)。

## 檢視重疊計數或關聯強度

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="重疊計數與關聯強度"
>abstract="<p>**重疊計數**&#x200B;是列維度專案與欄維度專案重疊的所選量度的值。</p><p>**相互關聯強度**&#x200B;是從–1到+1的線性相互關聯，說明兩個維度專案的量度在一段時間內的移動程度。 值為+1表示它們一起上升和下降，0表示沒有關係，而–1表示它們向相反方向移動。 關聯強度與重疊分開計算，因此重疊較少的維度專案仍可具有強大的關聯。</p>"

<!-- markdownlint-enable MD034 -->

您可以切換矩陣視覺效果以顯示重疊計數或關聯強度。 預設會顯示重疊計數。

1. 在Analysis Workspace中，開啟「矩陣」視覺效果或[建立新的](#build-a-matrix-visualization)。

1. 在矩陣視覺效果的左上角，從下列選項中選取：

   * [!UICONTROL **重疊計數**]：顯示每個資料列維度專案與每個資料行維度專案的重疊程度。 每個儲存格會顯示兩個維度專案發生之人員、工作階段或事件的所選量度值（視容器而定）。

   * [!UICONTROL **相互關聯強度**]：顯示每個列維度專案與每個欄維度專案在面板日期範圍內一起移動的緊密程度，呈現從–1到+1的線性相互關聯。 值為+1表示兩個維度專案總是一起上升和下降，0表示沒有關係，而–1表示它們總是以相反的方向移動。 關聯強度與重疊分開計算，因此重疊較少的維度專案仍可具有強大的關聯。 以&#x200B;[!UICONTROL **相互關聯粒度**]&#x200B;設定中所顯示的時間粒度來計算相互關聯。<!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   「矩陣」視覺效果右上角的圖例會顯示目前檢視的色階：低到高表示重疊計數，或負(-1)到正(+1)表示關聯強度。

## 檢視深入分析

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

矩陣視覺效果底部的insight卡片會說明矩陣資料中的顯著模式。

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

若要檢視深入分析：

1. 在矩陣視覺效果中，檢視視覺效果底部的insight卡。

1. 使用insight卡上的箭頭，逐頁瀏覽可用的深入分析。

## 編輯矩陣設定

建置矩陣視覺效果後，您可以變更其設定，例如維度、量度或容器。

若要編輯矩陣設定：

1. 在矩陣視覺效果中，選取視覺效果頂端子標題旁的![編輯](/help/assets/icons/Edit.svg)。 副標題會摘要目前設定，例如量度和維度。

1. 變更[建置矩陣視覺效果](#build-a-matrix-visualization)中說明的任何設定。

1. 選取「[!UICONTROL **建置**]」。

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## 檢視趨勢資料

您可以在[線條視覺效果](/help/analysis-workspace/visualizations/line.md)中檢視儲存格的趨勢資料。 折線圖視覺效果會顯示所選量度在面板日期範圍內的變化。 顯示的行視矩陣是否顯示[重疊計數或關聯強度](#view-overlap-count-or-correlation-strength)而定。

若要檢視趨勢資料：

1. 在矩陣視覺效果中，以滑鼠右鍵按一下您要檢視趨勢資料的儲存格。

1. 選取「[!UICONTROL **趨勢**]」。

   在面板中，在矩陣視覺效果的上方新增線條視覺效果：

   * [!UICONTROL **重疊計數**]：單行顯示選取的量度，此量度是同時依列維度專案和欄維度專案篩選。

   * [!UICONTROL **關聯強度**]：兩行顯示選取的量度，一行用於列維度專案，另一行用於欄維度專案。 比較這兩條線以瞭解兩個維度專案的趨勢結合程度。

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## 在「文氏圖」視覺效果中檢視重疊

您可以在[Venn視覺效果](/help/analysis-workspace/visualizations/venn.md)中檢視儲存格的列維度專案與欄維度專案之間的重疊。

如需關於何時使用矩陣視覺效果或文氏圖表視覺效果的詳細資訊，請參閱[矩陣概觀](/help/analysis-workspace/visualizations/matrix/matrix.md)中的[選擇矩陣、自由表格、文氏圖表或散佈圖視覺效果](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations)。

若要在「文氏圖」視覺效果中檢視重疊：

1. 在矩陣視覺效果中，用滑鼠右鍵按一下要檢視重疊的儲存格。

1. Select [!UICONTROL **以Venn**]&#x200B;顯示。

   「文氏圖」視覺效果會新增至面板。 一個圓代表列尺寸專案，另一個圓代表欄尺寸專案。 文氏圖表視覺效果使用與矩陣視覺效果相同的量度。<!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## 套用劃分

您可以依其他維度劃分儲存格的資料，以檢視哪些維度專案對儲存格值有貢獻。

若要套用劃分，請執行下列動作：

1. 在矩陣視覺效果中，以滑鼠右鍵按一下您要套用劃分的儲存格。

1. 選取「[!UICONTROL **劃分**]」。

1. 選取要用於劃分的維度。

   劃分維度的排名最前維度專案會顯示在新的自由表格中。<!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


