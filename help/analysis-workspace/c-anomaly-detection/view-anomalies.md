---
description: 瞭解如何在Analysis Workspace中根據內容檢視和分析資料異常。
title: 異常偵測概觀
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
role: User
source-git-commit: 808b09d79d3c686747f7b19b6646001e3345b9aa
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 50%

---


# 檢視異常

您可以在Analysis Workspace的表格或折線圖中檢視異常。

## 在表格中檢視異常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在時間序列自由表格中檢視異常。

1. 在欄標題中選取![設定](/help/assets/icons/Setting.svg)，然後確定已在選項清單中選取&#x200B;**[!UICONTROL 顯示異常]**&#x200B;選項。 如需詳細資訊，請參閱[欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 異常情況在表格中顯示如下：

   ![偵測到異常](assets/anomaly-detected.png)

   偵測到資料異常的每一列右上角都會顯示◥。

   每一列&#x200B;**中的**&#x200B;彩色垂直線➋表示預期的值。 每一列&#x200B;**中的**&#x200B;彩色陰影區域➊表示實際值。 線條 (預期值) 與陰影區域 (實際值) 的比較方式會決定是否有異常。 （根據[異常偵測所使用的統計技術](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中所述的進階統計技術，將觀察視為異常。）

1. 選取資料列右上角的◥以檢視有關異常的詳細資訊。 這會顯示實際值高於或低於預期值的偏離程度 (以百分比表示)。

## 在線性圖中檢視異常

折線圖是唯一可讓您檢視異常的視覺效果。

若要在折線圖中檢視異常：

1. 在視覺效果標題中選取![設定](/help/assets/icons/Setting.svg)，然後確定已在選項清單中選取&#x200B;[!UICONTROL **顯示異常**]&#x200B;選項。 如需詳細資訊，請參閱[折線圖](/help/analysis-workspace/visualizations/line.md)。

1. （選擇性）若要允許信賴區間縮放圖表，請選取視覺效果標題中的![設定](/help/assets/icons/Setting.svg)，然後選取&#x200B;**[!UICONTROL 允許異常縮放Y軸]**&#x200B;選項。

   預設為不選取此選項，因為有時會讓圖表較不清晰。

   異常情況在折線圖中顯示如下：

   ![偵測到異常的線條視覺效果](assets/anomaly-detected-line.png)

   **白點**&#x200B;會顯示在偵測到資料異常的位置。（根據[異常偵測所使用的統計技術](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中所述的進階統計技術，將觀察視為異常。）

   此&#x200B;**淺色陰影區域**&#x200B;是信賴範圍或預期範圍，值應發生的位置。任何超出此預期範圍的值都是異常。

   如果折線圖中有多個量度，系統只會顯示異常值，您必須將滑鼠移到每個異常值上方，才能查看該量度的信賴帶。

   此&#x200B;**虛線**&#x200B;是確切的預期值。

1. 選取異常（白點）以檢視下列資訊：

   * 異常發生的日期。

   * 異常的原始值。

   * 高於或低於期望值的百分比，期望值會加上綠色實線。








<!--
# View anomalies in Analysis Workspace

You can view anomalies in a table or in a line chart.

## View anomalies in a table {#table}

You can view anomalies in a time-series Freeform Table.

1. Select the column settings icon in the column header, then ensure that the [!UICONTROL **Anomalies**] option is selected in the list of options. For more information, see [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Click away from the settings menu to view the updated table.

   ![An anomaly detection notification indicating 15% below expected.](assets/anomaly_detected.png)

1. Anomalies are shown in the table as follows:

   A **dark gray triangle** appears in the upper-right corner of each row where a data anomaly is detected.

   The colored **vertical line** in each row indicates the expected value. The colored **shaded area** in each row indicates the actual value. How the line (expected value) compares with the shaded area (actual value) determines whether there is an anomaly. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Select the gray triangle in the upper-right corner of a row to view details about the anomaly. This shows the extent (as a percentage) to which the actual value diverges either above or below the expected value.

## View anomalies in a line chart {#line-chart}

A Line chart is the only visualization that allows you to view anomalies.

To view anomalies in a line chart:

1. Select the settings icon in the visualization header, then ensure that the [!UICONTROL **Show anomalies**] option is selected in the list of options. For more information, see [Line](/help/analysis-workspace/visualizations/line.md).

1. (Optional) To allow the confidence interval to scale the chart, select the settings icon in the visualization header, then select the option, **[!UICONTROL Allow anomalies to Scale Y-axis]**. 

   This option is not selected by default because it can sometimes make the chart less legible.
   
1. Click away from the settings menu to view the updated line chart.

      ![A line chart with an anomaly detected message indicating 15% above expected.](assets/anomaly_linechart.png)

   Anomalies are shown in the line chart as follows:
   
   A **white dot** appears on the line wherever a data anomaly is detected. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   The **light shaded area** is the confidence band, or expected range, where values should occur. Any value that falls outside of this expected range is an anomaly. 

   If you have multiple metrics in the line chart, only the anomalies are shown and you have to hover over each anomaly to see the confidence band for that metric. 

   The **dotted line** is the exact expected value.

1. Click an anomaly (white dot) to view the following information:

   * The date the anomaly occurred 
   
   * The raw value of the anomaly 
   
   * The percentage value above or below the expected value, which is represented by the solid green line.
   
-->
