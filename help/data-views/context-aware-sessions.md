---
title: 內容感知工作階段
description: 資料檢視中的設定可用來定義內容感知工作階段。
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 100%

---


# 內容感知工作階段

資料檢視中的內容感知工作階段會改變 Customer Journey Analytics 根據連線中的資料計算工作階段的方式。

在資料檢視的「[!UICONTROL 設定]」索引標籤中，您能夠以任何方式定義工作階段，以符合使用者與您數位體驗的互動方式。內容感知工作階段定義是非破壞性的，不會改變底層資料。您可以將多個資料檢視設定為 Workspace 專案的基礎；每個資料檢視都有具體的內容感知工作階段定義。

若要定義資料檢視之工作階段的內容：

1. 在 Customer Journey Analytics 中，選取「**[!UICONTROL 資料檢視]**」。

1. 建立新的或編輯現有的資料檢視。如需詳細資訊，請參閱[建立或編輯資料檢視](create-dataview.md)。

1. 選取「**[!UICONTROL 設定]**」索引標籤。在「[!UICONTROL 工作階段設定]」下：

   1. 輸入「**[!UICONTROL 工作階段逾時]**」的值，以[!UICONTROL 分鐘]、[!UICONTROL 小時]、[!UICONTROL 天]或[!UICONTROL 週]為單位。工作階段逾時決定在開始新工作階段之前工作階段可以閒置 (沒有事件發生) 多少時間。

   2. 在「[!UICONTROL 以量度啟動新工作階段]」下的「**[!UICONTROL 在這裡放置量度]**」清單中選取一個量度。或者，您可以從左側窗格中將量度拖放到「**[!UICONTROL 放置量度欄位]**」。所選量度定義新工作階段開始。您可以定義多個量度。

1. 選取「**[!UICONTROL 儲存]**」或「**[!UICONTROL 儲存並完成]**」以儲存內容感知工作階段定義。

