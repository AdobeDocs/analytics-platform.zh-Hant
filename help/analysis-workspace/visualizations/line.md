---
description: 使用線條圖視覺效果來描繪資料集的趨勢 (以時間為基礎)
title: 折線圖
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 94%

---


# 折線圖

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

線條圖視覺效果使用線條圖表示量度，以顯示一段時間中值的變化。僅可在使用時間當作維度時，才使用折線圖。

![線條圖視覺效果](assets/line-viz.png)

>[!IMPORTANT]
>
>某些線條圖視覺效果設定 (例如[!UICONTROL 顯示趨勢線]) 目前正進行有限的測試。[更多詳情](https://docs.adobe.com/content/help/zh-Hant/analytics/landing/an-releases.html)

按一下線條圖視覺效果右上角的齒輪圖示，即可存取可用的&#x200B;[**視覺效果設定**](freeform-analysis-visualizations.md)。設定可歸類為：

* **一般**：在各種視覺效果類型中都很常見的設定
* **軸**：影響線條圖視覺效果 X 或 Y 軸的設定
* **覆蓋**：用於將其他內容新增至線條圖視覺效果中所顯示系列的選項。

![視覺效果設定](assets/viz-settings-modal.png)

## 變更粒度

[視覺效果設定](freeform-analysis-visualizations.md)中的粒度下拉式清單可讓您將趨勢視覺效果 (例如折線圖、長條圖) 從每日變更為每週、每月等。粒度也會在資料來源表格中更新。

## 顯示最小值或最大值

在&#x200B;**[!UICONTROL 「視覺效果設定]** >**[!UICONTROL 覆蓋]** > **[!UICONTROL 顯示最小值/最大值」]**&#x200B;下方，您可以覆蓋最小值和最大值標籤，以便快速反白標示量度中的尖峰和低谷。注意：最小值／最大值是從視覺化中的可見資料點衍生而來，而非維度中的完整值集。

![顯示最小值/最大值](assets/min-max-labels.png)

## 顯示趨勢線覆蓋

在&#x200B;**[!UICONTROL 「視覺效果設定]** > **[!UICONTROL 覆蓋]** > **[!UICONTROL 顯示趨勢線」]**&#x200B;下方，您可以選擇將迴歸趨勢線新增至線條圖系列。趨勢線有助於描繪出資料中更清晰的模式。

![線性趨勢線](assets/show-linear-trendline.png)

所有模型都使用普通最小平方法：

| 模型 | 說明 |
| --- | --- |
| 線性 | 為簡單的線性資料集建立最合適的直線，當資料以穩定速率增加或減少時非常有用。方程式：`y = a + b * x` |
| 對數 | 建立最合適的曲線，當資料變更率快速增加或減少，然後穩定下來時相當有用。對數趨勢線可使用負值和正值。方程式：`y = a + b * log(x)` |
| 指數 | 建立曲線，當資料以不斷提高的速率上升或下降時相當有用。如果您的資料包含零或負值，則不應使用此選項。方程式：`y = a + e^(b * x)` |
| 乘冪 | 建立曲線，比較以特定速率增加的測量之資料集時相當有用。如果您的資料包含零或負值，則不應使用此選項。方程式：`y = a * x^b` |
| 二次方 | 找出拋物線形 (向上或向下凹入) 的資料集最合適的線條。方程式：`y = a + b * x + c * x^2` |
