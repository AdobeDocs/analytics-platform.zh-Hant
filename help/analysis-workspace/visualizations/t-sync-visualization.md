---
description: 同步視覺效果可讓您控制哪些資料表或資料來源會對應至視覺效果。
keywords: Analysis Workspace, 將視覺效果同步至資料來源
title: 管理資料來源
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 388e008f4ee092dd8224bfacd020cdf762d4fb82
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 17%

---

# 管理資料來源 {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection"
>title="鎖定選取範圍"
>abstract="啟用此設定可將視覺效果鎖定至資料來源中的選定位置或選定專案。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_lockselection_showtable"
>title="顯示表格"
>abstract="選取&#x200B;**[!UICONTROL 顯示表格]**&#x200B;將會為您目前的視覺效果產生新的資料來源，與原始資料來源分開。"

<!-- markdownlint-enable MD034 -->



同步視覺效果可讓您控制哪些資料表或資料來源會對應至視覺效果。

>[!TIP]
>
>您可以藉由視覺效果標題旁的![StatusOrange](/help/assets/icons/StatusOrange.svg)顏色來分辨哪些視覺效果為相關。 相符色彩表示視覺效果是根據相同的資料來源。
>

您可以顯示或隱藏資料來源。 您也可以將選取專案鎖定至選取的位置或選取的專案。 這些設定會決定當新資料進入時視覺效果的變更方式 (或不變更)。

![資料Source選項對話方塊，顯示下一節所述的選項。](assets/lock-selection.png)


| 選項 | 說明 |
|--- |--- |
| **[!UICONTROL 資料來源]** | 從下拉式選單中選取視覺效果所根據的資料來源。 |
| **[!UICONTROL 連結的視覺效果]** | 列出所有連結的視覺效果。 套用至資料來源（自由表格）。 |
| **[!UICONTROL 顯示資料來源]** | 可讓您顯示或隱藏對應至視覺效果的資料來源（自由表格）。 |
| **[!UICONTROL 鎖定選取項目]** | 選取此選項可將視覺效果![LockClosed](/help/assets/icons/LockClosed.svg)鎖定至目前在對應的資料表中選取的資料。 啟用後，請選取：  <ul><li>**選取的位置**：視覺效果已鎖定在對應資料表中選取的&#x200B;**位置**&#x200B;上。 即使這些位置中的特定專案變更（例如，由於排序或篩選），這些位置仍會繼續視覺化。 例如，如果您想要一直在此視覺效果中顯示在資料來源排名前五的行銷活動名稱，請選取此選項。 無論顯示哪個促銷活動名稱，</li> <li>**選取的專案**：視覺效果已在對應資料表中目前選取的特定&#x200B;**專案**&#x200B;上鎖定。 這些專案會繼續視覺化，即使它們在表格中的專案之間變更了排名。 例如，如果您想要在任何時候都顯示這個視覺效果中資料來源列出的五個特定促銷活動名稱，請選取此選項。 無論這些行銷活動名稱的排名如何。</li></ul>如果視覺效果已鎖定至所連線資料表中不再可見的資料，您可以產生新的表格。 選取&#x200B;**[!UICONTROL 顯示資料表]**，為您目前的視覺效果產生新的資料來源，與原始資料來源分開。 |
