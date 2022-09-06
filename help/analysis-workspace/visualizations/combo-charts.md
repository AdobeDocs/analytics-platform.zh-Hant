---
description: 可讓您輕鬆在Analysis Workspace中視覺化比較資料，例如建立上個月、去年等的比較。
title: 組合圖視覺效果
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: 5eebcccc45b9760ecc18ec94ca526f2082d089bc
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 31%

---

# 組合圖表

>[!NOTE]
>
>此功能目前正在進行[有限測試](/help/release-notes/releases.md)。

此 [!UICONTROL 組合圖] 視覺效果可讓您輕鬆快速建立比較視覺效果，而無須先建立表格。您可以透過折線圖/長條圖組合輕鬆檢視資料趨勢。

使用 [!UICONTROL 組合圖] to

* 將本週的訂單與上個月（和去年）的訂單進行比較，只需點擊幾次即可完成。

* 快速分析和比較多個量度(例如 [!UICONTROL 不重複訪客] 和 [!UICONTROL 收入])，而在同一圖表上彼此相對。

* 根據函式分析量度(例如 [!UICONTROL 累積平均值])。

請記住，您可以

* 在單一中新增多個比較 [!UICONTROL 組合圖].
* 如果您新增一或多個比較，這些比較必須是相同類型，例如 [!UICONTROL 時間比較].
* 最多可加5次比較。
* 最多可套用3個篩選器（區段）至量度。

## 建立組合圖

1. 從左側邊欄的「視覺效果」下拉式清單中，拖曳 [!UICONTROL 組合圖] 視覺效果轉換為空白麵板。

   ![](assets/combo-chart-build.png)

1. 從下拉式清單中，選取X軸的維度和Y軸的量度。

1. 選取 [!UICONTROL 行比較] 您想要使用。

   | 行比較類型 | 定義 |
   | --- | --- |
   | **[!UICONTROL 時間比較]** | 最常見的比較類型 — 例如，將此時段與4週前比較。 如果您選取 [!UICONTROL 時間比較]，請進行次要選取，以比較您要比較的時段。<p>![](assets/combo-time-period.png) |
   | **[!UICONTROL 函數]** | 你可以引入 [!UICONTROL 平均] 進行比較。 請參閱下方支援的函式清單。<p>![](assets/combo-functions.png) |
   | **[!UICONTROL 次要量度]** | 例如，您可以比較 [!UICONTROL 收入] 至其他量度。<p>![](assets/combo-2metrics.png) |

   {style=&quot;table-layout:auto&quot;}

1. 按一下&#x200B;**[!UICONTROL 「建置」]**。

   輸出看起來將類似以下：

   ![](assets/combo-output.png)

   當前期間以條形圖顯示，而比較期間以折線圖表示。 折線圖上的點稱為「長條鐘」。

## 支援的函式

如果您選擇 **[!UICONTROL 函式]** 作為 [!UICONTROL 行比較類型]，則會傳回您所選量度的函式。

| 函數 | 定義 |
| --- | --- |
| **[!UICONTROL 欄總和]** | 在欄內（跨維度的元素）新增量度的所有數值 |
| **[!UICONTROL 累積平均值]** | 傳回最後 N 列的平均值。 |
| **[!UICONTROL 中位數]** | 傳回一欄中量度的中位數。中位數是位於一組數字中間的數字，也就是一半數字的值大於或等於中位數，另一半數字的值小於或等於中位數。 |
| **[!UICONTROL 累積]** | N列的累積總和。 |
| **[!UICONTROL 欄最大值]** | 傳回量度欄中一組維度元素的最大值。 |
| **[!UICONTROL 平均值]** | 傳回量度的算術平均值。 |
| **[!UICONTROL 欄最小值]** | 傳回量度欄中一組維度元素的最小值。 |

{style=&quot;table-layout:auto&quot;}

以下是「收入」量度的累積平均值範例：

![](assets/combo-cumul-avg.png)

以下是包含累積平均值和平均值函式的組合圖範例：

![](assets/combo-two-functions.png)

## 組合圖設定

按一下組合圖右上方的齒輪圖示以變更其設定。

![](assets/combo-settings.png)

| 設定 | 定義 |
| --- | --- |
| **[!UICONTROL 視覺效果類型]** | 可讓您切換至其他視覺效果類型。 |
| **[!UICONTROL 詳細程度]** | 若要取得最新式的視覺效果，您可在此下拉功能表中變更時間的詳細程度 (日、週、月等)。 |
| **[!UICONTROL 一般]** |  |
| **[!UICONTROL 百分比]** | 以百分比顯示值。 |
| **[!UICONTROL 可見圖例]** | 可讓您隱藏組合圖視覺效果的詳細圖例文字。 |
| **[!UICONTROL 限制項目數上限]** | 減少X軸上的項目數。 如果您有大資料集，則只能顯示前10個項目（或您挑選的任何值）。 |
| **[!UICONTROL 覆蓋]** | 線上上顯示或隱藏槓鈴。 |
| **[!UICONTROL 軸]** |  |
| **[!UICONTROL 顯示雙軸]** | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，這項功能會很有用。除非有多個比較，否則雙軸顏色與表的顏色匹配。 在這種情況下，所有比較的顏色都是灰色。 |
| **[!UICONTROL 標準化]** | 強制量度為相同比例。當繪製的量度大小非常不同時，這項功能會很有用。 |
| **[!UICONTROL 顯示x軸]** | 顯示或隱藏x軸。 |
| **[!UICONTROL 顯示Y軸]** | 顯示或隱藏Y軸。 |
| **[!UICONTROL 將Y軸固定於零]** | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |

{style=&quot;table-layout:auto&quot;}
