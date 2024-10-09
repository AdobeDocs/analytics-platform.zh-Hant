---
title: 基本函數
description: 計算量度產生器可讓您套用統計和數學函數，以建立進階計算量度。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 29%

---

# 基本函數


[計算量度產生器](cm-workflow/cm-build-metrics.md)可讓您套用統計和數學函式。 本文記錄函式及其定義的字母順序清單。

>[!NOTE]
>
>此處將 [!DNL metric] 視為函數中的引數，也允許使用其他的量度運算式。例如，[COLUMN MAXIMUM（量度）](#column-maximum)也允許使用[COLUMN MAXIMUM（頁面檢視+造訪）](#column-maximum)。



## 表格函式和列函式

表格函數是表格每一列的輸出都相同。列函數則是表格每一列的輸出都不同。

在適用和相關的情況下，函式會以函式型別註釋： [!BADGE 表格]{type="Neutral"}[!BADGE 列]{type="Neutral"}

## 「包含零」引數的意義是什麼？

此參數指出是否在計算中包括零。有時零表示&#x200B;*無*，但有時很重要。

例如，如果您有收入量度，然後新增頁面檢視量度至報表，您的收入會突然有更多的列，而且全都是零。 您可能不想讓額外的量度影響任何&#x200B;**[MEAN](cm-functions.md#mean)**、**[ROW MINIMUM](cm-functions.md#row-min)**、**[QUARTILE](cm-functions.md#quartile)**&#x200B;以及您在收入欄中擁有的其他計算。 在此情況下，您需要檢查`include-zeros`引數。

另一種情況是，您有兩個相關量度，且其中一個的平均值或最小值較高，因為有些列是零。  在這種情況下，您可以選擇不檢查引數以包含零



## 絕對值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 絕對值（量度）]**

[!BADGE 列]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其絕對值的量度。 |


## 欄最大值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 欄最大值（量度，包括_零）]**

傳回量度欄中一組維度元素的最大值。MAXV 會垂直評估單一欄 (量度) 中的維度元素。

| 引數 | 說明 |
|---|---|
| 量度 | 至少需要一個量度，但可使用任意數量的量度做為引數。 |
| include_zeros | 是否在計算中包含零值。 |


## 欄最小值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 欄最小值（量度，include_zeros）]**

傳回量度欄中一組維度元素的最小值。MINV 會垂直評估單一欄 (量度) 中的維度元素。

| 引數 | 說明 |
|---|---|
| 量度 | 至少需要一個量度，但可使用任意數量的量度做為引數。 |
| include_zeros | 是否在計算中包含零值。 |


## 欄總和

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 資料行總和（量度）]**

將某一欄中量度的所有數值相加（涵蓋維度的各個元素）。

| 引數 | 說明 |
|---|---|
| 量度 | 至少需要一個量度，但可使用任意數量的量度做為引數。 |


## 計數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 計數（量度）]**

[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要計數的量度。 |


## 指數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數（量度）]**

[!BADGE 列]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 套用至基底e的指數。 |


## 平均值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric， include_zeros)]**

[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算平均值的量度。 |
| include_zeros | 是否在計算中包含零值。 |


## 中間值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric， include_zeros)]**

[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算中間值的量度。 |
| include_zeros | 是否在計算中包含零值。 |


## 模數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 模數(metric_X， metric_Y)]**

使用歐幾里得除法，將x除以y之後傳回餘數。

| 引數 | 說明 |
|---|---|
| metric_X | 您要除的第一個量度。 |
| metric_Y | 您要除的第二個量度。 |

### 範例

傳回值的正負號與輸入相同 (或等於零)。

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

為了確保您一律得到正數，請使用

```
MODULO(MODULO(x,y)+y,y)
```

## 百分位數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 百分位數(metric， k， include_zeros)]**

[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 0 至 100 (含) 範圍內的百分位數值。 |
| k | 定義相對位置的量度欄。 |
| include_zeros | 是否在計算中包含零值。 |



## 乘冪運運算元

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘冪運運算元(metric_X， metrix_Y)]**

傳回x提升至y次方。

| 引數 | 說明 |
|---|---|
| metric_X | 您要提升至metric_Y次方的量度。 |
| metric_Y | 您希望將metric_X提升到的能力。 |


## 四分位數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric， quartile， include_zeros)]**

[!BADGE 表格]{type="Neutral"}當QUARTILE分別等於`0` （零）、`2`和`4`時，[COLUMN MINIMUM](#column-minimum)、[MEDIAN](#median)和[COLUMN MAXIMUM](#column-maximum)會傳回與[QUARTILE](#quartile)相同的值。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算四分位數值的量度。 |
| 四分位數 | 指出要傳回的四分位數值。 |
| include_zeros | 是否在計算中包含零值。 |


## 四捨五入

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric， number)]**

不含&#x200B;*number*&#x200B;引數的四捨五入與含&#x200B;*number*&#x200B;引數為0的四捨五入相同，也就是四捨五入到最接近的整數。  使用&#x200B;*number*&#x200B;引數時，ROUND會傳回小數點右邊的&#x200B;*number*&#x200B;位數。  如果&#x200B;*number*&#x200B;為負數，則會傳回小數點左邊的0。

| 引數 | 說明 |
|---|---|
| 量度 | 您要四捨五入的量度。 |
| 數字 | 要傳回的小數點右邊的位數。 （如果為負數，會在小數點左邊傳回零）。 |

### 範例

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## 列計數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列計數()]**

傳回指定欄的列計數 (維度中報告的唯一元素數)。超過&#x200B;*個不重複值*&#x200B;計為1。


## 列最大值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列MAX（量度，include_zeros）]**

每一列的最大欄數。

| 引數 | 說明 |
|---|---|
| 量度 | 至少需要一個量度，但可使用任意數量的量度做為引數。 |
| include_zeros | 是否在計算中包含零值。 |

## 列最小值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列最小值（量度，包含_零）]**

每一列的最小欄數。

| 引數 | 說明 |
|---|---|
| 量度 | 至少需要一個量度，但可使用任意數量的量度做為引數。 |
| include_zeros | 是否在計算中包含零值。 |



## 列總和

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 資料列總和（量度，包含_零）]**

每一列的欄總和。

| 引數 | 說明 |
|---|---|
| 量度 | 至少需要一個量度，但可使用任意數量的量度做為引數。 |


## 平方根

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（量度，包含_零）]**

[!BADGE 列]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算平方根的量度。 |


## 標準差

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 標準差（量度，包括_零）]**

[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| | 您要計算其標準差的量度。 |
| include_zeros | 是否在計算中包含零值。 |


## 變數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric， include_zeros)]**

[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算變異數的量度。 |
| include_zeros | 是否在計算中包含零值。 |


VARIANCE 的方程式為：

![](assets/variance_eq.png){width="100"}

其中&#x200B;*x*&#x200B;為樣本平均值，[MEAN（*量度*）](#mean)且&#x200B;*n*&#x200B;為樣本大小。


若要計算變數，您可以檢視整欄的數字。 請先從那列數字計算平均值。取得平均值後，請逐一檢視每個專案，並執行下列作業：

1. 將數字減去平均值。

1. 取結果的平方。

1. 將其加入總計。

一旦您疊代了整個欄，您就會有單一總計。 接著將合計除以欄中的項目數。該數字會是欄的變數。一個單一的數字。但是，它會顯示為一欄數字。

在下列三個專案欄的範例中：

| 欄 |
|:---:|
| 1 |
| 2 |
| 3 |

欄平均值為 2。資料行的變數是((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3。




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