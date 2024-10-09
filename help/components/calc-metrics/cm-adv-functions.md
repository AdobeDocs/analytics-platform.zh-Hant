---
title: 進階函數
description: 勾選函數下拉式清單中的顯示進階即可存取這些函數。
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: e355194d6699128ac817ea564940c0afdea61efc
workflow-type: tm+mt
source-wordcount: '3126'
ht-degree: 20%

---

# 進階函數

[計算量度產生器](cm-workflow/cm-build-metrics.md)可讓您套用統計和數學函式。 本文記錄進階函式及其定義的字母順序清單。

在[元件]面板中選取![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 函式]**&#x200B;清單下的&#x200B;**[!UICONTROL 顯示全部]**，以存取這些函式。 向下捲動以檢視&#x200B;**[!UICONTROL 進階函式]**&#x200B;的清單。

## 表格函式和列函式

表格函數是表格每一列的輸出都相同。列函數則是表格每一列的輸出都不同。

在適用和相關的情況下，函式會以函式型別註釋： [!BADGE 表格]{type="Neutral"}[!BADGE 列]{type="Neutral"}

## 「包含零」引數的意義是什麼？

此參數指出是否在計算中包括零。有時零表示&#x200B;*無*，但有時很重要。

例如，如果您有收入量度，然後新增頁面檢視量度至報表，您的收入會突然有更多的列，而且全都是零。 您可能不想讓額外的量度影響任何&#x200B;**[MEAN](cm-functions.md#mean)**、**[ROW MINIMUM](cm-functions.md#row-min)**、**[QUARTILE](cm-functions.md#quartile)**&#x200B;以及您在收入欄中擁有的其他計算。 在此情況下，您需要檢查`include-zeros`引數。

另一種情況是，您有兩個相關量度，且其中一個的平均值或最小值較高，因為有些列是零。  在這種情況下，您可以選擇不檢查引數以包含零。


## 和

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**


結合。 不等於零則視為true，等於零則視為false。 輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| logical_test | 至少需要一個引數，但可採用任意數量的引數。 任何可評估為TRUE或FALSE的值或運算式 |

## 近似計數相異

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 近似的相異計數（維度）]**


針對選取的維度，傳回維度項目的近似相異計數。


| 引數 | 說明 |
|---|---|
| 維度 | 您要計算近似相異專案計數的維度 |

### 範例

此函式的常見使用案例是當您想要取得大致數量的客戶時。




## 反餘弦

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 反餘弦（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您要從–1到1的角度的餘弦 |



## 反正弦

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 反正弦（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您要從–1到1的角度的正弦 |



## 反正切

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 反正切（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您要從–1到1的角度的正切 |



## Cdf-T

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T（量度，數字）]**


傳回自由度為n的學生t分佈中，隨機變數的z分數小於col的機率。


| 引數 | 說明 |
|---|---|
| 量度 | 您想要Student t-distribution的累積分佈函式的量度 |
| 數字 | 學生t分佈的累積分佈函式的自由度 |

### 範例

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z（量度，數字）]**


傳回常態分佈之隨機變數的z分數小於col的機率。


| 引數 | 說明 |
|---|---|
| 量度 | 您要使用標準常態分佈的累積分佈函式的量度 |

### 範例

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## 上限

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 上限（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您要舍入的量度 |


## 信賴度 (下限)

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 信賴度(normalizing-container， success-metric， control， implementation-treshold)]**

使用WASKR方法計算隨時有效的信賴度&#x200B;**下限**，如[時間統一中心限制理論和漸近信賴序列](https://arxiv.org/pdf/2103.06476)中所述。

信賴度指有多少證據顯示指定變體與控制變體相同的機率測度。 信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。

| 引數 | 說明 |
| --- | --- |
| normalizing-container | 執行測試的基礎（人員、工作階段或事件）。 |
| success-metric | 使用者用來比較變體的一個或多個量度。 |
| 控制 | 和實驗中所有其他變體進行比較的變體。輸入控制變體維度項目的名稱。 |
| 顯著性臨界值 | 此函數中的臨界值設定為預設值 95%。 |

## 信賴度 (上限)

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 信賴度(normalizing-container， success-metric， control， implementation-treshold)]**

使用WASKR方法計算隨時有效的信賴度&#x200B;**上限**，如[時間統一中心限制理論和漸近信賴序列](https://arxiv.org/pdf/2103.06476)中所述。

信賴度指有多少證據顯示指定變體與控制變體相同的機率測度。 信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。

| 引數 | 說明 |
| --- | --- |
| normalizing-container | 執行測試的基礎（人員、工作階段或事件）。 |
| success-metric | 使用者用來比較變體的一個或多個量度。 |
| 控制 | 和實驗中所有其他變體進行比較的變體。輸入控制變體維度項目的名稱。 |
| 顯著性臨界值 | 此函數中的臨界值設定為預設值 95%。 |


## 餘弦

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 餘弦（量度）]**

[!BADGE 列]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您想要餘弦的角度（弧度） |


## 立方根

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE根（量度）]**


傳回數字的正立方根。數字的立方根是該數字的 1/3 乘冪值。


| 引數 | 說明 |
|---|---|
| 量度 | 您要計算立方結構根的量度 |



## 累積

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 累積（數字，量度）]**

傳回x欄最後n個元素的總和。如果n > 0，則會加總最後n個元素或x。如果n &lt; 0，則加總前面的元素。

| 引數 | 說明 |
| --- | --- |
| 數字 | 要傳回總和的最後N列數。 如果N &lt;= 0，則使用所有先前的列。 |
| 量度 | 您要求累積總和的量度。 |

### 範例

| 日期 | 收入 | 累積（0，收入） | 累積（2，收入） |
|------|------:|--------------:|--------------:|
| 5 月 | $500 | $500 | $500 |
| 6 月 | 200美元 | $700 | $700 |
| 7 月 | $400 | $1100 | $600 |


## 累積（平均）

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 累積平均值（數字，量度）]**

傳回欄x最後n個元素的平均值。如果n > 0，則會加總最後n個元素或x。如果n &lt; 0，則加總前面的元素。

| 引數 | 說明 |
| --- | --- |
| 數字 | 要傳回平均值的最後N列數。 如果N &lt;= 0，則使用所有先前的列。 |
| 量度 | 您希望求累積平均值的量度。 |

>[!NOTE]
>
>此函式不適用於比率量度，例如每人收入。 此函式計算比率的平均值，而非將過去N期的收入相加、將過去N期的人員相加，然後再將兩者相除。 <br/>請改用[**[!UICONTROL 累積（收入）]**](#cumulative) ![除](/help/assets/icons/Divide.svg) [**[!UICONTROL 累積（人員）]**](#cumulative)。
>


## 等於

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**


等於。 輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| metric_X | |
| metric_Y | |

### 範例

`Metric 1 = Metric 2`



## 指數回歸：相關係數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數回歸：相關係數(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要與metric_Y建立關聯的量度 |
| metric_Y | 您要與metric_X建立關聯的量度 |
| include_zeros | 是否在計算中包含零值 |

## 指數回歸：預計Y

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數回歸：預計Y(metric_X， metric_Y， include_zeros)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為獨立資料的量度。 |
| metric_Y | 您要指定為相依資料的量度。 |
| include_zeros | 是否在計算中包含零值 |


## 指數回歸：截距

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數回歸：截距(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## 指數回歸：斜率

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數回歸：斜率(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## Floor

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X， metric_Y， include_zeros)]**

[!BADGE 列]{type="Neutral"}

| 引數 | 說明 |
|---|---|
| 量度 | 您要四捨五入的量度。 |


## 大於

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 大於()]**


輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| metric_X | |
| metric_Y | |

### 範例

`Metric 1 > Metric 2`

## 大於或等於

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 大於或等於()]**


大於或等於。 輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| metric_X |  |
| metric_Y |  |

### 範例

`Metric 1 >= Metric 2`



## 雙曲餘弦

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 雙曲餘弦（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您要尋找雙曲餘弦的角度（弧度） |



## 雙曲正弦

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 雙曲正弦（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您想要尋找雙曲正弦的角度（弧度） |



## 雙曲正切

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 雙曲正切（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您要尋找其雙曲正切的角度（弧度） |


## 若  

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test， value_if_true， value_if_false)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| logical_test | 必填。任何可評估為TRUE或FALSE的值或運算式 |
| value_if_true | logical_test引數評估為TRUE時要傳回的值。 (若未指定則此引數預設為 0。) |
| value_if_false | 如果 logical_test 引數評估為 FALSE 時您想要傳回的值。(若不含，則此引數預設值為 0。) |


## 小於

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 小於()]**


輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| metric_X | |
| metric_Y | |


### 範例

`Metric 1 < Metric 2`

## 小於或等於

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 小於或等於()]**

小於或等於。 輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| metric_X | |
| metric_Y | |

### 範例

`Metric 1 <= Metric 2`



## 線性回歸：相關係數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 線性回歸：相關係數(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要與metric_Y建立關聯的量度 |
| metric_Y | 您要與metric_X建立關聯的量度 |
| include_zeros | 是否在計算中包含零值 |



## 線性回歸：截距

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 線性回歸：截距(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 線性回歸：預計Y

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 線性回歸：預計Y(metric_X， metric_Y， include_zeros)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 線性回歸：斜率

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 線性回歸：斜率(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## 以10為底的對數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 以10為基數的記錄檔（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您希望以10為底的對數的正實數 |


## 對數回歸：相關係數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 對數回歸：相關係數(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要與metric_Y建立關聯的量度 |
| metric_Y | 您要與metric_X建立關聯的量度 |
| include_zeros | 是否在計算中包含零值 |


## 對數回歸：截距

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 對數回歸：截距(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 對數回歸：預計Y

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 對數回歸：預計Y(metric_X， metric_Y， include_zeros)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 對數回歸：斜率

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 對數回歸：斜率(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 自然對數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 自然對數（量度）]**


傳回數字的自然對數。自然對數是以常數 e (2.71828182845904) 為底數。LN 是 EXP 函數的反函數。


| 引數 | 說明 |
|---|---|
| 量度 | 您希望自然對數的正實數 |



## Not

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL NOT（邏輯）]**


否定是一種布林值。 輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| 邏輯 | 必填。可評估為TRUE或FALSE的值或運算式 |



## 不等於

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 不等於()]**


不等於。 輸出為0 (false)或1 (true)。


| 引數 | 說明 |
|---|---|
| metric_X | |
| metric_Y | |

### 範例

`Metric 1 != Metric 2`


## 或

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| logical_test | 至少需要一個引數，但可採用任意數量的引數。 任何可評估為TRUE或FALSE的值或運算式 |


>[!NOTE]
>
>0 (零) 表示 False，其他值表示 True。


## Pi

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

傳回 Pi：3.14159...


## 乘冪回歸：相關係數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘冪回歸：相關係數(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要與metric_Y建立關聯的量度 |
| metric_Y | 您要與metric_X建立關聯的量度 |
| include_zeros | 是否在計算中包含零值 |



## 乘冪回歸：截距

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘冪回歸：截距(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## 乘冪回歸：預計Y

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘冪回歸：預計Y(metric_X， metric_Y， include_zeros)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 乘冪回歸：斜率

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘冪回歸：斜率(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 二次回歸：相關係數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回歸：相關係數(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要與metric_Y建立關聯的量度 |
| metric_Y | 您要與metric_X建立關聯的量度 |
| include_zeros | 是否在計算中包含零值 |

## 二次回歸：截距

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回歸：截距(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## 二次回歸：預計Y

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回歸：預計Y(metric_X， metric_Y， include_zeros)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |

## 二次回歸：斜率

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 二次回歸：斜率(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |



## 倒數回歸：相關係數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 倒數回歸：相關係數(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要與metric_Y建立關聯的量度 |
| metric_Y | 您要與metric_X建立關聯的量度 |
| include_zeros | 是否在計算中包含零值 |


## 倒數回歸：截距

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 倒數回歸：截距(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## 倒數回歸：預計Y

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 倒數回歸：預計Y(metric_X， metric_Y， include_zeros)]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |


## 倒數回歸：斜率

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 倒數回歸：斜率(metric_X， metric_Y， include_zeros)]**


[!BADGE 表格]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| metric_X | 您要指定為相依資料的量度 |
| metric_Y | 您要指定為獨立資料的量度 |
| include_zeros | 是否在計算中包含零值 |




## 正弦

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL SINE（量度）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您想要正弦值的角度（弧度） |




## T 分數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE（公制，包含_零）]**


[MEAN](cm-functions.md#mean)的偏差除以標準差。 [Z分數](#z-score)的別名。


| 引數 | 說明 |
|---|---|
| 量度 | 您想要T分數的量度 |
| include_zeros | 是否在計算中包含零值 |


## T 檢定

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL T檢定（公制、度、尾）]**


執行m尾t檢定，x為t分數，n為自由度。


| 引數 | 說明 |
|---|---|
| 量度 | 您要對其執行T測試的量度 |
| 度 | 自由度 |
| 尾部 | 用於執行T測試的尾部長度 |

### 詳細資料

簽章是T-TEST（公制、度、尾）。 在下面，它只會呼叫&#x200B;***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**。 此函式類似於&#x200B;**[Z-TEST](#z-test)**&#x200B;函式，它執行&#x200B;***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**。

- ***m***&#x200B;是尾數。
- ***n***&#x200B;是自由度，並且應該在整個報告中為常數數字，也就是說，不會逐列變更。
- ***x***&#x200B;是T檢定的統計資料，且經常會是基於量度的公式（例如&#x200B;**[Z-SCORE](#z-score)**），並在每列進行評估。

傳回值是在給定自由度和反面的數目下，出現檢定統計資料 x 的機率。

**範例：**

1. 使用函式來尋找離群值：

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. 結合函式與&#x200B;**[IF](#if)**&#x200B;以忽略非常高或非常低的反彈率，然後統計其他專案的工作階段：

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```




## 正切

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 正切（量度）]**


傳回給定角度的正切。如果角度是以度表示，請將角度乘以 PI( )/180。


| 引數 | 說明 |
|---|---|
| 量度 | 您想要切線的角度（弧度） |



## Z分數

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE（公制，包含_零）]**


[!BADGE 列]{type="Neutral"}


| 引數 | 說明 |
|---|---|
| 量度 | 您想要Z分數的量度 |
| include_zeros | 是否在計算中包含零值 |

Z分數為0 （零）表示分數與平均值相同。 Z 分數可為正或負，代表其高於或低於平均值多少標準差。

Z 分數的方程式為：

![](assets/z_score.png)

其中&#x200B;***[!DNL x]***&#x200B;是原始分數，***[!DNL μ]***&#x200B;是母體的平均值，***[!DNL σ]***&#x200B;是母體的標準差。

>[!NOTE]
>
>***[!DNL μ]*** (mu)和&#x200B;***[!DNL σ]*** (sigma)會自動從量度中計算得出。



## Z 檢定

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**


執行n尾z檢定，z分數為x。


| 引數 | 說明 |
|---|---|
| 量度 | 您要對其執行Z測試的量度 |
| 尾部 | 用於執行Z測試的尾部長度 |

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