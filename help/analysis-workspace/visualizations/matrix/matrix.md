---
title: Analysis Workspace中的矩陣視覺效果概觀
description: 瞭解Customer Journey Analytics Analysis Workspace中的矩陣視覺效果，包括它顯示的內容、何時使用，以及與其他視覺效果相較之下的結果。
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# 矩陣概述 {#matrix-overview}

Analysis Workspace中的矩陣視覺效果可讓您檢視兩個維度的維度專案如何重疊或相互關聯。

一個維度的Dimension專案會顯示為列（沿Y軸），而另一個維度的維度專案則會顯示為欄（沿X軸）。 每個交集儲存格都會根據您選擇的量度顯示重疊或相互關聯資料。

例如，下列矩陣視覺效果顯示依國家/地區代碼的裝置名稱事件重疊計數。

* Dimension 1 （列維度）：裝置名稱

* Dimension 2 （欄維度）：國家/地區代碼

* 量度：事件

![矩陣概述](assets/matrix-overview.png)

## 主要功能

* **比較兩個不同的維度**：瞭解一個維度中的專案如何與另一個維度中的專案相關。

* **比較維度與本身**：瞭解相同維度中的專案如何關聯。

* **重疊**：檢視維度專案的重疊。

* **關聯**：檢視維度專案的趨勢程度，範圍從–1 （永遠相反方向移動）到+1 （永遠一起移動）。

* **熱度圖色彩**：儲存格色彩顯示重疊是高還是低，或是相關是正還是負，以及它的強度。 重疊和相關性有不同的調色盤。

## 潛在的洞察

* 尋找兩個維度間的陣列和間隙。 例如，您可以回答下列問題：

  * 哪些行銷活動在某些區域表現良好，但在其他區域則否？

  * 哪些內容型別在每種裝置型別上執行時效果最佳？

* 找出維度專案彼此之間的趨勢。 例如，您可以回答下列問題：

  * 哪些行銷管道會隨著時間而趨向同一、哪些會獨立移動，哪些會朝著相反的方向移動？

  * 哪些頁面的流量會一起上升和下降？

* 比較維度與本身。 例如，您可以回答下列問題：

  * 同一人經常購買哪些產品？

  * 同一群人一起使用哪些裝置，例如行動電話和平板電腦？

## 在「矩陣」、「自由表格」、「文氏圖表」或「散佈圖」視覺效果之間選擇

矩陣視覺效果與[使用自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)中的多個維度欄、[Venn視覺效果](/help/analysis-workspace/visualizations/venn.md)和[散佈視覺效果](/help/analysis-workspace/visualizations/scatterplot.md)具有相似性。 每個視覺效果都會顯示元件彼此的相關性，但它們使用的元件及顯示結果的方式有所不同。

### 何時使用每個視覺效果

選擇最適合您分析的視覺效果：

* **矩陣：**&#x200B;針對指定的量度，檢視一個維度中每個維度專案與另一個維度中每個維度專案的關聯性，包括差距和一起走向的維度專案。

* **具有多個維度資料行的自由表格：**&#x200B;您最多可以新增5個維度做為個別的資料行至自由表格。 顯示在表格同一列中的Dimension專案會串連。 將任意數量的量度新增至表格，以檢視每個串連維度專案的量度資料。 篩選、排序及新增劃分至串連的維度專案。

* **Venn：**&#x200B;若為單一量度，最多可檢視3個區段的重疊。

* **散佈圖：**&#x200B;比較兩個或三個量度的維度專案，以找出模式與離群值。

### 了解差異性

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| 函數 | 矩陣 | 自由表格中的多個維度欄 | 文氏圖表 | 散佈圖 |
| --- | --- | --- | --- | --- |
| **使用的元件** | 2個維度；1個量度<p>比較2個維度或1個維度的維度專案。</p> | 最多5個維度；任何量度數量<p>出現在相同列中的Dimension專案會串連，且行為類似於單一維度專案。 串連的列會依據其量度值進行比較。</p> | 最多3個區段；1個量度<p>比較區段之間的重疊。</p> | 1個維度；最多3個量度<p>比較各量度的維度專案。</p> |
| **容器** | 在視覺效果中設定：「人員」（預設）、「工作階段」或「事件」<p>判斷重疊是否會計入相同人員、相同工作階段或相同事件中發生的維度專案。</p> | 無容器設定<p>每一列會結合套用至相同事件的維度專案。 您選擇的量度（例如「人員」或「工作階段」）會決定要計算哪些專案。</p> | 在每個區段中設定<p>每個區段都使用自己的[容器](/help/components/segments/seg-overview.md#containers) （人員、工作階段或事件）。 此量度會決定每個重疊中會計入哪些專案。</p> | 無容器設定<p>您選擇的量度會決定要計算哪些專案。</p> |
| **配置** | 格線，類似樞紐分析表<p>一個維度的Dimension專案是列，另一個維度的維度專案是欄。</p> | 清單<p>每一列會結合每個維度欄中的一個維度專案。</p> | 重疊的圓形 | X軸和Y軸上的點 |
| **顯示重疊** | 是<p>顯示列中每個維度專案與欄中每個維度專案之間的重疊。</p><p>使用&#x200B;**[!UICONTROL 重疊計數]**&#x200B;檢視。</p> | 是<p>顯示每個維度專案組合的量度，每一列顯示一個組合。</p> | 是<p>顯示區段之間的重疊。</p> | 否 |
| **顯示相互關聯** | 是，在維度專案之間<p>以從–1 （相反方向）到+1 （一起）的縮放顯示維度專案在一段時間內的趨勢程度。</p><p>使用&#x200B;**[!UICONTROL 相互關聯強度]**&#x200B;檢視。</p> | 否 | 否 | 是，在量度之間<p>顯示量度彼此的關係。 每個點都是由最多3個量度繪製的維度專案。</p> |

{style="table-layout:auto"}

