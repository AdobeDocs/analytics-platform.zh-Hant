---
description: 使用「摘要數字」和「摘要變更」視覺效果來呈現專案中的重要資料點。
title: 摘要數字和摘要變更
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 61c1fe48ebe8ebff5b7104cebae1ce7b62289b7d
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 94%

---

# 摘要數字和摘要變更

## 摘要數字視覺效果 {#summary-number}

使用「摘要數字」視覺效果來強調專案中重要的大數字。此視覺效果的運作方式如下：

* 如果未選取儲存格，則會選取該欄的總計。
* 如果選取單一儲存格，則會顯示該儲存格的摘要。
* 如果選取多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會挑選欄中第一個儲存格的值。

按一下右上角的&#x200B;**「視覺效果設定」**&#x200B;齒輪，設定「摘要數字」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 顯示百分比而非原始數據。 |
| 可見圖例 | 顯示所顯示量度的相關資訊。 |
| 縮簡值 | 選擇以縮簡值，顯示最多小數點後 3 位。 |
| 值摘要依據: | 選擇以顯示一系列資料的最大值、最小值、平均值、中間值或總計。 |

{style="table-layout:auto"}

## 摘要變更視覺效果 {#summary-change}

使用摘要變更視覺效果可顯示兩個數字間的差異（變更）。

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

此視覺效果的運作方式如下：

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。


![摘要變更視覺效果顯示兩個數字間的差異。s](assets/summary-change.png)


按一下右上角的&#x200B;**「視覺效果設定」**&#x200B;齒輪，設定「摘要變更」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 顯示百分比而非原始數據。 |
| 可見圖例 | 顯示所顯示量度的相關資訊。 |
| 顯示百分比變化 | 顯示 2 個數字之間的百分比變化。 |
| 顯示原始資料差異 | 顯示 2 個數字之間的原始差異。您也可以縮簡值，使用此選項顯示最多小數點後 3 位。 |
