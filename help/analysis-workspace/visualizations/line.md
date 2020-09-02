---
description: 使用線條視覺化來描繪趨勢（以時間為基礎的）資料集
title: 折線圖
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 20%

---


# 折線圖

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

「行」視覺化會使用行來表示量度，以顯示值在一段時間內的變化。 僅可在使用時間當作維度時，才使用折線圖。

![線條視覺化](assets/line-viz.png)

>[!IMPORTANT]
>
>某些線條視覺化設定，例如 [!UICONTROL 顯示趨勢線]，目前正進行有限的測試。 [更多詳情](https://docs.adobe.com/content/help/zh-Hant/analytics/landing/an-releases.html)

按一下「線條」視覺化右上角的齒輪圖示，即可存取 [**視覺化設定**](freeform-analysis-visualizations.md) 可用。 設定分為：

* **一般**:在各種視覺化類型中都常見的設定
* **軸**:影響線條視覺化x或y軸的設定
* **覆蓋**:用於新增其他上下文至行視覺化中顯示的系列的選項。

![視覺效果設定](assets/viz-settings-modal.png)

## 變更詳細程度

[視覺效果設定](freeform-analysis-visualizations.md)中的粒度下拉式清單可讓您將趨勢視覺效果 (例如折線圖、長條圖) 從每日變更為每週、每月等。詳細程度也會在資料來源表格中更新。

## 顯示最小值或最大值

在 **[!UICONTROL 視覺化設定]** > **[!UICONTROL 覆蓋]** > **[!UICONTROL 顯示最小值／最大值]**，您可以覆蓋最小值和最大值標籤，以快速反白顯示量度中的尖峰和谷谷。 注意：最小值／最大值是從視覺化中的可見資料點衍生而來，而非維度中的完整值集。

![顯示最小值／最大值](assets/min-max-labels.png)

## 顯示趨勢線覆蓋

在 **[!UICONTROL 視覺化設定]** > **[!UICONTROL 覆蓋]** > **[!UICONTROL 顯示趨勢線]**，您可以選擇將回歸趨勢線新增至行系列。 趨勢線有助於描述資料中更清晰的模式。

![線性趨勢線](assets/show-linear-trendline.png)

所有模型都使用普通最小二乘擬合：

| 模型 | 說明 |
| --- | --- |
| 線性 | 為簡單的線性資料集建立最適合的直線，當資料以穩定速率增加或減少時，該直線非常有用。 等式： `y = a + b * x` |
| 對數 | 建立最適合的曲線，當資料的變更率快速增加或減少，然後退出等級時，就很有用。 對數趨勢線可使用負值和正值。 等式： `y = a + b * log(x)` |
| 指數 | 建立曲線，當資料以不斷增加的速率上升或下降時，就很有用。 如果您的資料包含零值或負值，則不應使用此選項。 等式： `y = a + e^(b * x)` |
| 乘冪 | 建立曲線，對於比較以特定速率增加的度量的資料集很有用。 如果您的資料包含零值或負值，則不應使用此選項。 等式： `y = a * x^b` |
| 二次方 | 尋找形狀為拋物線（向上或向下凹入）的資料集的最佳擬合。 等式： `y = a + b * x + c * x^2` |
