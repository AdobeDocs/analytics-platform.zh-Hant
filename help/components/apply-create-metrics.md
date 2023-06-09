---
description: 在 Analysis Workspace 中使用量度有兩種方式。
title: 量度
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: a9751cad1ba49fe3e8c2c484e34d1725e063c2d4
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 23%

---

# 量度

量度可讓您量化Analysis Workspace中的資料點。 它們最常用作視覺效果中的欄，並與維度繫結。


## 量度型別

Adobe提供數種用於Analysis Workspace的量度型別：

* **標準量度**：標準量度的範例為「人員」、「工作階段」、「事件」。

* **計算量度** ![計算量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)：根據標準量度、靜態數字或演演算法函式的使用者定義量度。

* **計算量度範本**  <img src="./assets/adobe-logo.svg" width="18"> ：Adobe定義的量度，其行為與計算量度類似。 您可以在Workspace專案中照原樣使用它們，或儲存副本以自訂其邏輯。


![UI中的量度](assets/cja-metrics.png)

您可以檢視量度是否已核准 ![「已核准」圖示](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  或不能。 如果您想要瞭解量度的詳細資訊，請將滑鼠指標暫留，然後選取「 」 ![資訊圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


量度在Analysis Workspace中的使用方式具有彈性。 將量度拖曳至空白的自由格式表格，以檢視專案日期期間的量度趨勢。 您也可以拖曳出現維度時的量度，以檢視該量度與每個維度專案的比較。 將量度拖曳至現有量度標頭上方會取代量度，拖曳至標頭旁的量度可讓您並排看到兩個量度。

## 計算量度

計算量度可讓您使用簡單的運運算元或統計函式，輕鬆檢視量度彼此之間的關係。 建立計算量度有數種方式：

您可以選取 **[!UICONTROL 元件]** > **[!UICONTROL 計算量度]**. 這會將您導向 [計算量度產生器](/help/components/calc-metrics/calc-metr-overview.md)，即可從現有量度建立自訂量度。

為了更方便快速建立計算量度，已將&#x200B;**[!UICONTROL 「從選取範圍建立量度」]**&#x200B;新增至自由表格中的欄滑鼠右鍵選單。只要選取一個或多個標頭欄儲存格，就可以看到這個選項。

![從選取專案建立](assets/create-metric-from-selection.png)

[計算量度：實作較少的量度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hant) (3:42)

## 比較不同歸因模型的量度

如果您想要輕鬆快速地比較不同的歸因模型，請用滑鼠右鍵按一下量度並選取「 」 **[!UICONTROL 比較歸因模型]**：

![比較歸因](assets/compare-attribution.png)

此快速鍵可讓您輕鬆快速地比較不同的歸因模型，而無須再次拖曳量度和進行設定。
