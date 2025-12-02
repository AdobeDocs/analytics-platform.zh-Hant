---
description: 瞭解如何將自由表格或資料來源同步至對應的視覺效果。
keywords: Analysis Workspace, 將視覺效果同步至資料來源
title: 管理資料來源
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 89%

---

# 管理資料來源 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="鎖定選取項目"
>abstract="啟用此設定，即可將視覺效果鎖定在資料來源中所選的位置或所選的項目。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="顯示表格"
>abstract="選取「**[!UICONTROL 顯示表格]**」將為您目前的視覺效果產生新的資料來源，並將其與原始資料來源分開。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="顯示表格"
>abstract="選取「**[!UICONTROL 顯示表格]**」可為您目前的視覺效果產生新的資料來源，且與原始資料來源分開。"


同步視覺效果可讓您控制哪些自由表格或資料來源會對應至視覺效果。

>[!TIP]
>
>您可以藉由視覺化標題旁的 ![StatusOrange](/help/assets/icons/StatusOrange.svg) 色彩得知哪些視覺效果為相關。相符色彩表示視覺效果是根據相同的資料來源。
>

您可以顯示或隱藏資料來源。您也可以將選取項目鎖定到選定的位置或選定的項目。這些設定會決定當新資料進入時視覺效果的變更方式 (或不變更)。

![資料來源選項對話框會顯示下一節所述的選項。](assets/lock-selection.png)


| 選項 | 說明 |
|--- |--- |
| **[!UICONTROL 資料來源]** | 從下拉式選單中選取視覺效果所根據的資料來源。 |
| **[!UICONTROL 連結的視覺效果]** | 列出所有連結的視覺效果。適用於資料來源 (自由格式表格)。 |
| **[!UICONTROL 顯示資料來源]** | 可顯示或隱藏與視覺效果對應的資料來源 (自由格式表格)。 |
| **[!UICONTROL 鎖定選取項目]** | 選取此設選項，將視覺效果![鎖定](/help/assets/icons/LockClosed.svg)至相對應資料表中目前選取的資料。啟用後，請選取以下兩者其中之一：  <ul><li>**選取的位置**：視覺效果已鎖定在相對應資料表內已選取的&#x200B;**位置**。即使這些位置上的特定項目發生變化 (例如由於排序或篩選)，這些位置仍將持續視覺化。例如，如果您想要隨時在此視覺效果中顯示資料來源所列的前五個活動名稱，請選擇此選項。無論哪個活動名稱顯示都一樣。</li> <li>**選取的項目**：視覺效果已鎖定在目前相對應資料表中選取的特定&#x200B;**項目**。即使這些項目在表格項目內的排名已變更，這些項目仍將持續視覺化。例如，如果您想要在此視覺效果中隨時顯示資料來源列出的相同五個活動名稱，請選擇此選項。無論這些活動名稱如何排名都一樣。</li></ul>如果視覺效果已鎖定到連線資料表內再也看不到的資料，則您可以產生一個新表格。選取「**[!UICONTROL 顯示表格]**」，可為您目前的視覺效果產生新的資料來源，並將其與原始資料來源分開。 |
