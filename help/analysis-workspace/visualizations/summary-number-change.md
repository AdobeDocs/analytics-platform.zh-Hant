---
description: 使用「摘要編號」和「變更」視覺化來顯示專案中的重要資料點。
title: 摘要數字和摘要變更
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 9733d6471e6f1c886fd27b702654349d6760870c
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 56%

---


# 摘要數字和摘要變更

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

## 摘要數字視覺效果 {#summary-number}

使用「摘要數字」視覺化來反白顯示專案中重要的大數字。 此視覺化的運作方式如下：

* 如果未選取儲存格，則會選取該欄的總計。
* 如果選取單一儲存格，則會顯示該儲存格的摘要。
* 如果選取多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會挑選欄中第一個儲存格的值。

![摘要數字](assets/summary-number.png)

按一下 **視覺化設定** 以右上角的格式設定「摘要編號」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 顯示百分比而非原始數字。 |
| 可見圖例 | 顯示所顯示量度的相關資訊。 |
| 縮簡值 | 選擇縮寫值，最多顯示3個小數位。 |
| 值摘要依據: | 選擇顯示所選資料的最大、最小值、平均值、中值或和。 |

## 摘要變更視覺效果 {#summary-change}

使用「摘要變更」視覺化顯示兩個數字之間的增量（變更）。 「摘要變更」的綠色和紅色可透過 [自訂事件極性](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/success-events/success-event.html) 或計算量度的 [將上升趨勢顯示為](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) 的雙曲餘切值。

此視覺化的運作方式如下：

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。

![摘要變更](assets/summary-change.png)

按一下 **視覺化設定** 以右上角的齒輪來配置「摘要更改」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 顯示百分比而非原始數字。 |
| 可見圖例 | 顯示所顯示量度的相關資訊。 |
| 顯示百分比變更 | 顯示2個數字之間的百分比變化。 |
| 顯示原始差異 | 顯示 2 個數字之間的原始差異。您也可以縮寫值，並使用此選項顯示最多3個小數位。 |
