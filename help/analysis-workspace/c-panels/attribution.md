---
title: 歸因面板
description: 如何使用和解讀 Analysis Workspace 中的歸因面板。
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 84%

---


# 歸因面板

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

您可以使用歸因面板輕鬆建立比較不同歸因模型的分析。這是[歸因 IQ](../attribution/overview.md) 中的一項功能，可讓您在專屬的工作區中使用和比較歸因模型。

## 建立歸因面板

1. 按一下左側的面板圖示。
1. 將歸因面版拖曳到您的 Analysis Workspace 專案中。

   ![新增歸因面板](assets/Attribution_Panel_1.png)

1. 新增要歸因的量度，並新增任何作為歸因依據的維度。其範例包括行銷管道或自訂維度，例如內部促銷。

   ![選取維度和量度](assets/attribution_panel2.png)

1. 選取要比較的[歸因模型和回顧期間](../attribution/models.md)。

1. 「歸因」面板會傳回一組豐富的資料和視覺效果，用以比較所選維度和量度的歸因。

   ![歸因視覺效果](assets/attr_panel_vizs.png)

## 歸因視覺效果

* **量度總計**：在報告時間範圍內發生的轉換總數。這些是在您所選取的維度中歸因的轉換。
* **量度歸因比較長條圖**：以視覺化方式比較您所選維度中個別維度項目的歸因轉換數。每個長條的顏色代表不同的歸因模型。
* **量度歸因自由表格**：顯示與長條圖相同的資料，但以表格顯示。在此表格中選取不同的欄或列可篩選長條圖，以及面板中的其他數個視覺效果。此表格的運作方式類似於工作區中的任何其他自由表格——可讓您新增量度、區段或劃分等元件。
* **維重疊圖**:「文氏圖」顯示前三維項目，以及它們共同參與轉換的頻率。 例如，泡泡重疊的大小表示當訪客同時接觸兩個維度項目時發生轉換的頻率。 選取相鄰自由表格中的其他列，可依據您的選取項目更新視覺效果。
* **每個歷程的行銷接觸點**：一個色階分佈圖，指出訪客在回顧期間內的接觸點數目。此圖表在查看多點接觸歸因影響資料集情形時相當實用。如果幾乎所有訪客都只有單一接觸點，不同的歸因模型很可能會顯示類似的資料。
* **行銷管道效能詳細資料**：可讓您使用散佈圖以視覺化方式比較最多三個歸因模型。
* **行銷管道流程**：可讓您查看互動最頻繁的管道，及其在訪客歷程中的順序。
