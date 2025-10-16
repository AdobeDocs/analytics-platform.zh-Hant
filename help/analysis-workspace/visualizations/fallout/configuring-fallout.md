---
description: 瞭解如何設定並指定接觸點來建立多維度流失序列。
title: 設定流失視覺效果
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: d91e6aaebd14bc02f53b28820dd6013350e36d36
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 69%

---

# 設定流失視覺效果 {#configure-fallout-visualization}


您可以指定接觸點來建立多維度流失序列。 通常接觸點是您網站上的頁面。 不過，接觸點並不限於頁面。 例如，您可以新增事件 (例如件數)，以及不重複人員和回訪次數。您也可以新增維度，例如類別、瀏覽器型別或內部搜尋詞。

您甚至可以在接觸點內新增區段。 例如，您可能想比較 iOS 和 Android™ 使用者之類的區段。將所需區段拖曳至流失上方，這些區段的相關資訊會新增至流失報告中。如果只想顯示這些區段，您可以移除「所有造訪數」基線。

對於可新增的步驟數或是可使用的維度數並沒有限制。

您可以對維度、量度及區段進行路徑分析。例如，假設某人正在同一頁面上查看鞋子和上衣，而在下一頁他改為查看上衣和襪子。來自鞋子的下一個產品流量報告會是上衣和襪子，「而非」上衣。

## 使用

1. 新增 ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL 流失]**&#x200B;視覺效果。請參閱[新增視覺效果至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 從「頁面」維度將頁面（例如home）拖曳至「*新增接觸點*」下拉式功能表。

   ![將首頁從首頁維度拖曳至新增接觸點欄位。](assets/fallout-drag.png)

   將滑鼠停留在接觸點上，以查看流失和有關該層級的其他資訊，例如接觸點的名稱和該點的人數。並查看該接觸點的成功率 (並將成功率與其他接觸點進行比較)。

   長條灰色部分裡頭圈起來的數字，是接觸點之間的流失 (不是該點的整體流失)。**[!UICONTROL 接觸點 %]** 顯示流失報告中從先前步驟到目前步驟的成功區間。

   您也可以將單次頁面新增至流失報告，而不是整個維度。按一下頁面維度上的「![ChevronRight](/help/assets/icons/ChevronRight.svg)」，以挑選要新增至流失報告的特定頁面。

1. 繼續新增接觸點，直到完成您的序列。

   您可以透過拖曳一個或多個其他元件至某個接觸點，以&#x200B;**合併多個接觸點**。

   >[!NOTE]
   >
   >多個區段必須以 AND 連結，但多個項目 (例如維度項目和量度) 則須以 OR 連結。

   ![頁面:CamerRoll或頁面：反白的相機接觸點。](assets/fallout-or.png)

1. 您也可以在路徑內&#x200B;**將個別觸控點限制為下一個事件** (而非「*最終*」)。在各接觸點下方，具有「**[!UICONTROL 最終路徑]**」和「**[!UICONTROL 下一個事件]**」選項的選擇器，如下所示：

   ![「所有造訪數」視圖顯示醒目提示的「最終路徑」選項。](assets/fallout-nexthit.png)

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 最終路徑]** (預設) | 列入計數的人員&#x200B;*最終*&#x200B;會登陸至路徑的下一個頁面，但不一定會至下一個事件。 |
   | **[!UICONTROL 下一個事件]** | 將登陸下一個事件路徑下個頁面的人員會被計入。 |


## 設定 {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="流失容器"
>abstract="選取容器以進行路徑分析。此選項有助於您了解參與度，並將分析範圍限制在所選容器內。"

作為視覺效果的一部分，可以使用特定設定。

| 流失容器 | 說明 |
|--- |--- |
| **[!UICONTROL 工作階段]**&#x200B;或&#x200B;**[!UICONTROL 人員]** | 在[!UICONTROL 工作階段]和[!UICONTROL 人員]之間切換，以進行人員路徑分析。預設為[!UICONTROL 人員]。這些設定可協助您了解人員層級的人員參與程度 (跨工作階段)，或是將分析限制為單一工作階段。 |


## 內容選單

作為視覺效果的一部分，可使用特定內容選單選項。

![流失選項](assets/fallout-options.png)

| 選項 | 說明 |
|--- |--- |
| **[!UICONTROL 趨勢接觸點]** | 在折線圖中查看接觸點的趨勢資料，其中包含一些預先建立的異常偵測資料。 |
| **[!UICONTROL 趨勢接觸點 (%)]** | 總流失百分比趨勢。 |
| **[!UICONTROL 所有接觸點趨勢 (%)]** | 在同一圖表上顯示流失中所有接觸點的百分比趨勢 (若已包括&#x200B;**[!UICONTROL 所有人員]**&#x200B;則除外)。 |
| **[!UICONTROL 在此接觸點劃分區間]** | 如果人員繼續進入下一個接觸點，可檢視人員在兩個接觸點 (此接觸點和下一個接觸點) 之間所做的動作。這樣會建立自由表格，顯示您的維度。 您可以取代表格的尺寸和其他元素。 例如，標示為&#x200B;**[!UICONTROL 區間：所有人員>頁面等於任何首頁]**，並包含&#x200B;**[!UICONTROL 頁面]**&#x200B;作為維度，以及以&#x200B;**[!UICONTROL 僅限專案的快速區段]**&#x200B;分割的[人員](/help/components/segments/seg-quick.md) **[!UICONTROL 區間：所有人員>頁面等於任何首頁]**&#x200B;作為量度。 檢查區段以瞭解如何決定遞補區段。 |
| **[!UICONTROL 在此接觸點劃分流失]** | 檢視未透過funnel的人，在選取步驟後立即做了什麼事。 這樣會建立自由表格，顯示您的維度。 您可以取代表格的尺寸和其他元素。 例如，標示為&#x200B;**[!UICONTROL 流失：人物>頁面等於任何首頁]**，並包含&#x200B;**[!UICONTROL 頁面]**&#x200B;作為維度，以及以&#x200B;**[!UICONTROL 僅限專案的快速區段]** [流失：所有訪客>頁面等於任何首頁](/help/components/segments/seg-quick.md)區段作為量度的分段&#x200B;**[!UICONTROL 人物]**。 檢查區段以瞭解如何判斷流失區段。 |
| **[!UICONTROL 從接觸點建立區段]** | 從選取的接觸點建立新的區段。 |

>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[視覺化內容選單](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

