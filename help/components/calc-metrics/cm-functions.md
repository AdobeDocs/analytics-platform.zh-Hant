---
title: 參考——基本函式
description: '計算量度產生器可讓您套用統計和數學函數，以建立進階計算量度。 '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# 參考——基本函式

計算量度產生器可讓您套用統計和數學函數，以建立進階計算量度。

以下是函數及其定義的字母順序清單。

> [!NOTE] 此處將 [!DNL metric] 視為函數中的引數，也允許使用其他的量度運算式。例如，[!DNL MAXV(metrics)] 也允許用於 [!DNL MAXV(PageViews + Visits).]

## 表格函數和列函數

表函式是表中每一行的輸出相同的函式。 行函式是表中每一行的輸出都不同的函式。

## 絕對值 (列)

傳回數字的絕對值。數字的絕對值是正值數字。

```
ABS(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要取絕對值的量度。 |

## 欄最大值

傳回單一量度欄中一組維度元素的最大值。MAXV 會在各維度元素上垂直評估單一欄 (量度)。

```
MAXV(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要評估的量度。 |

## 欄最小值

傳回單一量度欄中一組維度元素的最小值。MINV 會在各維度元素上垂直評估單一欄 (量度)。

```
MINV(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要評估的量度。 |

## 欄總和

將單一欄中量度的所有數值相加 (包括所有維度元素)。

```
SUM(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要其總值或總和的量度。 |

## 計數 (表格)

傳回單一欄中量度的非零值數目 (或計數) (在一個維度中報告的唯一元素數目)。

```
COUNT(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要計算的量度。 |

## 指數 (列)

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | The exponent applied to the base *e*. |

## 乘冪

乘冪運算元

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (乘以 y 次)
</pre>

## 平均值 (表格)

傳回單一欄中量度的算術平均值。

```
MEAN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要取平均值的量度。 |

## 中位數 (表格)

傳回單一欄中量度的中位數。中位數是位於一組數字中間的數字，也就是一半數字的值大於或等於中位數，另一半數字的值小於或等於中位數。

```
MEDIAN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要取中位數的量度。 |

## 模數

col1 / col2的余數，使用歐幾里得除法。

傳回x除以y之後的余數。

```
x = floor(x/y) + modulo(x,y)
```

傳回值與輸入具有相同符號（或為零）。

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

若要一律取得正數，請使用

```
modulo(modulo(x,y)+y,y)
```

## 百分位數 (表格)

傳回量度值的第k個百分位數。 您可以使用此函式來建立接受的臨界值。 例如，您可以決定檢驗分數高於第 90 個百分位數的維度元素。

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>量度</i> </td> 
   <td colname="col2"> 定義相對位置的量度欄。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> 從 0 到 100 之間的百分位數值，包含 0 和 100。 </td> 
  </tr> 
 </tbody> 
</table>

## 四分位數 (表格)

傳回量度值的四分位數。例如，四分位數可用來尋找創造最高收入的前 25% 產品。當四分位數分別等於 0 (零)、2 和 4 時，MINV、MEDIAN 和 MAXV 會傳回與該四分位數相同的值。

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>量度</i> </td> 
   <td colname="col2"> 您想要取四分位數值的量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> 指出要傳回的*值。 </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. 如果 *quart* = 1，QUARTILE 會傳回第一個四分位數 (第 25 個百分位數)。如果 *quart* = 2，QUARTILE 會傳回第一個四分位數 (第 50 個百分位數)。如果 *quart* = 3，QUARTILE 會傳回第一個四分位數 (第 75 個百分位數)。如果 *quart* = 4，QUARTILE 會傳回最大值。

## 四捨五入

傳回給定值的最接近整數。例如，如果您不想報表中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 Round(*Revenue*) 可將收入四捨五入至最接近的美金 $569。報告$569.51的產品將四捨五入至最接近的$570。

```
ROUND(metric)
```

| 引數 | 說明 |
|---|---|
| *數字* | 您要四捨五入的量度。 |

沒有數字參數的四捨五入與有數字參數 0 的四捨五入相同，也就是四捨五入至最近的整數。在有數字參數的情況下，系統會傳回小數點右邊的數字。如果數字是負值，則傳回小數點左邊的 0。

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## 列計數

傳回指定欄的列數 (在一個維度中報告的唯一元素數)。「超出唯一數目」計為 1。

## 列最大值

每一列的最大欄數。

## 列最小值

每一列的最小欄數。

## 列總和

每一列的欄總和。

## 平方根 (列)

傳回數字的正平方根。數字的平方根是該數字的 1/2 乘冪值。

```
SQRT(metric)
```

| 引數 | 說明 |
|---|---|
| *數字* | 您想要取平方根的量度。 |

## 標準差 (表格)

根據一組資料樣本，傳回標準差 (或變異數的平方根)。

STDEV 的方程式為：

![](assets/std_dev.png)

其中x是樣本平均值(*量度*), *n是樣本大小* 。

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> 引數</b> </td> 
   <td> <b> 說明</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> 量度</i></b> </td> 
   <td> <p> 您想要取標準差的量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 變異數 (表格)

根據一組資料樣本，傳回變異數。

VARIANCE 的方程式為：

![](assets/variance_eq.png)

其中x是樣本平均值，MEAN(*metric*), ** n是樣本大小。

```
VARIANCE(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要取變異數的量度。 |

為了計算差異，您會查看整列數字。 從那個數字清單中，你先計算平均值。 取得平均值後，請陸續處理每個項目，然後進行下列步驟：

1. 將數字減去平均值。

2. 取結果的平方。

3. 將其加入總計。

在整個欄上迭代後，您會有單一總計。 然後，您將該總計除以欄中的項目數。 該數字是列的變數。 只是一個數字。 但是，它會顯示為一列數字。

舉例來說，假設您的欄中有三個項目：

1

2

3

此列的平均值為2。 欄的變數將會是 ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3。在臨機分析中，這看起來如下：

1 2/3

2 2/3

3 2/3
