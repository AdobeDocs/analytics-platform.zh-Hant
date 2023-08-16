---
title: 工作階段設定
description: 資料檢視中的設定，您可以使用來定義工作階段的長度，以及起始新工作階段的觸發條件
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 25ff6feda28f0447927a52f44aed800cdd89e0cb
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 38%

---


# 工作階段設定

「資料」檢視中的工作階段設定會變更Customer Journey Analytics從您連線中的資料計算工作階段的方式。

在資料檢視的「**[!UICONTROL 設定]**」索引標籤中，您能夠以任何方式定義工作階段，以符合使用者與您數位體驗的互動方式。工作階段設定定義是非破壞性的，不會變更基礎資料。 您可以設定多個資料檢視（每個檢視都有各自的特定工作階段設定定義），作為工作區專案的基礎。

若要定義資料檢視之工作階段的內容：

1. 在 Customer Journey Analytics 中，選取「**[!UICONTROL 資料檢視]**」。

2. 建立新的或編輯現有的資料檢視。如需詳細資訊，請參閱[建立或編輯資料檢視](create-dataview.md)。

3. 選取「**[!UICONTROL 設定]**」索引標籤。在「[!UICONTROL 工作階段設定]」下：

   1. 輸入「**[!UICONTROL 工作階段逾時]**」的值，以[!UICONTROL 分鐘]、[!UICONTROL 小時]、[!UICONTROL 天]或[!UICONTROL 週]為單位。工作階段逾時決定在開始新工作階段之前工作階段可以閒置 (沒有事件發生) 多少時間。

      如果您想分析大部分的線上互動，請使用短的工作階段逾時（例如30分鐘）。 例如，分析造訪您線上商店產品頁面的設定檔是否確實將產品加入購物車，或甚至線上上購買。

      如果您要結合線上和離線資料，且想要分析已購買您的一或多個產品的客戶是否在購買後的前三個月內，致電您的聯絡中心，請使用長的工作階段逾時（例如3個月）。


   2. 在「**[!UICONTROL 以量度啟動新工作階段]**」下的「**[!UICONTROL 在這裡放置量度]**」清單中選取一個量度。或者，您可以從左側窗格中將量度拖放到「**[!UICONTROL 放置量度欄位]**」。所選量度定義新工作階段開始。您可以定義多個量度。

      您可以使用任何型別的量度來定義新的工作階段。 例如，假設您想在每次設定檔啟動您的行動應用程式時，定義新的工作階段。 在 **[!UICONTROL 資料檢視]** > **[!UICONTROL 元件]**，您可定義量度型別的元件，名為 **[!UICONTROL 啟動]**，根據 **[!UICONTROL appInteraction]** **[!UICONTROL 名稱]** 結構欄位。 您進一步指定 **[!UICONTROL 啟動]** 量度元件，以便在值符合時僅對值進行計數 `launch`.

      ![應用程式互動量度元件啟動次數](assets/component-launches.png)

      然後您拖放或選取 **[!UICONTROL 啟動]** 量度定義為定義新工作階段的量度。

      ![工作階段設定啟動](assets/session-settings-launches-metric.png)



4. 選取 **[!UICONTROL 儲存]** 或 **[!UICONTROL 儲存並完成]** 以儲存工作階段設定定義。

