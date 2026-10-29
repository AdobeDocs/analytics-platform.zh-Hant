---
description: 使用趨勢主題視覺效果來探索對話中的趨勢主題。
title: 趨勢主題
feature: Visualizations
role: User
hide: true
source-git-commit: 113a215e26092c65d6eaf2c321f60d3f3a5015b8
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 16%
---
# 趨勢主題 {#trending-topics}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="趨勢主題"
>abstract="建立視覺效果，顯示趨勢主題的階層式向下展開功能劃分，以及發生次數和百分比，以協助您識別對話中的重要主題。"

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="趨勢主題"
>abstract="根據選定的排名量度來分析趨勢主題。 選取主題以深入研究至最多 5 層。 搜尋特定主題，並將主題與其他日期範圍進行比較。"

{{release-limited-testing}}

![摘要](/help/assets/icons/Feed.svg) **[!UICONTROL 趨勢主題]**&#x200B;視覺效果可讓您探索和分析趨勢主題，作為交談深入分析的一部分。

您可以搜尋特定主題，並將每個層級每個主題的數量和百分比與其他資料範圍進行比較。

## 建立及設定 {#trendimg-topics-create-and-configure}

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel"
>title="使用非預設歸因模型"
>abstract="為此量度啟用非預設歸因模型。"

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_usenondefaultattributionmodel_disabled"
>title="使用非預設歸因模型"
>abstract="非預設歸因模型不適用於此量度。"


若要建立及設定&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺效果：

1. 新增![摘要](/help/assets/icons/Feed.svg) **[!UICONTROL 趨勢主題]**&#x200B;視覺效果。 請參閱[新增視覺效果至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 在&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺效果設定中：

   1. 選取&#x200B;**[!UICONTROL 排名量度]**。 例如： **[!UICONTROL 交談]**。
   1. 如果您想要在量度上使用非預設的[歸因](/help/analysis-workspace/attribution/models.md)模型，請選取&#x200B;**[!UICONTROL 使用非預設的歸因模型]**，然後選取&#x200B;**[!UICONTROL 模型]**、**[!UICONTROL 容器]**&#x200B;和&#x200B;**[!UICONTROL 回顧視窗]**。
1. 選取&#x200B;**[!UICONTROL 建置]**&#x200B;以建置視覺效果。 選取&#x200B;**[!UICONTROL 重設]**&#x200B;將組態值重設為預設值。

若要重新設定趨勢主題視覺效果，請選取&#x200B;**排名量度： _排名量度_旁的![編輯](/help/assets/icons/Edit.svg) |子主題層級： _x_**。

## 使用

若要使用視覺效果：

![使用趨勢主題視覺效果](assets/trending-topics.png)

* 將滑鼠指標暫留在主題上，即可檢視包含更多詳細資訊的快顯視窗。➊

* 若要檢視較低層級主題的趨勢子主題，請選取特定層級的主題。 如果在子層級沒有可用的主題，您會看到![資料移除](/help/assets/icons/DataRemove.svg) **[!UICONTROL 找不到&#x200B;_主題>子主題_ > ...]**&#x200B;的子主題。

* 使用![搜尋](/help/assets/icons/Search.svg) **[!UICONTROL _搜尋主題_]**&#x200B;來快速搜尋主題。➋

* 若要比較主題與其他日期範圍，請選取日期範圍，範圍是&#x200B;**[!UICONTROL 比較對象]**。➌

  若要使用自訂日期範圍：

  * 從下拉式功能表中選取&#x200B;**[!UICONTROL 自訂日期範圍]**，並在&#x200B;**[!UICONTROL 新增日期範圍]**&#x200B;對話方塊中定義並儲存自訂日期範圍。
  * 選取該自訂日期範圍。

* 若要顯示目前所選主題的線圖，請在&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺效果上放置[線](/help/analysis-workspace/visualizations/line.md)視覺效果。 **[!UICONTROL 線條]**&#x200B;視覺效果會自動連結至&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺效果，並顯示所選主題的線條。

  ![趨勢主題線條視覺效果](assets/trending-topics-line-viz.png)

## 設定

下列特定的[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)可供使用。

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 顯示實際值]** | 顯示主題的實際值。 |
| **[!UICONTROL 顯示百分比]** | 顯示主題的百分比。 |
