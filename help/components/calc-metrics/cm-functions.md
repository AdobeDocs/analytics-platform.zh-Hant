---
title: 基本函數
description: 瞭解基本計算量度函式。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 92%

---

# 基本函數


使用[計算量度產生器](cm-workflow/cm-build-metrics.md)可套用統計和數學函數。本文記錄了函數及其定義的清單，依字母順序排列。

>[!NOTE]
>
>此處將 [!DNL metric] 視為函數中的引數，也允許使用其他的量度運算式。例如，[欄最大值 (量度)](#column-maximum) 也允許使用 [欄最大值 (頁面檢視 + 造訪)](#column-maximum)。



## 表格函數和列函數的比較

表格函數是表格每一列的輸出都相同。列函數則是表格每一列的輸出都不同。

在適用且相關的情況下，函數會以函數類型進行註解：[!BADGE 表格]{type="Neutral"}或[!BADGE 列]{type="Neutral"}

## include_zeros 參數的意義是什麼? 

此參數指出是否在計算中包括零。有時候零&#x200B;*沒有意義*，有時候卻很重要。

例如，如果您有「收入」量度，隨後新增「頁面檢視」量度至報表，您的收入會突然出現許多全都是零的列。您可能不希望該附加量度影響任何 **[平均值](cm-functions.md#mean)**、**[列最小值](cm-functions.md#row-min)**、**[四分位數](cm-functions.md#quartile)**，以及收入欄中的更多計算。在這種情況下，您可以勾選 `include-zeros` 參數。

另一種情況是，您有兩個感興趣的量度，其中一個具有較高的平均值或最小值，因為某些列是零。在這種情況下，您可以選擇不檢查參數是否包括零



## 絕對值 {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="絕對值"
>abstract="傳回數字的絕對值。數字的絕對值是正值的數字。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 絕對值 (量度)]**

[!BADGE 列]{type="Neutral"}傳回數字的絕對值。 數字的絕對值是正值的數字。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其絕對值的量度。 |


## 欄最大值 {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="欄最大值"
>abstract="傳回量度欄中一組維度元素的最大值。MAXV 會垂直評估單一欄 (量度) 中的維度元素。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 欄最大值 (量度，包括零)]**

傳回量度欄中一組維度元素的最大值。MAXV 會垂直評估單一欄 (量度) 中的維度元素。

| 引數 | 說明 |
|---|---|
| 量度 | 需要至少一個量度，但可以採用任意數量的量度作為參數。 |
| 包括零 | 計算中是否包括零值。 |


## 欄最小值 {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="欄最小值"
>abstract="傳回量度欄中一組維度元素的最小值。MINV 會垂直評估單一欄 (量度) 中的維度元素。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 欄最小值 (量度，包括零)]**

傳回量度欄中一組維度元素的最小值。MINV 會垂直評估單一欄 (量度) 中的維度元素。

| 引數 | 說明 |
|---|---|
| 量度 | 需要至少一個量度，但可以採用任意數量的量度作為參數。 |
| 包括零 | 計算中是否包括零值。 |


## 欄總和 {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="欄總和"
>abstract="將一欄中量度的所有數值 (涵蓋維度的所有元素) 相加。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 欄總和 (量度)]**

將一欄中量度的所有數值 (涵蓋維度的所有元素) 相加。

| 引數 | 說明 |
|---|---|
| 量度 | 需要至少一個量度，但可以採用任意數量的量度作為參數。 |


## 計數 {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="計數"
>abstract="傳回一欄中量度的數目、計數或非零數值 (在一個維度中報告的唯一元素數目)。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 計數 (量度)]**

[!BADGE 表格]{type="Neutral"}傳回資料行中量度的非零值數目或計數（維度中報告的唯一元素數目）。

| 引數 | 說明 |
|---|---|
| 量度 | 您想計數的量度。 |


## 指數 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="指數"
>abstract="傳回 e 的指定數字的次方。常數 e 是自然對數的底數，等於 2.71828182845904。EXPONENT 是 LN (一個數字的自然對數) 的反函數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數 (量度)]**

[!BADGE 列]{type="Neutral"}傳回e提升至指定數字的冪。 常數 e 是自然對數的底數，等於 2.71828182845904。EXPONENT 是 LN (一個數字的自然對數) 的反函數。

| 引數 | 說明 |
|---|---|
| 量度 | 套用至底數 e 的指數。 |


## 平均值 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="平均值"
>abstract="傳回一欄中量度的算術平均數或平均值"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 平均值 (量度，包括零)]**

[!BADGE 表格]{type="Neutral"}傳回資料行中量度的算術平均值或平均值。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其平均值的量度。 |
| 包括零 | 計算中是否包括零值。 |


## 中位數 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="中位數"
>abstract="傳回一欄中量度的中位數。中位數是一組數字中位於中間的數字。意即，有一半的數字其值大於或等於中位數，另有一半的值小於或等於中位數。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 中間值 (量度，包括零)]**

[!BADGE 表格]{type="Neutral"}傳回資料行中量度的中位數。 中位數是一組數字中位於中間的數字。意即，有一半的數字其值大於或等於中位數，另有一半的值小於或等於中位數。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其中間值的量度。 |
| 包括零 | 計算中是否包括零值。 |


## 模數 {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="模數"
>abstract="傳回使用歐幾里德輾轉相除法將 x 除以 y 後的餘數。 "

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 模數 (metric_X、metric_Y)]**

傳回使用歐幾里德輾轉相除法將 x 除以 y 後的餘數。

| 引數 | 說明 |
|---|---|
| metric_X | 您想要相除的第一個量度。 |
| metric_Y | 您想要相除的第二個量度。 |

### 範例

傳回值的正負號與輸入相同 (或等於零)。

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

為了確保一律取得正數，請使用

```
MODULO(MODULO(x,y)+y,y)
```

## 百分位數 {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="百分位數"
>abstract="傳回第 n 個百分位數，該值介於 0 到 100 之間。當 n &lt; 0 時，則函數使用零。當 n > 100 時，函數傳回 100。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 百分位數 (量度，k，包括零)]**

[!BADGE Table]{type="Neutral"}傳回第n個百分位數，這個值介於0到100之間。 當 n &lt; 0 時，則函數使用零。當 n > 100 時，函數傳回 100。

| 引數 | 說明 |
|---|---|
| 量度 | 0 至 100 (含) 範圍內的百分位數值。 |
| k | 定義相對位置的量度欄。 |
| 包括零 | 計算中是否包括零值。 |



## 乘冪運算子 {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="乘冪運算子"
>abstract="傳回 x 的 y 次方。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘冪運算子 (metric_X、metrix_Y)]**

傳回 x 的 y 次方。

| 引數 | 說明 |
|---|---|
| metric_X | 您想要以 metric_Y 作為次方連乘的量度。 |
| metric_Y | 您想要將 metric_X 作為底數要連乘的次方。 |


## 四分位數 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="四分位數"
>abstract="傳回量度的數值四分位數。例如，四分位數可用於尋找創造最多營收的前 25% 產品。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 四分位數 (量度、四分位數、包括零)]**

[!BADGE 表格]{type="Neutral"}傳回量度值的四分位數。 例如，四分位數可用來尋找推動最高收入的前 25% 產品。當四分位數分別等於 `0` (零)、`2` 和 `4` 時，[欄最小值](#column-minimum)、[中間值](#median)和[欄最大值](#column-maximum)傳回與[四分位數](#quartile)相同的值。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其四分位數值的量度。 |
| 四分位數 | 指出要傳回哪個四分位數值。 |
| 包括零 | 計算中是否包括零值。 |


## 四捨五入 {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="四捨五入"
>abstract="沒有&#x200B;*數值*&#x200B;參數的四捨五入值等於&#x200B;*數值*&#x200B;參數為 0 的四捨五入值，也就是四捨五入到最接近的整數。具有&#x200B;*數值*&#x200B;參數時，則會在小數點右側傳回與&#x200B;*數值*&#x200B;一樣多的小數位數。如果&#x200B;*數值*&#x200B;為負，則會在小數點左側傳回 0。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 四捨五入 (量度，數值)]**

沒有&#x200B;*數值*&#x200B;參數的四捨五入值等於&#x200B;*數值*&#x200B;參數為 0 的四捨五入值，也就是四捨五入到最接近的整數。具有&#x200B;*數值*&#x200B;參數時，則會在小數點右側傳回與&#x200B;*數值*&#x200B;一樣多的小數位數。如果&#x200B;*數值*&#x200B;為負，則會在小數點左側傳回 0。

| 引數 | 說明 |
|---|---|
| 量度 | 您要四捨五入的量度。 |
| 數字 | 要傳回小數點右邊的多少位數字。(如果為負數，則會在小數點左側傳回零)。 |

### 範例

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## 列計數 {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="列計數"
>abstract="傳回指定欄的列計數 (維度中報告的唯一元素數)。*「超出唯一值*」計為 1。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列計數 ()]**

傳回指定欄的列計數 (維度中報告的唯一元素數)。*「超出唯一值*」計為 1。


## 列最大值 {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="列最大值"
>abstract="每列的最大欄數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列最大值 (量度，包括零)]**

每列的最大欄數。

| 引數 | 說明 |
|---|---|
| 量度 | 需要至少一個量度，但可以採用任意數量的量度作為參數。 |
| 包括零 | 計算中是否包括零值。 |


## 列最小值 {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="列最小值"
>abstract="每列的最小欄數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列最小值 (量度，包括零)]**

每列的最小欄數。

| 引數 | 說明 |
|---|---|
| 量度 | 需要至少一個量度，但可以採用任意數量的量度作為參數。 |
| 包括零 | 計算中是否包括零值。 |



## 列總和 {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="列總和"
>abstract="每一列的欄總和。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列總和 (量度，包括零)]**

每一列的欄總和。

| 引數 | 說明 |
|---|---|
| 量度 | 需要至少一個量度，但可以採用任意數量的量度作為參數。 |


## 平方根 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="平方根"
>abstract="傳回數字的正平方根。數字的平方根是該數字的 1/2 次方。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根 (量度，包括零)]**

[!BADGE 列]{type="Neutral"}傳回數字的正平方根。 數字的平方根是該數字的 1/2 次方。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其平方根的量度。 |


## 標準差 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="標準差"
>abstract="根據一組來自母體的樣本資料，傳回標準差或變異數的平方根。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 標準差 (量度，包括零)]**

[!BADGE 表格]{type="Neutral"}傳回標準差，或變異數的平方根，根據資料樣本母體。

| 引數 | 說明 |
|---|---|
| | 您要計算其標準差的量度。 |
| 包括零 | 計算中是否包括零值。 |


## 變異數 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="變異數"
>abstract="根據來自母體的一組樣本資料，傳回變異數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 變數 (量度，包括零)]**

[!BADGE 表格]{type="Neutral"}傳回以樣本資料母體為基礎的變異數。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其變數的量度。 |
| 包括零 | 計算中是否包括零值。 |


變數的方程式為：

![](assets/variance_eq.png){width="100"}

其中 *x* 是樣本平均值 [MEAN(*量度*)](#mean)，而 *n* 是樣本大小。


為了計算變數，請查看整欄的數字。請先從那列數字計算平均值。取得平均值後，請陸續處理每個項目，然後進行下列步驟:

1. 將數字減去平均值。

1. 取結果的平方。

1. 將其加入總計。

反覆運算整欄之後，會得到單一合計。接著將合計除以欄中的項目數。該數字會是欄的變數。一個單一的數字。但是，它會顯示為一欄數字。

在以下三項目欄的範例中：

| 欄 |
|:---:|
| 1 |
| 2 |
| 3 |

欄平均值為 2。欄的變數為 ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3。

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->