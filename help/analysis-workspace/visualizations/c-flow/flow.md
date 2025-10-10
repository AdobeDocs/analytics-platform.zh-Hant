---
description: 瞭解如何使用Analysis Workspace中的流量視覺效果。
title: 流量概觀
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 96%

---

# 流量概觀 {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="流量"
>abstract="建立視覺效果以查看從某一接觸點到下一個接觸點的人員流量。"

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="流量"
>abstract="分析從某一接觸點到下一個接觸點的造訪或訪客流量。指定開始和結束的元件 (量度、維度或項目)。或者，您也可以定義進階設定，進一步設定視覺效果。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 中的流量圖視覺效果。_<br/>_請參閱本文中 ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_**Adobe Analytics**版本的[流量](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)_。_

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;視覺效果會顯示通過您網站和應用程式的客戶路徑。

透過視覺效果可以：

* 將透過您網站或應用程式的客戶歷程以視覺效果呈現。
* 分析客戶在所指定查核點 (例如登入、特定維度或退出) 之前和之後的前往位置。
* 指定選定路徑中的特定點，建立區段。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [建立流量視覺效果](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"}的示範影片。

{{videoaa}}

>[!ENDSHADEBOX]


## 維度間流量

您可以顯示[維度之間的流量](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)。例如，您可以在一個圖表中結合頁面和部門。在此例中，您的流量可能來自首頁、前往「男性」頁面，接著前往「鞋子」部門。

每一欄會顯示不同的維度。拖曳維度並將其放至拖放區域，即可將該維度新增至圖表中。

>[!MORELIKETHIS]
>
>[設定流量視覺效果](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。
>

## 在流量、流失或歷程畫布之間作選擇

流量視覺效果與[流失視覺效果](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)有相似之處，但也有重要的差異。

### 了解差異性

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何時使用流量

流量視覺效果適合：

* 對路徑的下一個接觸點進行探索性的臨機分析。(使用歷程畫布來記錄有預先定義的頁面序列的歷程，或用來記錄使用最終路徑的歷程。)

* 具有多個入口點和路徑的非線性歷程。(使用歷程畫布來記錄具有預先定義頁面序列的歷程。)

使用[上面表格](#understand-the-differences)來了解流量、流失和流量和歷程畫布之間的差異。
