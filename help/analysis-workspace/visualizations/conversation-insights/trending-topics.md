---
description: 使用趨勢主題視覺效果來探索對話中的趨勢主題。
title: 趨勢主題
feature: Visualizations
role: User
hide: true
source-git-commit: 65d4115d4c292cff7e074d37a91563d369072ba5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 20%
---
# 趨勢主題

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="趨勢主題"
>abstract="建立視覺化圖表來顯示趨勢主題的階層式深入研究劃分，包括發生次數和百分比，以協助您識別對話中的重要主題。"

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="趨勢主題"
>abstract="根據選定的排名量度來分析趨勢主題。 選取主題以深入研究至最多 5 層。 搜尋特定主題，並將主題與其他日期範圍進行比較。"

![摘要](/help/assets/icons/Feed.svg) **[!UICONTROL 趨勢主題]**&#x200B;視覺效果可讓您探索和分析趨勢主題，作為交談深入分析的一部分。

您可以搜尋特定主題，並將每個層級每個主題的數量和百分比與其他資料範圍進行比較。

## 建立及設定

若要建立和設定趨勢主題視覺效果：

1. 新增![摘要](/help/assets/icons/Feed.svg) **[!UICONTROL 趨勢主題]**&#x200B;視覺效果。 請參閱[新增視覺效果至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 在&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺效果設定中：

   1. 選取&#x200B;**[!UICONTROL 排名量度]**。 例如： **[!UICONTROL 交談]**。
   1. 選擇性地選取&#x200B;**[!UICONTROL 設定歸因]**，並選取&#x200B;**[!UICONTROL 模型]**、**[!UICONTROL 容器]**&#x200B;和&#x200B;**[!UICONTROL 回顧視窗]**。
   1. 選取&#x200B;**[!UICONTROL 限制子主題層級]**&#x200B;的層級。 預設值為&#x200B;**[!UICONTROL 層級5]**。

      >[!NOTE]
      >
      >**[!UICONTROL 限制子主題層級]**&#x200B;定義了視覺效果中主題要向下鑽研的層級數目上限。 若在該定義的最大數量內沒有其他主題可供使用，![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL 找不到主題]**。

1. 選取&#x200B;**[!UICONTROL 建置]**&#x200B;以建置視覺效果。 選取&#x200B;**[!UICONTROL 重設]**&#x200B;將組態值重設為預設值。

若要重新設定趨勢主題視覺效果，請選取&#x200B;**排名量度： _排名量度_旁的![編輯](/help/assets/icons/Edit.svg) |子主題層級： _x_**。

## 使用

若要使用視覺效果：

* 若要鑽研並檢視較低層級之主題的趨勢子主題，請選取特定層級的主題。

* 若要比較其他日期範圍的主題，請從「比較對象」中選取日期範圍。 若要使用自訂日期範圍：
  * 從下拉式選單中選取「自訂日期範圍」，並在「新增日期範圍」對話方塊中定義並儲存自訂日期範圍。
  * 選取該自訂日期範圍。

* 若要顯示目前所選主題的線圖，請在&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺化上放置[線](/help/analysis-workspace/visualizations/line.md)視覺化。 **[!UICONTROL 線條]**&#x200B;視覺效果會自動連結至&#x200B;**[!UICONTROL 趨勢主題]**&#x200B;視覺效果。

## 設定

下列特定的[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)可供使用。

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 顯示實際值]** | 顯示主題的實際值。 |
| **[!UICONTROL 顯示百分比]** | 顯示主題的百分比。 |



