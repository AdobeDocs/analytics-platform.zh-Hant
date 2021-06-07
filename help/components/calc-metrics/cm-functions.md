---
title: 參考資料 - 基本函數
description: 計算量度產生器可讓您套用統計和數學函數，以建立進階計算量度。
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 100%

---

# 參考資料 - 基本函數

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[深入了解...](/help/getting-started/cja-aa.md)

計算量度產生器可讓您套用統計和數學函數，以建立進階計算量度。

以下是函數及其定義的字母順序清單。

>[!NOTE]
>
>此處將 [!DNL metric] 視為函數中的引數，也允許使用其他的量度運算式。例如，[!DNL MAXV(metrics)] 也允許用於 [!DNL MAXV(PageViews + Visits).]

## 表格函數和列函數

表格函數是表格每一列的輸出都相同。列函數則是表格每一列的輸出都不同。

## 絕對值 (列)

傳回數字的絕對值。數字的絕對值是正值的數字。

```
ABS(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取其絕對值的量度。 |

## 欄最大值

傳回量度欄中一組維度元素的最大值。MAXV 會垂直評估單一欄 (量度) 中的維度元素。

```
MAXV(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想評估的量度。 |

## 欄最小值

傳回量度欄中一組維度元素的最小值。MINV 會垂直評估單一欄 (量度) 中的維度元素。

```
MINV(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想評估的量度。 |

## 欄總和

將一欄中量度的所有數值 (所有維度元素) 相加。

```
SUM(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要計算總值或總和的量度。 |

## 計數 (表格)

傳回一欄中量度的非零值數目 (或計數) (在一個維度中報告的獨特元素數目)。

```
COUNT(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想計數的量度。 |

## 指數 (列)

傳回給定數字的 *e* 乘冪。常數 *e* 是自然對數的底數，等於 2.71828182845904。EXP 是 LN (一個數字的自然對數) 的反函數。

```
EXP(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 套用至底數 *e* 的指數。 |

## 乘冪

乘冪運算元

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (乘以 y 次)
</pre>

## 平均值 (表格)

傳回一欄中量度的算術平均值。

```
MEAN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取平均值的量度。 |

## 中位數 (表格)

傳回一欄中量度的中位數。中位數是位於一組數字中間的數字，也就是一半數字的值大於或等於中位數，另一半數字的值小於或等於中位數。

```
MEDIAN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取中位數的量度。 |

## 模數

col1 / col2 的餘數，使用歐幾里德輾轉相除法。

傳回將 x 除以 y 之後的餘數。

```
x = floor(x/y) + modulo(x,y)
```

傳回值的正負號與輸入相同 (或等於零)。

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

若想一律取得正數，請使用

```
modulo(modulo(x,y)+y,y)
```

## 百分位數 (表格)

傳回量度值的第 k 個百分位數。您可使用此函數來建立接受臨界值。例如，您可以決定檢驗分數高於第 90 個百分位數的維度元素。

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
   <td colname="col2"> 0 至 100 (含) 範圍內的百分位數值。 </td> 
  </tr> 
 </tbody> 
</table>

## 四分位數 (表格)

傳回量度值的四分位數。例如，四分位數可用來尋找推動最高收入的前 25% 產品。當 quart 分別等於 0 (零)、2 和 4 時，MINV、MEDIAN 和 MAXV 會傳回與 QUARTILE 相同的值。

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
   <td colname="col2"> 您要擷取四分位數值的量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> 指出傳回哪個值*。 </td> 
  </tr> 
 </tbody> 
</table>

*如果 *quart* = 0，QUARTILE 會傳回最小值。如果 *quart* = 1，QUARTILE 會傳回第一個四分位數 (第 25 個百分位數)。如果 *quart* = 2，QUARTILE 會傳回第一個四分位數 (第 50 個百分位數)。如果 *quart* = 3，QUARTILE 會傳回第一個四分位數 (第 75 個百分位數)。如果 *quart* = 4，QUARTILE 會傳回最大值。

## 四捨五入

傳回給定值的最接近整數。例如，如果您不想報表中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 Round(*Revenue*) 可將收入四捨五入至最接近的美金 $569。價格 $569.51 的產品則會四捨五入至最接近的美金 $570。

```
ROUND(metric)
```

| 引數 | 說明 |
|---|---|
| *數字* | 您要四捨五入的量度。 |

沒有小數參數的四捨五入值等於小數參數為 0 的四捨五入值，也就是四捨五入到最接近的整數。具有小數參數時，則會在小數點右側傳回與此值一樣多的小數位數。如果小數參數為負，則會在小數點左側傳回 0。

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## 列計數

傳回指定欄的列數 (在一個維度中報告的唯一元素數)。「超出不重複值」計為 1。

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
| *數字* | 您要擷取平方根的量度。 |

## 標準差 (表格)

根據一組資料樣本，傳回標準差 (或變異數的平方根)。

STDEV 的方程式為：

![](assets/std_dev.png)

其中 x 是樣本平均值 (*量度*) 而 *n* 是樣本大小。

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
   <td> <b> <i> 量度</i> </b> </td> 
   <td> <p> 您要擷取標準差的量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 變異數 (表格)

根據一組資料樣本，傳回變異數。

VARIANCE 的方程式為：

![](assets/variance_eq.png)

其中 x 是樣本平均值 MEAN(*量度*)，而 *n* 是樣本大小。

```
VARIANCE(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要擷取變異數的量度。 |

為了計算變數，請查看整欄的數字。請先從那列數字計算平均值。取得平均值後，請陸續處理每個項目，然後進行下列步驟：

1. 將數字減去平均值。

2. 取結果的平方。

3. 將其加入總計。

反覆運算整欄之後，會得到單一合計。接著將合計除以欄中的項目數。該數字會是欄的變數。一個單一的數字。但是，它會顯示為一欄數字。

舉例來說，假設您的欄中有三個項目：

1

2

3

欄平均值為 2。欄的變數將會是 ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3。
