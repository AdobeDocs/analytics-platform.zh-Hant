---
description: 瞭解如何將視覺效果連結至自由表格資料來源。
keywords: Analysis Workspace;將視覺效果同步至資料來源
title: 在Analysis Workspace中管理視覺效果資料來源
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 22%
---
# 管理資料來源 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="鎖定選取項目"
>abstract="啟用此設定，即可將視覺效果鎖定在資料來源中所選的位置或所選的項目。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="顯示表格"
>abstract="選取「**[!UICONTROL 顯示表格]**」會為您目前的視覺效果產生新的資料來源，並將其與原始資料來源分開。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="顯示表格"
>abstract="選取「**[!UICONTROL 顯示表格]**」可為您目前的視覺效果產生新的資料來源，且與原始資料來源分開。"

Analysis Workspace中的每個視覺效果都根據資料來源，通常是自由表格。 同步視覺效果可讓您控制哪些自由表格或資料來源對應至視覺效果，以及視覺效果是否仍鎖定至該表格中的特定列。

>[!TIP]
>
>您可以藉由視覺化標題旁的 ![StatusOrange](/help/assets/icons/StatusOrange.svg) 色彩得知哪些視覺效果為相關。 相符色彩表示視覺效果是根據相同的資料來源。
>

## 設定資料來源設定 {#configure}

1. 在Analysis Workspace中，前往您要設定其資料來源或鎖定設定的視覺效果。

1. 將滑鼠停留在視覺效果上，然後選取&#x200B;**[!UICONTROL 設定]**&#x200B;圖示![設定](/help/assets/icons/Setting.svg)。

1. 選取&#x200B;**[!UICONTROL 資料來源]**&#x200B;標籤。

   ![顯示資料來源、連結的視覺效果和鎖定選取範圍設定的資料來源標籤。](assets/lock-selection.png)

1. 設定下列任一設定：

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 資料來源]** | 選取視覺效果所在的資料來源。 |
   | **[!UICONTROL 連結的視覺效果]** | 列出連結至資料來源（自由表格）的所有視覺效果。 |
   | **[!UICONTROL 顯示資料來源]** | 顯示或隱藏對應至視覺效果的資料來源（自由表格）。 |
   | **[!UICONTROL 鎖定選取專案]** | 將視覺效果鎖定至資料來源中目前選取的列，然後選取&#x200B;**[!UICONTROL 選取的位置]**&#x200B;或&#x200B;**[!UICONTROL 選取的專案]**。 請參閱[鎖定選取專案](#lock-selection)。 |

## 鎖定選取項目 {#lock-selection}

鎖定選取範圍可讓視覺效果聚焦於您在資料來源中選取的列，即使表格變更亦然。 例如，當您排序或篩選表格、變更其日期範圍或套用區段時，表格會變更。 鎖定的視覺效果在其標題旁顯示![LockClosed](/help/assets/icons/LockClosed.svg)。

如果資料來源中的區段、維度或量度變更，且鎖定的資料不再顯示，請選取&#x200B;**[!UICONTROL 顯示表格]**&#x200B;以產生新的視覺效果資料來源（與原始資料來源分開）。

鎖定選取範圍時，請選擇下列其中一個選項：

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 選取的職位]** | 將視覺效果鎖定至資料來源中所選列的&#x200B;**位置**。 這些位置會繼續視覺化，即使其中的專案有所變更。 例如，選取此選項可一律顯示資料來源中前五個促銷活動名稱，無論其屬於哪個促銷活動。<br><br>如果您鎖定劃分列，而這些列已不在表格中，則不會顯示視覺效果。 若要再次顯示，請更新表格（例如其日期範圍、區段或篩選器）或更新鎖定選取範圍。 |
| **[!UICONTROL 選取的專案]** | 將視覺效果鎖定至資料來源中選取的特定&#x200B;**專案**。 即使這些專案在表格中的排名改變，仍會繼續將其視覺化。 例如，選取此選項可一律顯示相同的五個行銷活動名稱，無論其排名為何。 |
