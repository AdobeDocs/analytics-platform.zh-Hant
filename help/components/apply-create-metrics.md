---
description: 在 Analysis Workspace 中使用量度有兩種方式。
title: 量度
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 20%

---

# 量度

量度可讓您量化 Analysis Workspace 中的資料點。它們最常用作視覺效果中的欄，並和維度相連結。

## 量度類型

Adobe 提供了多種可用於 Analysis Workspace 中的量度類型：


* **標準量度**：標準量度的範例為人員、工作階段、事件。

* **計算量度** ![電腦](/help/assets/icons/Calculator.svg)：以標準量度、靜態數字或演演算法函式為基礎的使用者定義量度。

* **計算量度範本** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ：與計算量度行為類似的Adobe定義量度。 您可以在Workspace專案中照原樣使用，或儲存復本來自訂邏輯。

您可以檢視量度是否核准![核准圖示](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)。 如果您想要瞭解量度的詳細資訊，請將滑鼠移至量度上，然後選取![資訊圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)。 如需詳細資訊，請參閱[元件資訊](use-components-in-workspace.md#component-info)。



## 在 Analysis Workspace 中使用量度

量度在Analysis Workspace中的使用有彈性。 將量度拖曳至空白的自由格式表格，以檢視專案日期期間的量度趨勢。 您也可以拖曳出現維度時的量度，以檢視與每個維度專案比較的量度。 將量度拖曳至現有量度標頭上方會取代量度，並將量度拖曳至標頭旁，可讓您並排看到兩個量度。

如需有關如何將量度和其他型別的元件新增到Analysis Workspace的資訊，請參閱[在Analysis Workspace中使用元件](/help/components/use-components-in-workspace.md)。

## 計算量度

計算量度可讓您使用簡單的運運算元或統計函式，輕鬆設定量度彼此之間的關係。 如需詳細資訊，請參閱[計算量度概觀](/help/components/calc-metrics/calc-metr-overview.md)。

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

+++

-->

## 比較不同歸因模型的量度

如果您想要輕鬆快速地比較量度的一個歸因模型與另一個歸因模型，請從量度的內容功能表中選取&#x200B;**[!UICONTROL 比較歸因模型]**。

![Workspace面板醒目提示比較歸因模型](assets/compare-attribution.png)

此快速鍵可讓您快速輕鬆比較歸因模型。
