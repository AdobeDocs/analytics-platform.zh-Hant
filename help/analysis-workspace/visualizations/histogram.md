---
description: 直方圖類似於長條圖，但前者將數字分組為範圍 (貯體)。
title: 直方圖
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 35%

---

# 直方圖 {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="直方圖"
>abstract="建立直方圖視覺效果來表示數值資料在範圍組中的分佈情形。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*本文以&#x200B;**Customer Journey Analytics**記錄長條圖視覺效果。 請參閱此文章的&#x200B;**Adobe Analytics**版本的[色階分佈圖](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram)。*

>[!ENDSHADEBOX]


![色階分佈圖](/help/assets/icons/Histogram.svg) **[!UICONTROL 色階分佈圖]**&#x200B;視覺效果類似於[!UICONTROL 長條圖]視覺效果，但會將數字分組為範圍（貯體）。 Analytics 會自動將數字分組至範圍貯體，但您可以在[進階設定](#advanced-settings)中變更設定。

## 使用

若要建立直方圖：

1. 新增![色階分佈圖](/help/assets/icons/Histogram.svg) **[!UICONTROL 色階分佈圖]**&#x200B;視覺效果。 請參閱[將視覺效果新增至面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 從&#x200B;**[!UICONTROL Metrics]**&#x200B;元件清單拖曳量度，或從&#x200B;[!UICONTROL *新增量度*]&#x200B;下拉式功能表選取量度。
1. （選擇性）選取&#x200B;**[!UICONTROL 顯示進階設定]**。 請參閱[進階設定](#advanced-settings)。
1. 選取「**[!UICONTROL 建立]**」。

>[!NOTE]
>
>直方圖僅支援標準量度，不支援計算量度。

在以下範例中，長條圖可用來儲存人數的工作階段。 長條圖顯示大多數人確實在所選日期範圍內有16至21個工作階段。

![](assets/histogram.png)

## 進階設定

在視覺效果中，可以使用特定的長條圖設定。

| 長條圖設定 | 說明 |
|---|---|
| **[!UICONTROL 開始貯體]** | 決定直方圖開始使用的貯體。「1」是預設值。您可設定從 0 開始的數字，一直到無限大 (無負數)。 |
| **[!UICONTROL 量度值區]** | 可讓您增加/減少資料範圍（貯體）的數量。 值區的最大數量為50。 |
| **[!UICONTROL 量度貯體大小]** | 可讓您設定每個貯體的大小。例如，您可將貯體大小從 1 次頁面檢視變更為 2 次頁面檢視。 |
| **[!UICONTROL 計數方法]** | 從&#x200B;**[!UICONTROL 人員]**、**[!UICONTROL 工作階段]**&#x200B;或&#x200B;**[!UICONTROL 事件]**&#x200B;中選取。 例如，每個工作階段的頁面檢視數、每個人的頁面檢視數，或每個事件的頁面檢視數。 |

<!--Russ or Meike - Check Hit Type link above. -->

**範例**：

| 起始貯體 | 量度值區 | 量度貯體大小 | 結果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![色階分佈圖，開始貯體1，量度貯體5，量度貯體大小2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![色階分佈圖，起始貯體0，量度貯體3，量度貯體大小5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>


## 部落格貼文

請參閱這篇部落格，瞭解[使用長條圖識別非預期資料值](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)的相關資訊。
