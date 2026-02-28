---
title: 基本函數
description: 了解基本計算量度函數。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 211f0411d0bf70288cbd46bb219fce7ae99fe03d
workflow-type: tm+mt
source-wordcount: '3599'
ht-degree: 48%

---

# 基本函數


使用[計算量度產生器](cm-workflow/cm-build-metrics.md)可套用統計和數學函數。本文記錄了函數及其定義的清單，依字母順序排列。

>[!NOTE]
>
>此處將 [!DNL metric] 視為函數中的引數，也允許使用其他的量度運算式。例如，[COLUMN MAXIMUM(metrics)](#column-maximum)也允許[COLUMN MAXIMUM(PageViews + Sessions)](#column-maximum)。



## 表格函數和列函數的比較

表格函式是每個表格列的輸出都相同的函式。 列函式是表格每一列的輸出都不同的函式。

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

[!BADGE 列]{type="Neutral"}傳回數字的絕對值。數字的絕對值是正值的數字。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其絕對值的量度。 |

**使用案例**：分析可能產生負值的量度（例如收入增量或百分比變更）時，請確定所有結果均為正數。 這有助於在不考慮方向的情況下聚焦於變更的幅度。

**在計算量度產生器中**：將您的量度或運算式包裝在&#x200B;**絕對值**&#x200B;函式中，例如： **絕對值**（目前收入 — 先前的收入）。 這會將任何負值差異轉換為正值。

>[!TIP]
>
>使用此選項來測量兩個時段或區段之間的絕對差異，無論效能是增加還是減少。
>

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

**使用案例**：識別劃分中的最高值，例如造訪次數最多的當天或收入最高的產品。 這有助於突顯不同類別的高峰效能。

**在計算量度產生器**&#x200B;中：依&#x200B;**天**&#x200B;或&#x200B;*產品*&#x200B;劃分時，將&#x200B;*欄最大值*&#x200B;套用至&#x200B;*收入*&#x200B;或&#x200B;*工作階段*&#x200B;之類的量度。 此函式會傳回該欄中每一列的最大值。

>[!TIP]
>
>使用[IF](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)陳述式(例如&#x200B;**IF**(*Revenue* = **欄最大值***(Revenue*)， 1， 0))來反白劃分中表現最好的專案。
>

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

**使用案例**：識別劃分中績效最低的值，例如轉換最少的行銷活動或收入最低的日子。 這有助於快速顯示表現缺佳的區段。

**在計算量度產生器**&#x200B;中：按&#x200B;**行銷活動**&#x200B;或&#x200B;*天*&#x200B;劃分時，將&#x200B;*欄最小值*&#x200B;套用至&#x200B;*收入*&#x200B;或&#x200B;*轉換率*&#x200B;之類的量度。 此函式傳回該欄中每一列的最小值。

>[!TIP]
>
>使用[IF](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)陳述式(例如&#x200B;**IF**(*Revenue* = **欄最小值***(Revenue*)， 1， 0))來反白劃分中表現最低的專案。
>


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

**使用案例**：計算劃分中所有值的總計，例如所有產品的總收入或所有天的總造訪次數。 當您需要整體總計來與個別列值比較時，這項功能會有所幫助。

**在計算量度產生器**&#x200B;中：將&#x200B;**欄總和**&#x200B;套用至&#x200B;*收入*&#x200B;或&#x200B;*工作階段*&#x200B;之類的量度，同時依&#x200B;*產品*&#x200B;或&#x200B;*天*&#x200B;劃分。 此函式傳回該欄中每一列所有值的總和。

>[!TIP]
>
>當您需要整體總計的參考以計算共用或總效能的百分比時使用。
>


## 計數 {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="計數"
>abstract="傳回一欄中量度的數目、計數或非零數值 (在一個維度中報告的唯一元素數目)。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 計數 (量度)]**

[!BADGE 表格]{type="Neutral"}傳回欄中量度的數目、計數或非零數值 (在一個維度中報告的唯一元素數目)。

| 引數 | 說明 |
|---|---|
| 量度 | 您想計數的量度。 |

**使用案例**：計算計算中包含的資料點數目，例如日期範圍內的天數或劃分中的產品數目。 當您需要知道有多少專案產生彙總值時，這項功能會有所幫助。

**在計算量度產生器中**：套用&#x200B;**計數**&#x200B;至類似&#x200B;*工作階段*&#x200B;或&#x200B;*收入*&#x200B;之類的量度，以傳回目前劃分或日期範圍中包含的列總數（或資料點）。

>[!TIP]
>
>與&#x200B;**欄總和**&#x200B;搭配使用，以手動計算平均值(例如&#x200B;**欄總和**（*收入*） / **計數** （收入）)。
>

## 指數 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="指數"
>abstract="傳回 e 的指定數字的次方。常數 e 是自然對數的底數，等於 2.71828182845904。EXPONENT 是 LN (一個數字的自然對數) 的反函數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指數 (量度)]**

[!BADGE 列]{type="Neutral"}傳回&#x200B;*e*，提升到指定數字的乘冪。 常數 *e* 是自然對數的底數，等於 2.71828182845904。EXPONENT 是 LN (一個數字的自然對數) 的反函數。

| 引數 | 說明 |
|---|---|
| 量度 | 套用至基底&#x200B;*e*&#x200B;的指數。 |

**使用案例**：將&#x200B;*e*&#x200B;提升至指定數字或量度的冪。 當建立成長趨勢模型或擴充量度至指數級時，這項功能相當實用。

**在計算量度產生器**&#x200B;中：使用&#x200B;**指數**&#x200B;與量度。 例如： **指數**（*工作階段*）將&#x200B;*e*&#x200B;提升至&#x200B;*工作階段*&#x200B;量度的冪。

>[!TIP]
>
>結合使用&#x200B;**對數**&#x200B;以建立進階模型，或在比較成長模式時平滑處理高度變數的資料。
>


## 平均值 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="平均值"
>abstract="傳回一欄中量度的算術平均數或平均值"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 平均值 (量度，include_zeros)]**

[!BADGE 表格]{type="Neutral"}傳回欄中量度的算術平均數或平均值。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其平均值的量度。 |
| 包括零 | 計算中是否包括零值。 |

**使用案例**：計算一組值的算術平均值，例如平均每日收入或每個行銷活動的平均造訪次數。 這有助於建立比較資料集中個別值的基準。

**在計算量度產生器中**：套用&#x200B;**平均值**&#x200B;至類似&#x200B;*收入*&#x200B;或&#x200B;*工作階段*&#x200B;的量度，以傳回所選劃分或日期範圍內所有資料點的平均值。

>[!TIP]
>
>用於瞭解整體效能趨勢，或將其與&#x200B;**標準差**&#x200B;結合，以測量平均值的一致性。
>

## 中位數 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="中位數"
>abstract="傳回一欄中量度的中位數。中位數是一組數字中位於中間的數字。意即，有一半的數字其值大於或等於中位數，另有一半的值小於或等於中位數。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 中位數 (量度，include_zeros)]**

[!BADGE 表格]{type="Neutral"}傳回欄中量度的中位數。中位數是一組數字中位於中間的數字。意即，有一半的數字其值大於或等於中位數，另有一半的值小於或等於中位數。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其中間值的量度。 |
| 包括零 | 計算中是否包括零值。 |

**使用案例**：識別一組資料中的中間值，例如每日收入中位數或每次造訪頁面檢視中位數。 如果您想要減少離群值的影響並檢視資料的核心趨勢，這項功能會很好用。

**在計算量度產生器中**：套用中位數至收入或頁面檢視之類的量度，以傳回所選劃分或日期範圍內所有資料點的中點值。

>[!TIP]
>
>當您的資料包含極高或極低，可能會扭曲平均值時，請改用&#x200B;**平均值**。
>


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

**使用案例**：將數字除以另一個數字後傳回餘數。 這對於循環或重複模式很有用，例如依序識別第n天或行銷活動。

**在計算量度產生器**&#x200B;中：使用具有兩個數值輸入的&#x200B;**模數**。 例如： **模數**（*日數*， 7）會傳回將日數除以七後的餘數，這有助於將資料按周分組。

>[!TIP]
>
>與條件邏輯結合，以反白顯示循環間隔或根據重複週期分段資料。
>

### 更多範例

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


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 百分位數 (量度，k，include_zeros)]**

[!BADGE 表格]{type="Neutral"}傳回第 n 個百分位數，該值介於 0 至 100 之間。當 n &lt; 0 時，則函數使用零。當 n > 100 時，函數傳回 100。

| 引數 | 說明 |
|---|---|
| 量度 | 0 至 100 (含) 範圍內的百分位數值。 |
| k | 定義相對位置的量度欄。 |
| 包括零 | 計算中是否包括零值。 |

**使用案例**：識別指定的資料點百分比低於的值，例如每日收入或頁面檢視的第90個百分位數。 這有助於測量分佈並偵測高績效的離群值。

**在計算量度產生器**&#x200B;中：將&#x200B;**百分位數**&#x200B;套用至&#x200B;*收入*&#x200B;或&#x200B;*工作階段*&#x200B;之類的量度，並指定所需的百分位數值(例如，**百分位數**（*收入*， 90）)。 結果顯示90%的資料點低於臨界值。

>[!TIP]
>
>用來設定效能基準，或篩選表現最好的日子、行銷活動或產品。
>

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

**使用案例**：將一個數字或量度提升為另一個數字或量度的冪，例如平方值或套用指數權重。 在建模成長、縮放值或執行進階數學轉換時，這很有幫助。

**在計算量度產生器**&#x200B;中：在兩個數值或量度之間使用&#x200B;**乘冪運運算元**。 例如： *Revenue* ^ 2會將&#x200B;*Revenue*&#x200B;值提高到次冪。

>[!TIP]
>
>類似於&#x200B;**指數**&#x200B;函式，但以數學運運算元表示，可在計算量度內使用更精簡的公式。
>

## 四分位數 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="四分位數"
>abstract="傳回量度的數值四分位數。例如，四分位數可用於尋找創造最多營收的前 25% 產品。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 四分位數 (量度，四分位數，include_zeros)]**

[!BADGE 表格]{type="Neutral"}傳回量度值的四分位數。例如，四分位數可用來尋找推動最高收入的前 25% 產品。當四分位數分別等於 `0` (零)、`2` 和 `4` 時，[欄最小值](#column-minimum)、[中間值](#median)和[欄最大值](#column-maximum)傳回與[四分位數](#quartile)相同的值。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其四分位數值的量度。 |
| 四分位數 | 指出要傳回哪個四分位數值。 |
| 包括零 | 計算中是否包括零值。 |

**使用案例**：將資料集分成四個相等的部分，以瞭解值的分配方式，例如依收入或造訪識別前25%的天數。 這有助於將效能劃分到排名群組中，以便進行更深入的比較。

**在計算量度產生器中**：套用&#x200B;**Quartile**&#x200B;至類似&#x200B;*收入*&#x200B;或&#x200B;*工作階段*&#x200B;的量度，並指定要傳回的四分位數(例如，**Quartile**（*收入*， 3）以尋找第三個四分位數或前25%的臨界值)。

>[!TIP]
>
>使用將值分組為績效層級，例如低、中和高績效的行銷活動或產品。
>

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

**使用案例**：將數值結果四捨五入為指定的小數位數，藉此簡化數值結果。 這項更新有助於建立更清晰的視覺效果，或是讓計算量度更易於在報表中讀取。

**在計算量度產生器**&#x200B;中：將&#x200B;**Round**&#x200B;套用至量度或運算式，並指定小數位數。 例如： **Round**（*轉換率*， 2）會將值四捨五入為兩位小數。

>[!TIP]
>
>用來標準化各報表的量度格式，尤其是在顯示百分比或貨幣值時。
>

### 更多範例

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

**使用案例**：計算劃分或資料集中傳回的總列數，例如包含在報告中的天數、行銷活動或產品。 這有助於瞭解有多少專案對您的分析有貢獻。

**在計算量度產生器中**：套用&#x200B;**資料列計數**&#x200B;以傳回目前劃分或區段中的資料列總數。 例如，當依&#x200B;*產品*&#x200B;檢視&#x200B;*收入*&#x200B;時，**資料列計數**&#x200B;會傳回顯示的產品數目。

>[!TIP]
>
>搭配其他函式（例如&#x200B;**欄總和**）以手動方式計算平均值(例如&#x200B;**欄總和**（*收入*） / **列計數**())。
>

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

**使用案例**：識別單一列中所有量度的最大值，例如判斷哪個量度（例如，*收入*、*訂單*&#x200B;或&#x200B;*工作階段*）在特定日期或區段具有最大值。 這有助於反白顯示每列資料中哪些量度有銷售機會。

**在計算量度產生器中**：當計算量度中包含多個量度時，套用&#x200B;**列最大值**。 例如： **資料列最大值**（*收入*，*訂單*，*工作階段*）會傳回每個資料列這些量度中的最大值。

>[!TIP]
>
>可用來並排比較相關量度，找出對每一列效能貢獻最大的專案。
>

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

**使用案例**：識別單一列中所有量度的最小值，例如找出哪個量度（例如，*收入*、*訂單*&#x200B;或&#x200B;*工作階段*）在特定日期或區段具有最小值。 這有助於找出每列資料中表現最差的量度。

**在計算量度產生器**&#x200B;中：比較多個量度時套用&#x200B;**列最小值**。 例如： **資料列最小值**（*收入*，*訂單*，*工作階段*）會傳回每一資料列這些量度中的最小值。

>[!TIP]
>
>與「列最大值」結合，以計算效能範圍，或強調並排比較中表現缺佳的量度。
>

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

**使用案例**：將單一資料列中多個量度的值加總，例如加總&#x200B;*Revenue*&#x200B;和&#x200B;*Tax*&#x200B;以計算總交易值，或結合來自不同來源的&#x200B;*工作階段*。 這有助於將相關的量度整合為總計。

**在計算量度產生器**&#x200B;中：套用&#x200B;**列總和**&#x200B;以合併多個量度。 例如： **資料列總和**(*Revenue*， *Tax*)將這兩個量度加到劃分中的每一資料列。

>[!TIP]
>
>用來建立合併總計，或將相關的績效指標群組至單一計算量度。
>

## 平方根 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="平方根"
>abstract="傳回數字的正平方根。數字的平方根是該數字的 1/2 次方。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根 (量度，include_zeros)]**

[!BADGE 列]{type="Neutral"}傳回數字的正平方根。數字的平方根是該數字的 1/2 次方。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其平方根的量度。 |

**使用案例**：傳回數字或量度的平方根，例如在計算標準差或標準化資料集中的值時找出變異數的根。 這對於進階統計或資料轉換計算非常有用。

**在計算量度產生器**&#x200B;中：將&#x200B;**平方根**&#x200B;套用至量度或運算式。 例如： **平方根**(變異數（*收入*）)會傳回&#x200B;*收入*&#x200B;的標準差。

>[!TIP]
>
>當您需要按比例縮放量度或支援其他依賴根值的統計函式時使用。
>

## 標準差 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="標準差"
>abstract="根據一組來自母體的樣本資料，傳回標準差或變異數的平方根。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 標準差 (量度，include_zeros)]**

[!BADGE 表格]{type="Neutral"}根據一組來自母體的樣本資料，傳回標準差或變數的平方根。

| 引數 | 說明 |
|---|---|
| | 您要計算其標準差的量度。 |
| 包括零 | 計算中是否包括零值。 |

**使用案例**：測量平均值差異的程度，例如評估日收入或造訪次數在一段時間內是否一致。 這有助於識別效能的波動性、穩定性或異常波動。

**在計算量度產生器中**：套用&#x200B;**標準差**&#x200B;至量度（例如&#x200B;*收入*&#x200B;或&#x200B;*工作階段*），以計算所選劃分或日期範圍內值的分佈。 例如： **標準差**（*收入*）會顯示每日收入偏離平均值的程度。

>[!TIP]
>
>搭配&#x200B;*Mean*&#x200B;使用以偵測異常，或比較行銷活動、產品或區段間的績效一致性。
>

## 變異數 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="變異數"
>abstract="根據來自母體的一組樣本資料，傳回變異數。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 變數 (量度，include_zeros)]**

[!BADGE 表格]{type="Neutral"}根據一組來自母體的樣本資料傳回變數。

| 引數 | 說明 |
|---|---|
| 量度 | 您要計算其變數的量度。 |
| 包括零 | 計算中是否包括零值。 |

**使用案例**：測量資料集中的值和平均值的分佈範圍，例如分析有多少每日收入或工作階段期間會隨著時間而改變。 這有助於量化效能的一致性或波動程度。

**在計算量度產生器中**：套用&#x200B;**變數**&#x200B;至類似&#x200B;*收入*&#x200B;或&#x200B;*每次造訪逗留時間*&#x200B;的量度，以計算平均值偏離平均值的平方。 例如： **Variance**(*Revenue*)會顯示所選範圍內的收入值與平均值的差異。

>[!TIP]
>
>搭配&#x200B;**標準差**&#x200B;使用，以更清楚瞭解資料變異性，並識別無法預測的效能區域。
>

變數的方程式為：

![](assets/variance_eq.png){width="100"}

其中 *x* 是樣本平均值 [MEAN(*量度*)](#mean)，而 *n* 是樣本大小。


為了計算變數，請查看整欄的數字。請先從那列數字計算平均值。取得平均值後，請陸續處理每個項目，然後進行下列步驟:

1. 將數字減去平均值。

1. 取結果的平方。

1. 將其加入總計。

反覆運算整欄之後，會得到單一合計。然後將該總數除以欄中的專案數。 該數字是欄的變數。 這是一個數字。 但是，它會顯示為一欄數字。

在以下三項目欄的範例中：

| 欄 |
|:---:|
| 1 |
| 2 |
| 3 |

此欄的平均值為2。 欄的變數為 ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3。

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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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