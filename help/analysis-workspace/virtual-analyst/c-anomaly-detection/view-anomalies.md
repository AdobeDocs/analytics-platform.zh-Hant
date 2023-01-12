---
description: 您可以在表格或線性圖中檢視異常。
title: 在 Analysis Workspace 中檢視異常
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---

# 在 Analysis Workspace 中檢視異常

您可以在表格或線性圖中檢視異常。

## 在表格中檢視異常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在時間序列自由表格中檢視異常。

1. 在欄標題中選取欄設定圖示，然後確定 [!UICONTROL **異常**] 選項。 如需詳細資訊，請參閱 [欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. 按一下離開設定功能表以檢視更新的表格。

   ![](assets/anomaly_detected.png)

1. 異常在表格中顯示如下：

   A **暗灰色三角形** 會顯示在偵測到資料異常的每一列的右上角。

   顏色 **垂直線** 在每一列中都表示預期值。 顏色 **著色區域** 在每一列中都表示實際值。 線條（預期值）與著色區域（實際值）的比較方式會決定是否有異常。 (根據以下所述的進階統計技術，觀察被視為異常 [異常偵測所使用的統計技術](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

1. 選取列右上角的灰色三角形，以檢視異常的詳細資訊。 這會顯示實際值偏移至高於或低於預期值的範圍（百分比）。

## 在線性圖中檢視異常 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折線圖是唯一可讓您檢視異常的視覺效果。

若要在折線圖中檢視異常：

1. 選取視覺效果標題中的設定圖示，然後確定 [!UICONTROL **顯示異常**] 選項。 如需詳細資訊，請參閱 [折線圖](/help/analysis-workspace/visualizations/line.md).

1. （選用）若要允許信賴區間縮放圖表，請選取視覺效果標題中的設定圖示，然後選取選項， **[!UICONTROL 允許異常縮放Y軸]**.

   預設不會選取此選項，因為有時會讓圖表較不清晰。

1. 按一下離開設定功能表以檢視更新的折線圖。

   ![](assets/anomaly_linechart.png)

   異常在折線圖中顯示如下：

   A **白點** 會顯示在偵測到資料異常的位置。 (根據以下所述的進階統計技術，觀察被視為異常 [異常偵測所使用的統計技術](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

   此 **淡色區域** 是信賴範圍或預期範圍，值應發生的位置。 任何超出此預期範圍的值都是異常。

   如果折線圖中有多個量度，系統只會顯示異常，且您必須將滑鼠移至每個異常上，才能查看該量度的信賴帶。

   此 **虛線** 是確切的預期值。

1. 按一下異常（白點）可檢視下列資訊：

   * 異常發生的日期

   * 異常情形的原始值

   * 高於或低於期望值的百分比，期望值會加上綠色實線。

