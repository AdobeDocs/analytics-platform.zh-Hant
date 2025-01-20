---
title: 工作階段設定
description: 您可使用資料檢視中的設定來定義工作階段長度，並定義啟動新工作階段的觸發器
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: ht
source-wordcount: '454'
ht-degree: 100%

---

# 工作階段設定 {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="資料預覽"
>abstract="將此資料檢視的資料與連線的資料進行比較。此預覽百分比是根據連線中&#x200B;**過去 90 天**&#x200B;的總數。<br><br/>如果預覽未載入，您的連線可能仍在進行回填。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


在 Customer Journey Analytics 中，您可以用任何方式定義工作階段，來配合人員與您所有數位體驗的互動方式。您可以在資料視圖中配置工作階段設定。

工作階段定義是非破壞性的，不會改變底層資料。您可以將多個資料檢視設定為 Workspace 專案的基礎 (每個資料檢視都有其各自具體的工作階段定義)。

若要在資料視圖中定義工作階段的內容：

1. 在 Customer Journey Analytics 中，選取「**[!UICONTROL 資料檢視]**」。

2. 建立新的或編輯現有的資料檢視。如需詳細資訊，請參閱[建立或編輯資料檢視](create-dataview.md)。

3. 選取「**[!UICONTROL 設定]**」索引標籤。在「[!UICONTROL 工作階段設定]」下：

   1. 輸入「**[!UICONTROL 工作階段逾時]**」的值，以[!UICONTROL 分鐘]、[!UICONTROL 小時]、[!UICONTROL 天]或[!UICONTROL 週]為單位。工作階段逾時決定在開始新工作階段之前工作階段可以閒置 (沒有事件發生) 多少時間。

      如果您有興趣分析大部份的線上互動情形，請使用較短的工作階段逾時 (例如 30 分鐘)。例如，分析那些瀏覽您線上商店產品頁面的輪廓，了解他們是否確實將產品加入其購物車或購買。

      如果您要結合線上和離線資料，並希望分析購買您一種或多種產品的客戶，了解他們是否在購買後的前三個月內打電話給您的聯絡中心，請使用較長的工作階段逾時 (例如 3 個月)。


   2. 在「**[!UICONTROL 以量度啟動新工作階段]**」下的「**[!UICONTROL 在這裡放置量度]**」清單中選取一個量度。或者，您可以從左側窗格中將量度拖放到「**[!UICONTROL 放置量度欄位]**」。所選量度定義新工作階段開始。您可以定義多個量度。

      您可以使用任何類型的量度來定義新工作階段。例如，假設您希望輪廓每次啟動您的行動應用程式時定義一個新的工作階段。在「**[!UICONTROL 資料檢視]**>**[!UICONTROL 元件]**」中，您定義一個類型度量的元件，並將其命名為「**[!UICONTROL 啟動]**」(根據 **[!UICONTROL appInteraction]****[!UICONTROL 名稱]**&#x200B;結構欄位)。您進一步指定「**[!UICONTROL 啟動]**」量度元件僅限在值符合 `launch` 時才計算該值。

      ![應用程式互動量度元件啟動](assets/component-launches.png)

      然後拖放，或選取「**[!UICONTROL 啟動]**」量度作為定義新工作階段的量度。

      ![工作階段設定啟動](assets/session-settings-launches-metric.png)



4. 選取「**[!UICONTROL 儲存]**」或「**[!UICONTROL 儲存並完成]**」，以儲存工作階段設定定義。
