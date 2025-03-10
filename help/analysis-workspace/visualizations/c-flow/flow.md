---
description: 瞭解流量功能，此功能可顯示客戶使用您網站和應用程式的路徑。
title: 流量概觀
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 36%

---

# 流量 {#flow}

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

_本文記錄了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中的流量視覺效果。_<br/>_檢視此文章的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[流量](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)。_

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;視覺效果可顯示客戶使用您網站和應用程式的路徑。

您可以使用視覺效果來：

* 將客戶在您網站或應用程式中的歷程視覺化。
* 分析客戶在所指定查核點（例如登入、特定維度或退出）之前和之後的前往位置。
* 指定所選路徑中的特定點，以建立篩選器。


>[!BEGINSHADEBOX]

請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [建立流量視覺效果](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"}以取得示範影片。

{{videoaa}}

>[!ENDSHADEBOX]


## 維度間流程

您可以顯示[維度之間的流量](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)。例如，您可以在一個圖表中結合頁面和部門。在此例中，您的流量可能來自首頁、前往「男性」頁面，接著前往「鞋子」部門。

每一欄會顯示不同的維度。拖曳維度並將其放至拖放區域，即可將該維度新增至圖表中。

>[!MORELIKETHIS]
>
>[設定流量視覺效果](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。
>

## 在「流量」、「流失」或「歷程畫布」視覺效果之間選擇

流量視覺效果與[流失視覺效果](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)有共同之處，但有重要的差異。

### 瞭解差異

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何時使用流量

流量視覺效果最適合用於：

* 探索性的Ad Hoc Analysis，用於路徑上的下一個直接接觸點。 （對於具有預先定義的頁面順序或使用最終路徑的歷程，請使用歷程畫布。）

* 具有多個入口點和路徑的非線性歷程。 （對於具有預先定義之頁面順序的歷程，請使用歷程畫布。）

使用[上表](#understand-the-differences)瞭解流量、流失和歷程畫布之間的差異。
