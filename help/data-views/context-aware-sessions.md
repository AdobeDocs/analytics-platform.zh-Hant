---
title: 內容感知作業
description: 資料檢視中的設定，可用於定義內容感知作業。
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 3%

---


# 內容感知作業

資料檢視中的內容感知作業階段會變更Customer Journey Analytics從您連線中的資料計算作業階段的方式。

在 [!UICONTROL 設定] 資料檢視的索引標籤中，您可以透過任何方式定義工作階段，以符合個人與您的數位體驗的互動方式。 內容感知作業定義是非破壞性的，不會改變基礎資料。 您可以將多個資料檢視（每個都具有其特定的內容感知工作階段定義）設定為工作區專案的基礎。

若要為資料檢視定義工作階段的前後關聯：

1. 選取 **[!UICONTROL 資料檢視]** 在Customer Journey Analytics UI中。

1. 建立新的資料檢視或編輯現有的資料檢視。 另請參閱 [建立或編輯資料檢視](create-dataview.md) 以取得詳細資訊。

1. 選取「**[!UICONTROL 設定]**」標籤。底下 [!UICONTROL 工作階段設定]：

   1. 輸入值 **[!UICONTROL 工作階段逾時]** 在 [!UICONTROL 分鐘]， [!UICONTROL 小時]， [!UICONTROL 天]，或 [!UICONTROL 周]. 工作階段逾時決定在開始新工作階段之前，工作階段可以閒置多久（不會發生事件）。

   2. 從中選擇量度 **[!UICONTROL 將量度拖放到這裡]** 清單底下 [!UICONTROL 使用量度開始新工作階段]. 或者，您可以從左側窗格將量度拖放至 **[!UICONTROL 放置量度欄位]**. 選取的量度會定義新工作階段的開始。 您可以定義多個量度。

1. 選取 **[!UICONTROL 儲存]** 或 **[!UICONTROL 儲存並完成]** 以儲存前後關聯感知作業階段定義。

