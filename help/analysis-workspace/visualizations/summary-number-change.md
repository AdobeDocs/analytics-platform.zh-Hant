---
description: 使用「摘要數字」和「摘要變更」視覺效果來呈現專案中的重要資料點。
title: 摘要數字和摘要變更
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 9733d6471e6f1c886fd27b702654349d6760870c
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 100%

---


# 摘要數字和摘要變更

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

## 摘要數字視覺效果 {#summary-number}

使用「摘要數字」視覺效果來強調專案中重要的大數字。此視覺效果的運作方式如下：

* 如果未選取儲存格，則會選取該欄的總計。
* 如果選取單一儲存格，則會顯示該儲存格的摘要。
* 如果選取多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會挑選欄中第一個儲存格的值。

![摘要數字](assets/summary-number.png)

按一下右上角的&#x200B;**「視覺效果設定」**&#x200B;齒輪，設定「摘要數字」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 顯示百分比而非原始數據。 |
| 可見圖例 | 顯示所顯示量度的相關資訊。 |
| 縮簡值 | 選擇以縮簡值，顯示最多小數點後 3 位。 |
| 值摘要依據: | 選擇以顯示一系列資料的最大值、最小值、平均值、中間值或總計。 |

## 摘要變更視覺效果 {#summary-change}

使用「摘要變更」視覺效果以顯示兩個數字間的差異 (變更)。可透過[自訂事件極性](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/success-events/success-event.html)，或計算量度的[「顯示上升趨勢的方式」](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)選項，控制「摘要變更」的綠色和紅色。

此視覺效果的運作方式如下：

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。

![摘要變更](assets/summary-change.png)

按一下右上角的&#x200B;**「視覺效果設定」**&#x200B;齒輪，設定「摘要變更」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 顯示百分比而非原始數據。 |
| 可見圖例 | 顯示所顯示量度的相關資訊。 |
| 顯示百分比變化 | 顯示 2 個數字之間的百分比變化。 |
| 顯示原始資料差異 | 顯示 2 個數字之間的原始差異。您也可以縮簡值，使用此選項顯示最多小數點後 3 位。 |
