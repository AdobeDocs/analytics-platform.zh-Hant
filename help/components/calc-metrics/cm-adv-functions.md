---
title: 參考——進階函式
description: 勾選函數下拉式清單中的顯示進階即可存取這些函數。
translation-type: tm+mt
source-git-commit: 2dab33dca173fcc0eab657b810e85e4740e5d7e0

---


# 參考——進階函式

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## 表格函數和列函數

表函式是表中每一行的輸出相同的函式。 行函式是表中每一行的輸出都不同的函式。

## 「包括零」參數的意義是什麼？

它會告訴計算中是否包含零。 有時零表示「無」，但有時它很重要。

例如，如果您有「收入」量度，然後新增「頁面檢視」量度至報表，您的收入會突然出現多行，全部為零。 您可能不希望這影響任何MEAN、MIN、QUARTILE等。 計算。 在這種情況下，您會檢查include-zeros參數。

另一方面，如果您有兩個您感興趣的量度，則可能不合理地指出其中一個的平均值或最小值較高，因為其部分列為零，因此您不會勾選參數以包含零。

## 和

傳回其引數的值。 使用NOT可確定值不等於一個特定值。

>[!NOTE] 0 (零) 表示 False，其他值表示 True。

```
AND(logical_test1,[logical_test2],...)
```

| 引數 | 說明 |
|---|---|
| *logical_test1* | 必要。任何可被評估為 TRUE 或 FALSE 的值或運算式。 |
| *logical_test2* | 選填。您要評估為TRUE或FALSE的其他條件 |

## 近似相異計數 (維度)

針對選取的維度，傳回維度項目的近似不重複計數。該函式使用HyperLogLog(HLL)方法逼近不同計數。  其設定可確保該值在實際值的5%內，即95%的時間。

```
Approximate Count Distinct (dimension)
```

| 引數 |  |
|---|---|
| *維度* | 您要求近似不同項目計數的維度。 |

## 範例使用案例

近似相異計數 (客戶 ID eVar) 是此函數的常見使用案例。

新「近似客戶」計算量度的定義：

![](assets/approx-count-distinct.png)

這是可以在報表中使用「近似客戶」量度的方式：

![](assets/approx-customers.png)

## 超出唯一客戶數

與Count()和RowCount()一樣，Approximate Count Distinct()受「超出唯一 [客戶數」限制的約束](https://marketing.adobe.com/resources/help/zh_TW/reference/metrics_uniques_high_numbers.html)。 如果維度在特定月份內達到「超出唯一客戶數」限制，該值會計為1個維度項目。

## 比較計數函式

Approximate Count Distinct()是Count()和RowCount()函式的改進，因為所建立的量度可用於任何維度報表，以呈現個別維度的項目近似計數。 例如，「行動裝置類型」報表中使用的客戶ID計數。

此函式的精確度會略低於Count()和RowCount()，因為它使用HLL方法，而Count()和RowCount()是精確的計數。

## 反餘弦 (列)

傳回量度的反餘弦 (或餘弦的反函數)。反餘弦是一種角度，其餘弦是數字。傳回的角度在 0 (零) 到 pi 的弧度之間。如要將結果從弧度轉換為度，請將結果乘以 180/PI( )。

```
ACOS(metric)
```

| 引數 |  |
|---|---|
| *量度* | 您想要的角度的餘弦，值為 -1 到 1。 |

## 反正弦 (列)

傳回數字的反正弦。反正弦是一種角度，其正弦是數字。傳回的角度在 -pi/2 到 pi/2 的弧度之間。若想以度表示反正弦，請將結果乘以 180/PI( )。

```
ASIN(metric) 
```

| 引數 |  |
|---|---|
| *量度* | 您想要的角度的餘弦，值為 -1 到 1。 |

## 反正切 (列)

傳回數字的反正切。反正切是一種角度，其正切是數字。傳回的角度在 -pi/2 到 pi/2 的弧度之間。若想以度表示反正切，請將結果乘以 180/PI( )。

```
ATAN(metric)
```

| 引數 |  |
|---|---|
| *量度* | 您想要的角度的餘弦，值為 -1 到 1。 |

## 指數迴歸：預計 Y (列)

已知 x 值 (metric_X)，計算預計 y 值 (metric_Y)，根據  ) 使用「最小平方」方法計算最佳配適線。

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## Cdf-T

傳回值在 Student 的 t 分布中的百分比，其中自由度為 n，z 分數小於 x。

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

傳回值在常態分布中的百分比，其中 z 分數小於 x。

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## 上限 (列)

傳回不小於給定值的最小整數。例如，如果您不想報表中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 CEILING(*Revenue*) 可將收入無條件進位至最接近的美金 $570。

```
CEILING(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要四捨五入的量度。 |

## 餘弦 (列)

傳回指定角度的餘弦。如果角度是以度表示，請將角度乘以 PI( )/180。

```
COS(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其餘弦的角度，單位為弧度。 |

## 立方根

傳回數字的正立方根。數字的立方根是該數字的 1/3 乘冪值。

```
CBRT(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要取立方根的量度。 |

## 累積

傳回最後N列的x總和（依維度排序，使用字串型欄位的雜湊值）。

如果N &lt;= 0，則使用所有先前的行。 由於依維度排序，因此只適用於日期或路徑長度等自然順序的維度。

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## 累積平均值

傳回最後N列的平均值。

如果N &lt;= 0，則使用所有先前的行。 由於依維度排序，因此只適用於日期或路徑長度等自然順序的維度。

>[!NOTE] 如果您想使用收入/訪客之類的比率量度，則此函數不適用，因為此函數會平均比率，而非將過去 N 期的收入相加、將過去 N 期的訪客數相加，然後再將兩者相除。請改為使用

```
cumul(revenue)/cumul(visitor)
```

## 等於

傳回完全符合數值或字串值的項目。

## 指數迴歸_ 相關係數 (表格)

針對迴歸方程式，傳回兩個量度欄 (*metric_A* 和 *metric_B*) 之間的相關係數 *r*。

```
CORREL.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 指數迴歸：截距 (表格)

針對以下迴歸方程式，傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間的截距 *b*

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 指數迴歸：斜率 (表格)

針對以下迴歸方程式，傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間的斜率 *a*。

```
SLOPE.EXP(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 下限 (列)

傳回不大於給定值的最大整數。例如，如果您不想報表中的收入出現貨幣小數位數，而有個產品是 $569.34，則使用公式 FLOOR(*Revenue*) 可將收入無條件捨去至最接近的美金 $569。

```
FLOOR(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您要四捨五入的量度。 |

## 大於

傳回數值計數大於輸入值的項目。

## 大於或等於

傳回數值計數大於或等於輸入值的項目。

## 雙曲餘弦 (列)

傳回數字的雙曲餘弦。

```
COSH(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其雙曲餘弦的角度，單位為弧度。 |

## 雙曲正弦 (列)

傳回數字的雙曲正弦。

```
SINH(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其雙曲正弦的角度，單位為弧度。 |

## 雙曲正切 (列)

傳回數字的雙曲正切。

```
TANH(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要尋找雙曲正切的角度（以弧度為單位）。 |

## IF (列)

如果指定的條件評估為TRUE，則IF函式返回一個值；如果該條件評估為FALSE，則返回另一個值。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 引數 | 說明 |
|---|---|
| *logical_test* | 必要。任何可被評估為 TRUE 或 FALSE 的值或運算式。 |
| *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.) |
| *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.) |

## 小於

傳回數值計數小於輸入值的項目。

## 小於或等於

傳回數值計數小於或等於輸入值的項目。

## 線性迴歸_ 相關係數

Y = a X + b。傳回相關係數

## 線性迴歸_ 截距

Y = a X + b。傳回 b。

## 指數迴歸_ 預計 Y

Y = a X + b。傳回 Y。

## 線性迴歸_ 斜率

Y = a X + b。傳回 a。

## 以 10 為底的對數 (列)

傳回數字以 10 為底的對數。

```
LOG10(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其底數 10 對數的正實數。 |

## 對數迴歸：相關係數 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，迴歸方程式 *的相關係數* r[!DNL Y = a ln(X) + b]。會使用 CORREL 方程式進行計算。

```
CORREL.LOG(metric_X,metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 對數迴歸：截距 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，迴歸方程式 *的截距* b[!DNL Y = a ln(X) + b] 做為最小平方迴歸。會使用 INTERCEPT 方程式進行計算。

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 對數迴歸：預計 Y (列)

已知 [!DNL y] 值 (me ric_X)，計算預計 [!DNL x] 值 (metric_Y)，根據 [!DNL Y = a ln(X) + b] 使用「最小平方」方法計算最佳配適線。會使用 ESTIMATE 方程式進行計算。

在迴歸分析中，已知 [!DNL y] 值 (*metric_X*)，此函數會計算預計 [!DNL x] 值 (*metric_Y*)，使用對數計算迴歸方程式 [!DNL Y = a ln(X) + b] 的最佳配適線。[!DNL a] 值對應到每個 x 值，而 [!DNL b] 是常數值。

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 對數迴歸：斜率 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，迴歸方程式 *的斜率* a[!DNL Y = a ln(X) + b]。會使用 SLOPE 方程式進行計算。

```
SLOPE.LOG(metric_A, metric_B)
```

| 引數 | 說明 |
|---|---|
| *metric_A* | 您想要指定為相依資料的量度。 |
| *metric_B* | 您想要指定為獨立資料的量度。 |

## 自然對數

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其自然對數的正實數。 |

## NOT

如果數字為0，則返回1；如果其他數字為0，則返回0。

```
NOT(logical)
```

| 引數 | 說明 |
|---|---|
| *邏輯* | 必要。可被評估為 TRUE 或 FALSE 的值或運算式。 |

使用NOT需要知道運算式（&lt;、>、=、&lt;>等）傳回0或1個值。

## 不等於

傳回所有不含輸入值的項目。

## 或 (列)

如果任何引數為 TRUE 則傳回 TRUE，若所有引數為 FALSE 則傳回 FALSE。

>[!NOTE] 0 (零) 表示 False，其他值表示 True。

```
OR(logical_test1,[logical_test2],...)
```

| 引數 | 說明 |
|---|---|
| *logical_test1* | 必要。任何可被評估為 TRUE 或 FALSE 的值或運算式。 |
| *logical_test2* | 選填。您要評估為TRUE或FALSE的其他條件 |

## Pi

傳回常數 PI 3.14159265358979，精確至小數點第 15 位。

```
PI()
```

[!DNL PI] 函數沒有引數。

## 乘冪迴歸：相關係數 (表格)

針對 [!DNL Y = b*X]，傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間的相關係數 *r*。

```
CORREL.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 乘冪迴歸：截距 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，*的截距* b[!DNL Y = b*X]。

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 乘冪迴歸：預計 Y (列)

已知 [!DNL x] 值 ([!DNL metric_X])，計算預測 [!DNL y] 值 ([!DNL metric_Y])，使用「最小平方」方法計算 [!DNL Y = b*X] 的最佳配適線。

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 乘冪迴歸：斜率 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，*) 的斜率* a[!DNL Y = b*X]。

```
SLOPE.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 二次迴歸：相關係數 (表格)

針對 [!DNL Y=(a*X+b)]****，傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間的相關係數 *r*。

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 二次迴歸：截距 (表格)

針對 [!DNL Y=(a*X+b)]****，傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間的截距 *b*。

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 二次迴歸：預計 Y (列)

已知 [!DNL y] 值 (metric_X)，計算預測 [!DNL x] 值 (metric_Y)，使用最小平方方法計算使用 [!DNL Y=(a*X+b)] 的最佳配適線。

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| 引數 | 說明 |
|---|---|
| *metric_A* | 您想要指定為相依資料的量度。 |
| *metric_B* | 您想要指定為相依資料的量度。 |

## 二次迴歸：斜率 (表格)

針對 [!DNL Y=(a*X+b)]****，傳回兩個量度欄 (*metric_X* 和 metric_Y) 之間的斜率 *a*。

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 倒數迴歸：相關係數 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，*的相關係數* r[!DNL Y = a/X+b]。

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## 倒數迴歸：截距 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，*的截距* b[!DNL Y = a/X+b]。

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 倒數迴歸：預計 Y (列)

已知 [!DNL y] 值 (metric_X)，計算預計 [!DNL x] 值 (metric_Y)，使用最小平方方法計算使用 [!DNL Y = a/X+b] 的最佳配適線。

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 倒數迴歸：斜率 (表格)

傳回兩個量度欄 (*metric_X* 和 *metric_Y*) 之間，*) 的斜率* a[!DNL Y = a/X+b]。

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| 引數 | 說明 |
|---|---|
| *metric_X* | 您想要指定為相依資料的量度。 |
| *metric_Y* | 您想要指定為獨立資料的量度。 |

## 正弦 (列)

傳回指定角度的正弦。如果角度是以度表示，請將角度乘以 PI( )/180。

```
SIN(metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其正弦的角度，單位為弧度。 |

## T 分數

Z 分數的別名，即平均值偏差除以標準差

## T 檢定

執行 m 尾 t 檢定，使用 col 的 t 分數和 n 自由度。

簽名是 `t_test( x, n, m )`。底下其只呼叫了 `m*cdf_t(-abs(x),n)`。(這與 z 檢定函數執行 `m*cdf_z(-abs(x))` ) 類似)。

在此，`m` 是反面的數目，而 `n` 是自由度。這些應該為數字 (在整個報表中為常數，例如，不會逐列變更)。

`X` 是 t 檢定的統計資料，且經常會是基於量度的公式 (例如 zscore)，並在每列進行評估。

返回值是在給定自由度和尾數的情況下查看測試統計數x的概率。

**範例：**

1. 用其找出極端值：

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. 將其與 `if` 合併，以便忽略非常高或非常低的反彈率，然後統計其他項目上的造訪率：

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## 正切

傳回指定角度的正切。如果角度是以度表示，請將角度乘以 PI( )/180。

```
TAN (metric)
```

| 引數 | 說明 |
|---|---|
| *量度* | 您想要找到其正切的角度，單位為弧度。 |

## Z 分數 (列)

傳回Z分數（或一般分數），以常態分佈為基礎。 Z分數是觀察與平均值之間的標準差數。 Z分數為0（零）表示分數與平均值相同。 Z分數可以是正數或負數，指出其高於或低於平均值，以及標準差的多少。

Z 分數的方程式為：

![](assets/z_score.png)

其中 [!DNL x] 是原始分數、[!DNL μ] 是族群平均值，[!DNL σ] 是族群標準差。

>[!NOTE][!DNL μ]  (mu) 和 [!DNL σ] (sigma) 會自動從量度中計算得出。

Z 分數 (量度)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 引數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>量度</i> </td> 
   <td colname="col2"> <p> 傳回其第一個非零引數的值。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z 檢定

執行A的Z分數為n尾的Z測試。

傳回在欄中偶然看到目前列的可能性。

>[!NOTE] 此處假設值為常態分布。

