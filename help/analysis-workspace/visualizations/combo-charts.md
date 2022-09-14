---
description: 讓您在 Analysis Workspace 中輕鬆地將比較資料視覺化，例如建置和上個月、去年等的比較資料。
title: 組合圖表視覺效果
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: 5aee0fcc0ec241d946da4ce97dc01eb6274648aa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 99%

---

# 組合圖表

[!UICONTROL 組合圖表]視覺效果可讓您快速建立比較視覺效果，而不用先建立表格。您可以在折線/條形組合中輕鬆地檢視資料中的趨勢。

使用[!UICONTROL 組合圖表]：

* 比較本週的訂單與上個月 (以及去年) 同時間的訂單 - 全都按幾下就能完成。
* 在相同圖表上快速逐一分析和比較多項量度 (例如[!UICONTROL 不重複訪客]和[!UICONTROL 收入])。
* 根據一段時間範圍內的函數，分析量度 (例如[!UICONTROL 累積平均值])。

請記住，您可以：

* 在單一[!UICONTROL 組合圖表]中新增多筆比較資料。
* 如果您新增一筆或更多比較資料，這些資料必須是相同類型，例如[!UICONTROL 時間比較]。
* 您最多只能新增 5 筆比較資料。
* 一個量度最多可以套用 3 個篩選器 (區段)。

## 建置組合圖表

1. 從左側邊欄中的「視覺效果」下拉式清單，將「[!UICONTROL 組合圖表]」視覺效果拖曳至空白面板。

   ![建置](assets/combo-chart-build.png)

1. 從下拉式清單，選取 X 軸的維度和 Y 軸的量度。

1. 選取您要使用的[!UICONTROL 折線比較]類型。

   | 折線比較類型 | 定義 |
   | --- | --- |
   | **[!UICONTROL 時間比較]** | 最常見的比較類型 - 例如，將此時段與 4 週前進行比較。如果您已選取[!UICONTROL 時間比較]，請針對您要比較的時段進行次要比較。<p>![時段](assets/combo-time-period.png) |
   | **[!UICONTROL 函數]** | 您可以將[!UICONTROL 平均值]等函數導入比較中。請參閱以下的支援函數清單。<p>![函數](assets/combo-functions.png) |
   | **[!UICONTROL 次要量度]** | 例如，您可以將[!UICONTROL 收入]與另一個量度比較。<p>![兩個量度](assets/combo-2metrics.png) |

   {style=&quot;table-layout:auto&quot;}

1. 按一下&#x200B;**[!UICONTROL 「建置」]**。

   輸出將與下圖相似：

   ![輸出](assets/combo-output.png)

   目前期間會以條形圖顯示，而比較期間則以折線圖呈現。折線圖上的圓點稱為「槓鈴」。

## 支援的函數

如果您選擇&#x200B;**[!UICONTROL 函數]**&#x200B;作為[!UICONTROL 折線比較類型]，則會傳回您已選擇的量度函數。

| 函數 | 定義 |
| --- | --- |
| **[!UICONTROL 欄總和]** | 將某一欄中量度的所有數值 (所有維度元素) 相加。 |
| **[!UICONTROL 累積平均值]** | 傳回最後 N 列的平均值。 |
| **[!UICONTROL 中位數]** | 傳回一欄中量度的中位數。中位數是位於一組數字中間的數字，也就是一半數字的值大於或等於中位數，另一半數字的值小於或等於中位數。 |
| **[!UICONTROL 累積]** | N 列的累積總和。 |
| **[!UICONTROL 欄最大值]** | 傳回量度欄中一組維度元素的最大值。 |
| **[!UICONTROL 平均值]** | 傳回量度的算術平均值或平均值。 |
| **[!UICONTROL 欄最小值]** | 傳回量度欄中一組維度元素的最小值。 |

{style=&quot;table-layout:auto&quot;}

以下為收入量度的累積平均值範例：

![累積平均值](assets/combo-cumul-avg.png)

以下為累積平均值和平均值函數的組合圖表範例：

![兩個函式](assets/combo-two-functions.png)

## 組合圖表設定

按一下組合圖表右上角的齒輪圖示，以變更其設定。

![設定](assets/combo-settings.png)

| 設定 | 定義 |
| --- | --- |
| **[!UICONTROL 視覺效果類型]** | 讓您切換至另一個視覺效果類型。 |
| **[!UICONTROL 粒度]** | 若要取得最新式的視覺效果，您可在此下拉功能表中變更時間的粒度 (日、週、月等)。 |
| **[!UICONTROL 一般]** |  |
| **[!UICONTROL 百分比]** | 以百分比顯示值。 |
| **[!UICONTROL 可見圖例]** | 讓您隱藏組合圖表視覺效果的詳細圖例文字。 |
| **[!UICONTROL 限制項目數量上限]** | 減少 X 軸上的項目數量。如果您有巨量資料集合，僅可顯示前 10 個項目 (或您選取的任一值)。 |
| **[!UICONTROL 重疊]** | 顯示或隱藏折線上的槓鈴。 |
| **[!UICONTROL 軸]** |  |
| **[!UICONTROL 顯示雙軸]** | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，這項功能會很有用。除非有多項比較，否則雙軸顏色會搭配表格的顏色。此時所有比較的顏色為灰色。 |
| **[!UICONTROL 標準化]** | 強制量度為相同比例。當繪製的量度大小非常不同時，這項功能會很有用。 |
| **[!UICONTROL 顯示 x 軸]** | 顯示或隱藏 x 軸。 |
| **[!UICONTROL 顯示 y 軸]** | 顯示或隱藏 y 軸。 |
| **[!UICONTROL 將 y 軸固定於零]** | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |

{style=&quot;table-layout:auto&quot;}
