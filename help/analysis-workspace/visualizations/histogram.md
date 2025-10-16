---
description: 瞭解如何使用色階分佈圖（類似於長條圖），但將數字分組為範圍（貯體）。
title: 直方圖
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 80%

---

# 直方圖 {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="直方圖"
>abstract="建立直方圖視覺效果來表示數值資料在範圍組中的分佈情形。"


>[!BEGINSHADEBOX]

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 中的直方圖視覺效果。_<br/>_請參閱本文中 ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_**Adobe Analytics**版本的[直方圖](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/histogram)_。_

>[!ENDSHADEBOX]


![直方圖](/help/assets/icons/Histogram.svg) **[!UICONTROL 直方圖]**&#x200B;視覺效果類似於[!UICONTROL 長條圖]視覺效果，但前者將數字分組為範圍 (貯體)。Analytics 會自動將數字分組至範圍貯體，但您可以在[進階設定](#advanced-settings)中變更設定。

## 使用

若要建立直方圖：

1. 新增![直方圖](/help/assets/icons/Histogram.svg) **[!UICONTROL 直方圖]**&#x200B;視覺效果。請參閱[新增視覺效果至面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 從&#x200B;**[!UICONTROL Metrics]**&#x200B;元件清單拖曳量度，或從&#x200B;[!UICONTROL *新增量度*]&#x200B;下拉式功能表選取量度。
1. (可選) 請選取「**[!UICONTROL 顯示進階設定]**」：請參閱[進階設定](#advanced-settings)。
1. 選取「**[!UICONTROL 建置]**」。

>[!NOTE]
>
>直方圖僅支援標準量度，不支援計算量度。

在下列範例中，直方圖用於人數的貯體工作階段。直方圖顯示大多數人在選取的日期範圍內的確有 16 至 21 個工作階段。

![直方圖](assets/histogram.png)

## 進階設定

作為視覺效果的一部分，可以使用特定直方圖設定。

| 直方圖設定 | 說明 |
|---|---|
| **[!UICONTROL 起始貯體]** | 決定直方圖開始使用的貯體。預設值為「1」。 您可以設定從0到無窮大的起始數字（無負數）。 |
| **[!UICONTROL 量度貯體]** | 可讓您增加/減少資料範圍 (貯體) 的數量，最大貯體數量為 50。 |
| **[!UICONTROL 量度貯體大小]** | 可讓您設定每個值區的大小。 例如，您可以將貯體大小從1個頁面檢視變更為2個頁面檢視。 |
| **[!UICONTROL 計算方法]** | 自「**[!UICONTROL 全域帳戶]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、「**[!UICONTROL 帳戶]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、「**[!UICONTROL 購買群組]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、「**[!UICONTROL 機會]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}」、「**[!UICONTROL 人員]**」、「**[!UICONTROL 工作階段]**」，或者「**[!UICONTROL 事件]**」中選取。例如，每個帳戶 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 的頁面檢視次數、每個工作階段的頁面檢視次數、每位人員的頁面檢視次數，或者每個事件的頁面檢視次數。 |

<!--Russ or Meike - Check Hit Type link above. -->

**範例**：

| 起始貯體 | 量度貯體 | 量度貯體大小 | 結果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![直方圖，起始貯體 1，量度貯體 5，量度貯體大小 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![直方圖，起始貯體 0，量度貯體 3，量度貯體大小 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[視覺化內容選單](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>>[使用直方圖識別非預期的資料值](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

