---
title: 動態與靜態維度專案
description: 如何與表格中的動態和靜態維度項目互動
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 49%

---

# 動態和靜態維度專案

在自由表格中，列和欄可以包含各種元件值。這些值可以是動態（隨時間而改變）或靜態（不隨時間而改變），具體取決於您要建立的分析。

## 動態維度項目

動態維度專案會隨著時間變更，取決於自由表格中排序的量度。 分析特定時段排名最前的項目時，偏好使用動態維度項目。

將維度放入自由表格中時，會傳回動態列。動態列代表對應至指定量度和時段之維度的排名最前專案。 您也可以將維度放入自由表格欄中，維度會自動展開至排名前 5 的維度項目。

例如，將「瀏覽器類型」維度拖曳至表格時，頂端的「瀏覽器類型」維度項目 (例如 Microsoft、Apple、Google 等)會以動態方式傳回表格列。如果放入欄中，排名前 5 的「瀏覽器類型」維度項目會以動態方式傳回。

動態維度專案具有列篩選器選項![篩選器](/help/assets/icons/Filter.svg)和![關閉](/help/assets/icons/Close.svg)，並且&#x200B;**不**&#x200B;有鎖定![LockClosed](/help/assets/icons/LockClosed.svg)。 <!--do they have the lock icon? -->當您按一下動態維度專案旁的![關閉](/help/assets/icons/Close.svg)時，會自動套用篩選器。 如需將篩選套用至表格的詳細資訊，請參閱[篩選及排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。


![反白顯示篩選圖示的自由表格。](assets/dynamic-items.png)

## 靜態維度項目

靜態維度項目不會隨時間改變；它們是固定元件，一律會在自由表格中傳回。想要一律分析相同項目時，偏好使用靜態維度項目，不論該項目是特定行銷活動或一週中的特定幾天皆然。

每當您手動選取特定元件值（維度、量度、篩選器、日期範圍）並放入表格時，結果會是列或欄的靜態清單。

例如，拖曳至特定的「瀏覽器類型」項目 (例如 Microsoft 和 Apple) 時，這 2 個特定項目一律會被提取至表格中。

如果您選擇從選取資料列的內容功能表選取&#x200B;**[!UICONTROL 僅顯示選取的資料列]**，也可以建立靜態維度專案。

靜態維度項目&#x200B;**沒有**&#x200B;列篩選選項。而是每個專案都有![LockClosed](/help/assets/icons/LockClosed.svg)和![Close](/help/assets/icons/Close.svg)。 選取![關閉](/help/assets/icons/Close.svg)以從資料表中移除該維度專案。

![顯示瀏覽器型別和Microsoft列（含鎖定圖示）的自由格式表格注意：此維度專案是靜態的，不會隨時間變更。](assets/static-items.png)

## 混合維度項目

可以將來自不同維度的維度項目新增至相同的表格。在這些情況下，資料列標題會顯示&#x200B;**[!UICONTROL 混合Dimension]**。 這些維度項目為靜態。例如，從「瀏覽器群組」維度新增特定維度專案，以及從「瀏覽器名稱」維度新增其他維度專案。

![反白顯示混合Dimension資料行的自由表格。](assets/mixed-dimensions.png)

## 自由表格總計列

自由表格總計列中動態和靜態列的行為不相同。根據預設：

* 動態列在伺服器端加總，並去除重複量度，例如工作階段或人員。
* 靜態列則在用戶端加總，且&#x200B;**不會**&#x200B;去除重複量度。若要在伺服器端計算總計列，請將「列」設定更改為&#x200B;**「顯示總計」**。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=zh-hant)
