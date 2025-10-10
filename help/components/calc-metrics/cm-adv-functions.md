---
title: 進階函數
description: 了解進階計算量度函數。
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '5241'
ht-degree: 100%

---

# 進階函數

使用[計算量度產生器](cm-workflow/cm-build-metrics.md)可套用統計和數學函數。本文記錄進階函數及其定義的清單，依字母順序排列。

透過選取元件面板中![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 函數]**&#x200B;清單下的「**[!UICONTROL 全部顯示]**」，以存取這些函數。向下捲動以查看&#x200B;**[!UICONTROL 進階函數]**&#x200B;清單。

## 表格函數和列函數的比較

表格函數是表格每一列的輸出都相同。列函數則是表格每一列的輸出都不同。

在適用且相關的情況下，函數會以函數類型進行註解：[!BADGE 表格]{type="Neutral"}或[!BADGE 列]{type="Neutral"}

## include_zeros 參數的意義是什麼? 

此參數指出是否在計算中包括零。有時候零&#x200B;*沒有意義*，有時候卻很重要。

例如，如果您有「收入」量度，隨後新增「頁面檢視」量度至報表，您的收入會突然出現許多全都是零的列。您可能不希望該附加量度影響任何 **[平均值](cm-functions.md#mean)**、**[列最小值](cm-functions.md#row-min)**、**[四分位數](cm-functions.md#quartile)**，以及收入欄中的更多計算。在這種情況下，您可以勾選 `include-zeros` 參數。

另一種情況是，您有兩個感興趣的量度，其中一個具有較高的平均值或最小值，因為某些列是零。在此情況下，您可以選擇不檢查參數是否包括零。


## 與 {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="與"
>abstract="結合。不等於零為是，等於零為否。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL AND (邏輯測試)]**

結合。不等於零為是，等於零為否。輸出為 0 (否) 或 1 (是)。

| 引數 | 說明 |
|---|---|
| logical_test | 需要至少一個參數，但可以採用任意數量的參數。可評估為 TRUE 或 FALSE 的任何值或運算式 |


## 近似計數相異 {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="近似計數相異"
>abstract="傳回所選取之維度的維度項目近似相異計數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 近似相異計數 (維度)]**


傳回選定維度之維度項目的近似相異計數。


| 引數 | 說明 |
|---|---|
| 維度 | 您希望計算近似相異項目計數的維度 |

### 範例

此函數的常見使用案例為當您想要獲得大致的客戶數量時。



## 反餘弦 {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="反餘弦"
>abstract="傳回量度的反餘弦 (或餘弦的反函數)。反餘弦是一種角度，其餘弦是數字。傳回的角度是限制在 0 (零) 到 pi 的弧度。如果您想將結果從弧度轉換為度數，請將結果乘以 180/PI()。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 反餘弦 (量度)]**


[!BADGE 列]{type="Neutral"}傳回量度的反餘弦 (或餘弦的反函數)。反餘弦是一種角度，其餘弦是數字。傳回的角度是限制在 0 (零) 到 pi 的弧度。如果您想將結果從弧度轉換為度數，請將結果乘以 180/PI()。


| 引數 | 說明 |
|---|---|
| 量度 | 您所要擷取之角度的餘弦，從 -1 到 1 |



## 反正弦 {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="反正弦"
>abstract="傳回數字的反正弦 (或正弦的反函數)。反正弦是一種角度，其正弦是數字。傳回的角度是在 -pi/2 到 pi/2 範圍內的弧度。若想以度數表示反正弦，請將結果乘以 180/PI()。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 反正弦 (量度)]**


[!BADGE 列]{type="Neutral"}傳回數字的反正弦 (或正弦的反函數)。反正弦是一種角度，其正弦是數字。傳回的角度是在 -pi/2 到 pi/2 範圍內的弧度。若想以度表示反正弦，請將結果乘以 180/PI()。


| 引數 | 說明 |
|---|---|
| 量度 | 您所要擷取之角度的正弦，從 -1 到 1。 |



## 反正切 {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="反正切"
>abstract="傳回數字的反正切 (或正切的反函數)。反正切是一種角度，其正切是數字。傳回的角度是在 -pi/2 到 pi/2 範圍內的弧度。若想以度數表示反正切，請將結果乘以 180/PI()。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 反正切 (量度)]**


[!BADGE 列]{type="Neutral"}傳回數字的反正切 (或正切的反函數)。反正切是一種角度，其正切是數字。傳回的角度是在 -pi/2 到 pi/2 範圍內的弧度。若想以度數表示反正切，請將結果乘以 180/PI()。


| 引數 | 說明 |
|---|---|
| 量度 | 您所要擷取之角度的正切，從 -1 到 1。 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="傳回具有 n 個自由度之 Student-t 分布隨機變數的 z 分數小於 col 之機率。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL CDF-T (量度、數字)]**

傳回具有 n 個自由度之 Student-t 分布之隨機變數的 z 分數小於 col 之機率。

| 引數 | 說明 |
|---|---|
| 量度 | 您想要 Student-t 分布的累積分布函數之量度 |
| 數字 | tudent-t 分布的累積分布函數的自由度 |

### 範例

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="傳回常態分布隨機變數的 z 分數小於 col 之機率。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL CDF-Z (量度、數字)]**

傳回常態分布之隨機變數的 z 分數小於 col 之機率。

| 引數 | 說明 |
|---|---|
| 量度 | 您想要標準常態分布的累積分布函數之量度 |

### 範例

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## 上限 {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="上限"
>abstract="傳回不小於給定值的最小整數。例如，若您不希望報告中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 CEILING(Revenue) 將收入無條件進位至最接近的金額，即 $570。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL CEILING (量度)]**

[!BADGE 列]{type="Neutral"}傳回不小於給定值的最小整數。例如，若您不希望報告中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 CEILING(Revenue) 將收入無條件進位至最接近的金額，即 $570。

| 引數 | 說明 |
|---|---|
| 量度 | 您要四捨五入的量度 |


## 信賴度 {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="信賴度"
>abstract="使用 WASKR 方法計算隨時有效的信賴度，如[時間一致中央極限定理和漸進信賴序列](https://arxiv.org/pdf/2103.06476)所述。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 信賴度 (標準化容器、成功量度、控制、顯著性臨界值)]**

使用 WASKR 方法計算隨時有效的信賴度，如[時間一致中央極限定理和漸進信賴序列](https://arxiv.org/pdf/2103.06476)所述。

信賴度指有多少證據顯示指定變體與控制變體相同的機率測度。信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。

| 引數 | 說明 |
| --- | --- |
| 標準化容器 | 執行測試的基礎 (人員、工作階段或事件)。 |
| 成功量度 | 使用者用來比較變體的一個或多個量度。 |
| 控制 | 和實驗中所有其他變體進行比較的變體。輸入控制變體維度項目的名稱。 |
| 顯著性臨界值 | 此函數中的臨界值設定為預設值 95%。 |


## 信賴度 (下界) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lower-individual-confidence-sequence"
>title="信賴度 (下界)"
>abstract="使用 WASKR 方法計算隨時有效的信賴度&#x200B;**下界**，如[時間一致中央極限定理和漸進信賴序列](https://arxiv.org/pdf/2103.06476)所述。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 信賴度 (標準化容器、成功量度、控制、顯著性臨界值)]**

使用 WASKR 方法計算隨時有效的信賴度&#x200B;**下界**，如[時間一致中央極限定理和漸進信賴序列](https://arxiv.org/pdf/2103.06476) 所述。

信賴度指有多少證據顯示指定變體與控制變體相同的機率測度。信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。

| 引數 | 說明 |
| --- | --- |
| 標準化容器 | 執行測試的基礎 (人員、工作階段或事件)。 |
| 成功量度 | 使用者用來比較變體的一個或多個量度。 |
| 控制 | 和實驗中所有其他變體進行比較的變體。輸入控制變體維度項目的名稱。 |
| 顯著性臨界值 | 此函數中的臨界值設定為預設值 95%。 |

## 信賴度 (上界) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-upper-individual-confidence-sequence"
>title="信賴度 (上界)"
>abstract="使用 WASKR 方法計算隨時有效的信賴度&#x200B;**上界**，如[時間一致中央極限定理和漸進信賴序列](https://arxiv.org/pdf/2103.06476)所述。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 信賴度 (標準化容器、成功量度、控制、顯著性臨界值)]**

使用 WASKR 方法計算隨時有效的信賴度&#x200B;**上界**，如[時間一致中央極限定理和漸進信賴序列](https://arxiv.org/pdf/2103.06476) 所述。

信賴度指有多少證據顯示指定變體與控制變體相同的機率測度。信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。

| 引數 | 說明 |
| --- | --- |
| 標準化容器 | 執行測試的基礎 (人員、工作階段或事件)。 |
| 成功量度 | 使用者用來比較變體的一個或多個量度。 |
| 控制 | 和實驗中所有其他變體進行比較的變體。輸入控制變體維度項目的名稱。 |
| 顯著性臨界值 | 此函數中的臨界值設定為預設值 95%。 |


## 餘弦 {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="餘弦"
>abstract="傳回指定角度的餘弦。如果角度以度數表示，請將角度乘以 PI()/180。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 餘弦 (量度)]**

[!BADGE 列]{type="Neutral"}傳回指定角度的餘弦。如果角度以度數表示，請將角度乘以 PI()/180。

| 引數 | 說明 |
|---|---|
| 量度 | 您要擷取餘弦的角度 (以弧度為單位) |


## 立方根 {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="立方根"
>abstract="傳回數字的正立方根。數字的立方根是該數字的值取 1/3 次方。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 立方根 (量度)]**


傳回數字的正立方根。數字的立方根是該數字的值取 1/3 次方。


| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其立方根的量度 |



## 累積 {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="累積"
>abstract="傳回 x 欄最後 n 個元素的總和。若 n > 0，則會加總最後 n 個元素或 x。若 n &lt; 0，則加總前面的元素。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 累積 (數字、量度)]**

傳回 x 欄最後 n 個元素的總和。若 n > 0，則會加總最後 n 個元素或 x。若 n &lt; 0，則加總前面的元素。

| 引數 | 說明 |
| --- | --- |
| 數字 | 傳回總和的最後 N 列。如果 N &lt;= 0 則使用所有先前列。 |
| 量度 | 您想要累積總和的量度。 |

### 範例

| 日期 | 收入 | 累積 (0、收入) | 累積 (2、收入) |
|------|------:|--------------:|--------------:|
| 5 月 | $500 | $500 | $500 |
| 6 月 | $200 | $700 | $700 |
| 7 月 | $400 | $1100 | $600 |


## 累計 (平均值) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="累計 (平均值)"
>abstract="傳回 x 欄最後 n 個元素的平均。若 n > 0，則會加總最後 n 個元素或 x。若 n &lt; 0，則加總前面的元素。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 累積平均值 (數字、量度)]**

傳回 x 欄最後 n 個元素的平均。若 n > 0，則會加總最後 n 個元素或 x。若 n &lt; 0，則加總前面的元素。

| 引數 | 說明 |
| --- | --- |
| 數字 | 傳回平均的最後 N 列。如果 N &lt;= 0 則使用所有先前列。 |
| 量度 | 您想要累積平均的量度。 |

>[!NOTE]
>
>此函數不適用於每人收入等比率量度。此函數對比率進行平均，而不是對過去 N 個的收入進行加總，並對過去 N 個人數進行加總然後除以它們。<br/>反之，使用[**[!UICONTROL 累積 (收入)]**](#cumulative)![除以](/help/assets/icons/Divide.svg)[**[!UICONTROL 累積 (人數)]**](#cumulative)。
>


## 等於 {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="等於"
>abstract="等於。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL EQUAL ()]**

等於。輸出為 0 (否) 或 1 (是)。


| 引數 | 說明 |
|---|---|
| metric_X | 您想要用於比較的量度。 |
| metric_Y | 您想要用於比較的依據量度。 |

### 範例

`Metric 1 = Metric 2`


## 指數迴歸：相關係數 {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="指數迴歸：相關係數"
>abstract="指數迴歸：Y = a exp(X) + b。傳回相關係數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 指數迴歸：相關係數 (metric_X、metric_Y、include_zeros)]**


[!BADGE 表格]{type="Neutral"}指數迴歸：Y = a exp(X) + b。傳回相關係數。


| 引數 | 說明 |
|---|---|
| metric_X | 您想與 metric_Y 建立關聯的量度 |
| metric_Y | 您想與 metric_X 建立關聯的量度 |
| include_zeros | 計算中是否包括零值 |

## 指數迴歸：預計 Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="指數迴歸：預計 Y"
>abstract="指數迴歸：Y = a exp(X) + b。傳回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 指數迴歸：預測 Y (metric_X、metric_Y、include_zeros)]**


[!BADGE 列]{type="Neutral"}指數迴歸：Y = a exp(X) + b。傳回 Y。


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為獨立資料的量度。 |
| metric_Y | 您要指定為相依資料的量度。 |
| include_zeros | 計算中是否包括零值 |


## 指數迴歸：截距 {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="指數迴歸：截距"
>abstract="指數迴歸：Y = a exp(X) + b。傳回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 指數迴歸：截距 (metric_X、metric_Y、include_zeros)]**


[!BADGE 表格]{type="Neutral"}指數迴歸：Y = a exp(X) + b。傳回 b。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 指數迴歸：斜率 {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="指數迴歸：斜率"
>abstract="指數迴歸：Y = a exp(X) + b。傳回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 指數迴歸：斜率 (metric_X、metric_Y、include_zeros)]**


[!BADGE 表格]{type="Neutral"}指數迴歸：Y = a exp(X) + b。傳回 a。


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 下限 {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="下限"
>abstract="傳回不大於給定值的最大整數。例如，若您不希望報告中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 FLOOR(Revenue) 將收入無條件捨去至最接近的金額 $569。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR (metric_X、metric_Y、include_zeros)]**

[!BADGE 列]{type="Neutral"}傳回不大於給定值的最大整數。例如，若您不希望報告中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 FLOOR(Revenue) 將收入無條件捨去至最接近的金額 $569。

| 引數 | 說明 |
|---|---|
| 量度 | 您要四捨五入的量度。 |


## 大於 {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="大於"
>abstract="輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 大於 ()]**

輸出為 0 (否) 或 1 (是)。

| 引數 | 說明 |
|---|---|
| metric_X | 您想要用於比較的基本量度。 |
| metric_Y | 您想要用於比較的依據量度。 |

### 範例

`Metric 1 > Metric 2`


## 大於或等於 {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="大於或等於"
>abstract="大於或等於。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 大於或等於 ()]**

大於或等於。輸出為 0 (否) 或 1 (是)。

| 引數 | 說明 |
|---|---|
| metric_X | 您想要用於比較的基本量度。 |
| metric_Y | 您想要用於比較的依據量度。 |

### 範例

`Metric 1 >= Metric 2`



## 雙曲餘弦 {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="雙曲餘弦"
>abstract="傳回數字的雙曲餘弦。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 雙曲餘弦 (量度)]**


[!BADGE 列]{type="Neutral"}傳回數字的雙曲餘弦。


| 引數 | 說明 |
|---|---|
| 量度 | «»您想找出雙曲餘弦的角度 (以弧度為單位) |



## 雙曲正弦 {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="雙曲正弦"
>abstract="傳回數字的雙曲正弦。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 雙曲正弦 (量度)]**

[!BADGE 列]{type="Neutral"}傳回數字的雙曲正弦。

| 引數 | 說明 |
|---|---|
| 量度 | 您想找出雙曲正弦的角度 (以弧度為單位) |


## 雙曲正切 {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="雙曲正切"
>abstract="傳回數字的雙曲正切。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 雙曲正切 (量度)]**

[!BADGE 列]{type="Neutral"}傳回數字的雙曲正切。

| 引數 | 說明 |
|---|---|
| 量度 | 您想找出雙曲正切的角度 (以弧度為單位) |


## 若   {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="若"
>abstract="如果條件參數的值非零 (是)，則結果是 value_if_true 參數的值。否則，它是 value_if_false 參數的值。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL IF (logical_test、value_if_true、value_if_false)]**


[!BADGE 列]{type="Neutral"}如果條件參數的值非零 (是)，則結果是 value_if_true 參數的值。否則，它是 value_if_false 參數的值。


| 引數 | 說明 |
|---|---|
| logical_test | 必填。可評估為 TRUE 或 FALSE 的任何值或運算式 |
| value_if_true | 您想在 logical_test 引數評估為 TRUE 時傳回的值。(若未指定則此引數預設為 0。) |
| value_if_false | 如果 logical_test 引數評估為 FALSE 時您想要傳回的值。(若不含，則此引數預設值為 0。) |


## 小於 {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="小於"
>abstract="輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 小於 ()]**

輸出為 0 (否) 或 1 (是)。

| 引數 | 說明 |
|---|---|
| metric_X | 您想要用於比較的量度。 |
| metric_Y | 您想要用於比較的依據量度。 |

### 範例

`Metric 1 < Metric 2`


## 小於或等於 {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="小於或等於"
>abstract="小於或等於。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 小於或等於 ()]**

小於或等於。輸出為 0 (否) 或 1 (是)。

| 引數 | 說明 |
|---|---|
| metric_X | 您想要用於比較的量度。 |
| metric_Y | 您想要用於比較的依據量度。 |

### 範例

`Metric 1 <= Metric 2`



## 提升度 {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="提升度"
>abstract="與控制值相比的提升率。"

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL 提升度 (規範化容器、成功量度、控制)]**

與控制值相比的提升率。

| 引數 | 說明 |
| --- | --- |
| 標準化容器 | 執行測試的基礎 (人員、工作階段或事件)。 |
| 成功量度 | 使用者用來比較變體的一個或多個量度。 |
| 控制 | 和實驗中所有其他變體進行比較的變體。輸入控制變體維度項目的名稱。 |



## 線性迴歸：相關係數 {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="線性迴歸：相關係數"
>abstract="線性迴歸：Y = a X + b。傳回相關係數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 線性迴歸：相關係數 (metric_X、metric_Y、include_zeros)]**


[!BADGE 表格]{type="Neutral"}線性迴歸：Y = a X + b。傳回相關係數。


| 引數 | 說明 |
|---|---|
| metric_X | 您想與 metric_Y 建立關聯的量度 |
| metric_Y | 您想與 metric_X 建立關聯的量度 |
| include_zeros | 計算中是否包括零值 |



## 線性迴歸：截距 {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="線性迴歸：截距"
>abstract="線性迴歸：Y = a X + b。傳回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 線性迴歸：截距 (metric_X、metric_Y、include_zeros)]**


[!BADGE 表格]{type="Neutral"}線性迴歸：Y = a X + b。傳回 b。


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 指數迴歸：預計 Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="指數迴歸：預計 Y"
>abstract="線性迴歸：Y = a X + b。傳回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 線性迴歸：預測 Y (metric_X、metric_Y、include_zeros)]**


[!BADGE 列]{type="Neutral"}線性迴歸：Y = a X + b。傳回 Y。


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 線性迴歸：斜率 {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="線性迴歸：斜率"
>abstract="線性迴歸：Y = a X + b。傳回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 線性迴歸：斜率 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}線性迴歸：Y = a X + b。傳回 a。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 以 10 為底的對數 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="以 10 為底的對數"
>abstract="傳回數字以 10 為底的對數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 以 10 為底的對數 (量度)]**


[!BADGE 列]{type="Neutral"}傳回數字以 10 為底的對數。


| 引數 | 說明 |
|---|---|
| 量度 | 您要擷取以 10 為底之對數的正實數 |


## 對數迴歸：相關係數 {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="對數迴歸：相關係數"
>abstract="對數迴歸：Y = a ln(X) + b。傳回相關係數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 對數迴歸：相關係數 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}對數迴歸：Y = a ln(X) + b。傳回相關係數。

| 引數 | 說明 |
|---|---|
| metric_X | 您想與 metric_Y 建立關聯的量度 |
| metric_Y | 您想與 metric_X 建立關聯的量度 |
| include_zeros | 計算中是否包括零值 |


## 對數迴歸：截距 {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="對數迴歸：截距"
>abstract="對數迴歸：Y = a ln(X) + b。傳回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 對數迴歸：截距 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}對數迴歸：Y = a ln(X) + b。傳回 b。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 對數迴歸：預計 Y {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="對數迴歸：預計 Y"
>abstract="對數迴歸：Y = a ln(X) + b。傳回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 對數迴歸：預測 Y (metric_X、metric_Y、include_zeros)]**

[!BADGE 列]{type="Neutral"}對數迴歸：Y = a ln(X) + b。傳回 Y。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 對數迴歸：斜率 {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="對數迴歸：斜率"
>abstract="對數迴歸：Y = a ln(X) + b。傳回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 對數迴歸：斜率 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}對數迴歸：Y = a ln(X) + b。傳回 a。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 自然對數 {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="自然對數"
>abstract="傳回數字的自然對數。自然對數是以常數 e (2.71828182845904) 為底數。LN 是 EXP 函數的反函數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 自然對數 (量度)]**

傳回數字的自然對數。自然對數是以常數 e (2.71828182845904) 為底數。LN 是 EXP 函數的反函數。

| 引數 | 說明 |
|---|---|
| 量度 | 您要擷取自然對數的正實數 |



## Not {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="Not"
>abstract="否定是一種布林值。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 非 (邏輯)]**

否定是一種布林值。輸出為 0 (否) 或 1 (是)。

| 引數 | 說明 |
|---|---|
| 邏輯 | 必填。可評估為 TRUE 或 FALSE 的值或運算式 |



## 不等於 {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="不等於"
>abstract="不等於。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 不等於 ()]**


不等於。輸出為 0 (否) 或 1 (是)。


| 引數 | 說明 |
|---|---|
| metric_X | 您想要用於比較的量度。 |
| metric_Y | 您想要用於比較的依據量度。 |

### 範例

`Metric 1 != Metric 2`


## 或 {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="或"
>abstract="無關。不等於零為是，等於零為否。輸出為 0 (否) 或 1 (是)。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 或 (邏輯測試)]**


[!BADGE 列]{type="Neutral"}分離。不等於零為是，等於零為否。輸出為 0 (否) 或 1 (是)。


| 引數 | 說明 |
|---|---|
| logical_test | 需要至少一個參數，但可以採用任意數量的參數。可評估為 TRUE 或 FALSE 的任何值或運算式 |


>[!NOTE]
>
>0 (零) 表示 False，其他值表示 True。


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="傳回 Pi：3.14159..."

<!-- markdownlint-enable MD034 -->

![影響](/help/assets/icons/Effect.svg) **[!UICONTROL PI ()]**

傳回 Pi：3.14159...


## 乘冪迴歸：相關係數 {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="乘冪迴歸：相關係數"
>abstract="乘冪迴歸：Y = b X ^ a。傳回相關係數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 乘冪迴歸：相關係數 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}乘冪迴歸：Y = b X ^ a。傳回相關係數。

| 引數 | 說明 |
|---|---|
| metric_X | 您想與 metric_Y 建立關聯的量度 |
| metric_Y | 您想與 metric_X 建立關聯的量度 |
| include_zeros | 計算中是否包括零值 |



## 乘冪迴歸：截距 {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="乘冪迴歸：截距"
>abstract="乘冪迴歸：Y = b X ^ a。傳回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 乘冪迴歸：截距 (metric_X、metric_Y、include_zeros)]**


[!BADGE 表格]{type="Neutral"}乘冪迴歸：Y = b X ^ a。傳回 b。


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 乘冪迴歸：預計 Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="乘冪迴歸：預計 Y"
>abstract="乘冪迴歸：Y = b X ^ a。傳回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 乘冪迴歸：預測 Y (metric_X、metric_Y、include_zeros)]**

[!BADGE 列]{type="Neutral"}乘冪迴歸：Y = b X ^ a。傳回 Y。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 乘冪迴歸：斜率 {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="乘冪迴歸：斜率"
>abstract="乘冪迴歸：Y = b X ^ a。傳回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 乘冪迴歸：斜率 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}乘冪迴歸：Y = b X ^ a。傳回 a。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 二次迴歸：相關係數 {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="二次迴歸：相關係數"
>abstract="二次迴歸：Y = (a + bX) ^ 2。傳回相關係數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 二次迴歸：相關係數 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}二次迴歸：Y = (a + bX) ^ 2。傳回相關係數。

| 引數 | 說明 |
|---|---|
| metric_X | 您想與 metric_Y 建立關聯的量度 |
| metric_Y | 您想與 metric_X 建立關聯的量度 |
| include_zeros | 計算中是否包括零值 |

## 二次迴歸：截距 {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="二次迴歸：截距"
>abstract="二次迴歸：Y = (a + bX) ^ 2。傳回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 二次迴歸：截距 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}二次迴歸：Y = (a + bX) ^ 2。傳回 a。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 二次迴歸：預計 Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="二次迴歸：預計 Y"
>abstract="二次迴歸：Y = (a + bX) ^ 2。傳回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 二次迴歸：預測 Y (metric_X、metric_Y、include_zeros)]**

[!BADGE 列]{type="Neutral"}二次迴歸：Y = (a + bX) ^ 2。傳回 Y。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 二次迴歸：斜率 {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="二次迴歸：斜率"
>abstract="二次迴歸：Y = (a + bX) ^ 2。傳回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 二次迴歸：斜率 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}二次迴歸：Y = (a + bX) ^ 2。傳回 b。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 倒數迴歸：相關係數 {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="倒數迴歸：相關係數"
>abstract="倒數迴歸：Y = a + b X ^ -1。傳回相關係數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 倒數迴歸：相關係數 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}倒數迴歸：Y = a + b X ^ -1。傳回相關係數。

| 引數 | 說明 |
|---|---|
| metric_X | 您想與 metric_Y 建立關聯的量度 |
| metric_Y | 您想與 metric_X 建立關聯的量度 |
| include_zeros | 計算中是否包括零值 |


## 倒數迴歸：截距 {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="倒數迴歸：截距"
>abstract="倒數迴歸：Y = a + b X ^ -1。傳回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 倒數迴歸：截距 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}倒數迴歸：Y = a + b X ^ -1。傳回 a。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 倒數迴歸：預計 Y {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="倒數迴歸：預計 Y"
>abstract="倒數迴歸：Y = a + b X ^ -1。傳回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 倒數迴歸：預測 Y (metric_X、metric_Y、include_zeros)]**

[!BADGE 列]{type="Neutral"}倒數迴歸：Y = a + b X ^ -1。傳回 Y。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |


## 倒數迴歸：斜率 {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="倒數迴歸：斜率"
>abstract="倒數迴歸：Y = a + b X ^ -1。傳回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 倒數迴歸：斜率 (metric_X、metric_Y、include_zeros)]**

[!BADGE 表格]{type="Neutral"}倒數迴歸：Y = a + b X ^ -1。傳回 b。

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 計算中是否包括零值 |



## 樣本變數

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="樣本變數"
>abstract="使用公式 (sum(metric^2) / (N - 1)) - (sum(metric))^2/(N*(N-1)) 計算樣本變數的估計值。其中 N 是標準化容器的數量。<br/>這用於&#x200B;*隨時有效*&#x200B;可信度計算的一部分。通常，此功能無法單獨使用，但可以用於檢查計算結果或&#x200B;*手動*&#x200B;執行可信度計算。"

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL 樣本變異數 (標準化容器、成功量度)]**

計算樣本變異數的預估值。

| 引數 | 說明 |
| --- | --- |
| 標準化容器 | 執行測試的基礎 (人員、工作階段或事件)。 |
| 成功量度 | 使用者用來比較變體的一個或多個量度。 |

<!-- markdownlint-enable MD034 -->



## 正弦 {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="正弦"
>abstract="傳回指定角度的正弦。如果角度以度數表示，請將角度乘以 PI()/180。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 正弦 (量度)]**


[!BADGE 列]{type="Neutral"}傳回指定角度的正弦。如果角度以度數表示，請將角度乘以 PI()/180。


| 引數 | 說明 |
|---|---|
| 量度 | 您要擷取正弦的角度 (以弧度為單位) |




## T 分數 {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="T 分數"
>abstract="[平均值](cm-functions.md#mean)的偏差除以標準差。[Z 分數](#z-score)的別名。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL T 分數 (量度，include_zeros)]**

[平均值](cm-functions.md#mean)的偏差除以標準差。[Z 分數](#z-score)的別名。

| 引數 | 說明 |
|---|---|
| 量度 | 您要 T 分數的量度 |
| include_zeros | 計算中是否包括零值 |


## T 檢定 {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="T 檢定"
>abstract="執行 m 尾 t 檢定，使用 x 的 t 分數和 n 自由度。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL T 檢定 (量度、度數、尾部)]**

執行 m 尾 t 檢定，使用 x 的 t 分數和 n 自由度。

| 引數 | 說明 |
|---|---|
| 量度 | 您要執行 T 檢定的量度 |
| 角度 | 自由度 |
| 尾部 | 用於執行 T 檢定的尾部長度 |

### 詳細資料

此簽名為 T 檢定 (量度、角度、尾部)。底下其僅呼叫 ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg)**[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**。此函數類似於 **[Z 檢定](#z-test)** 函數，此函數執行 ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg)**[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**。

- ***m*** 是尾數。
- ***n*** 是自由度，且對整個報告而言應為一個常數，亦即不會逐列變更。
- ***x*** 是 T 檢定的統計資料，且通常會是根據量度的公式 (例如，**[Z 分數](#z-score)**)，並在每列進行評估。

傳回值是在給定自由度和反面的數目下，出現檢定統計資料 x 的機率。

### 範例

1. 使用函數找出離群值：

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. 將此函數與 **[if](#if)** 合併，以便忽略非常高或非常低的退回率，然後統計其他項目上的工作階段：

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## 正切 {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="正切"
>abstract="傳回指定角度的正切。如果角度以度數表示，請將角度乘以 PI()/180。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 正切 (量度)]**

傳回指定角度的正切。如果角度以度數表示，請將角度乘以 PI()/180。

| 引數 | 說明 |
|---|---|
| 量度 | 您要擷取正切的角度 (以弧度為單位) |



## Z 分數 {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Z 分數"
>abstract="平均值的偏差除以標準差。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL Z 分數 (量度，include_zeros)]**

[!BADGE 列]{type="Neutral"}平均值的偏差除以標準差。

| 引數 | 說明 |
|---|---|
| 量度 | 您要 Z 分數的量度 |
| include_zeros | 計算中是否包括零值 |

Z 分數為 0 (零) 表示分數與平均值相同。Z 分數可為正或負，代表其高於或低於平均值多少標準差。

Z 分數的方程式為：

![](assets/z_score.png)

其中 ***[!DNL x]*** 是原始分數，***[!DNL μ]*** 是群體平均值，***[!DNL σ]*** 是群體標準差。

>[!NOTE]
>
>***[!DNL μ]*** (mu) 和&#x200B;***[!DNL σ]*** (sigma) 會自動從量度中計算得出。



## Z 檢定 {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Z 檢定"
>abstract="執行 n 尾 z 檢定，使用 x 的 z 分數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg)**[!UICONTROL Z 檢定 (metric_tails)]**

執行 n 尾 z 檢定，使用 x 的 z 分數。

| 引數 | 說明 |
|---|---|
| 量度 | 您要執行 Z 檢定的量度 |
| 尾部 | 用於執行 Z 檢定的尾部長度 |

>[!NOTE]
>
>此處假設值為常態分布。




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->