---
title: Customer Journey Analytics 中有什麼元件？
description: 了解 Customer Journey Analytics 提供哪些元件，以及如何在報告中使用這些元件。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 100%

---

# 元件概觀

元件是 Customer Journey Analytics 中的功能，可用於視覺化呈現 (例如自由格式表格) 或與報告功能搭配使用。

若要從 Customer Journey Analytics 主介面管理元件：

1. 從頂端列選取&#x200B;**[!UICONTROL 元件]**。
1. 選取&#x200B;**[!UICONTROL 元件]**&#x200B;以查看您可以管理的元件概觀，或直接從選單中選取您要管理的元件。

您可以管理下列元件：

* [區段](segments/seg-overview.md)：建置、管理、共用強大且重點明確的客群區段，並將其套用到您的報告中。區段讓您根據特性或互動來識別人員子集。
* [計算量度](calc-metrics/calc-metr-overview.md)：將量度和公式作為新元件用於報告中
* [日期範圍](date-ranges/create.md)：自訂和調整 Analysis Workspace 提供的日期範圍。
* [註解](/help/components/annotations/overview.md)：將內容相關的資料細微差別和深入分析傳達給您的組織。
* [智慧提醒](/help/components/c-intelligent-alerts/intelligent-alerts.md)：讓您根據變更的百分比或特定資料點來接收通知。
* [已排程的專案](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager)：管理您已排程的專案。
* [偏好設定](/help/analysis-workspace/user-preferences.md)：管理 Analysis Workspace 的偏好設定。
* [客群](/help/components/audiences/audiences-overview.md)：利用 Customer Journey Analytics 建立客群並發佈到 Experience Platform 中的[Real-Time Customer Data Platform](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/profile/home)，以利目標市場選擇和個人化。
* [匯出](/help/components/exports/manage-export-locations.md)：管理您的匯出帳戶和地點。


## Analysis Workspace 元件

Analysis Workspace 中的元件由量度、維度、區段和日期範圍組成，您可以將它們拖放至 Workspace 專案的面板和視覺效果中。您建立的自訂元件會新增至這些面板，例如計算量度或自訂日期範圍。

若要存取元件面板，請選取在按鈕面板中的![Curate](/help/assets/icons/Curate.svg)**[!UICONTROL 元件]**。

![Workspace panel highlighting the Components icon in the left-rail](assets/components.png)

請參閱[建立專案](/help/analysis-workspace/home.md)，以了解在專案中如何使用元件的詳細資訊。


## 管理元件 {#actions}

您可以使用 Analysis Workspace **[!UICONTROL 元件]**&#x200B;選單快速建立新元件。請參閱[Analysis Workspace 選單](/help/analysis-workspace/home.md#menu)以了解更多詳細資訊。

您可以管理元件 (個別或選取多個元件)。

1. 選取一個或多個元件。

1. 從內容選單，或從![MoreVertical](/help/assets/icons/MoreVertical.svg)「元件」動作按鈕 (位於元件頂端) 選取下列其中一項動作。


   >[!TIP]
   >
   >按住 **[!UICONTROL Shift]** 或按住 **[!UICONTROL Command]** (macOS 版) 或 **[!UICONTROL Ctrl]** (Windows 版)，即可選取多個元件。


   ![「元件動作」清單，顯示「標記」、「我的最愛」、「核准」、「共用」和「刪除」。](assets/component-menu.gif){width=100%}

   | 元件動作 | 說明 |
   |--- |--- |
   | ![Label](/help/assets/icons/Label.svg)[!UICONTROL **標記**] | 以套用標記的方式組織或管理元件。然後您可以透過選取![Filter](/help/assets/icons/Filter.svg)篩選或輸入 `#`，依左側面板的標記進行搜尋。標記也會作為元件管理員中的篩選器。 |
   | ![Star](/help/assets/icons/Star.svg)[!UICONTROL **最愛項目**] | 將元件新增至最愛項目清單。如同標記，您可以依左側面板的「最愛項目」搜尋，並在元件管理員中依這些條件篩選。 |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL 取消最愛項目]** | 將元件從最愛項目清單移除。 |
   | ![Checkmark](/help/assets/icons/Checkmark.svg)[!UICONTROL **核准**] | 將元件標示為「已核准」，向您的使用者表示此元件已獲得組織核准。如同標記，您可以在左側面板中依已批准進行搜尋和篩選。![Checkmark](/help/assets/icons/Checkmark.svg)識別已核准的元件。 |
   | ![Share](/help/assets/icons/ShareAlt.svg)[!UICONTROL **共用**] | 缃元件提供給組織中的用戶共用。此選項僅適用於自訂元件，例如區段或計算量度。 |
   | ![Delete](/help/assets/icons/Delete.svg)[!UICONTROL **刪除**] | 刪除您不再需要的元件。 此選項僅適用於自訂元件，例如區段或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。如需範例，請參閱[管理區段](/help/components/segments/seg-manage.md)。

## 管理元件清單

您可以在 Analysis Workspace 的左側面板中搜尋、篩選元件清單並進行排序，以找到特定元件。

### 搜尋

1. 選取左側面板中的&#x200B;**元件** ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 在搜尋欄位中開始輸入要用於專案中的元件的名稱。

   顏色和圖示識別元件類型。**維度**![維度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)是橘色的，**區段**![區段圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)是藍色的，**日期範圍**![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)是紫色的，而&#x200B;**量度**![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)是綠色的。<br/>Adobe 圖示 ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) 表示計算量度範本或區段範本。計算機圖示![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 表示管理員在您組織中所建立的計算量度。

3. 從下拉式選單中選取元件。

### 篩選器

1. 在左側面板中選取&#x200B;**元件**&#x200B;圖示![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。


2. 選取&#x200B;**篩選條件**![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，或在搜尋欄位中輸入 `#`。

3. 選取以下任一篩選條件選項以篩選元件清單：

   | 圖示 | 篩選條件選項 | 說明 |
   |---------|---|----------|
   | ![Checkmark](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 已核准]** | 僅顯示標記為由管理員核准的元件。 |
   | ![Star](/help/assets/icons/Star.svg) | **[!UICONTROL 我的最愛]** | 僅顯示「我的最愛」清單中的元件。<br/>如需有關將元件新增到最愛項目清單的資訊，請參閱「[管理元件](#manage-components)」。 |
   | ![Dimensions](/help/assets/icons/Dimensions.svg) | **[!UICONTROL 維度]** | 僅顯示維度的元件。 |
   | ![Event](/help/assets/icons/Event.svg) | **[!UICONTROL 量度]** | 僅顯示量度的元件。 |
   | ![Segmentation](/help/assets/icons/Segmentation.svg) | **[!UICONTROL 區段]** | 僅顯示屬於區段的元件。 |
   | ![Calendar](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日期範圍]** | 僅顯示日期範圍的元件。 |
   | ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL *標記名稱&#x200B;*]** | 僅顯示具有特定已選取標記的元件。Adobe 範本有一個專用標記，是來自 Adobe 的[預設計算量度](/help/components/calc-metrics/default-calcmetrics.md)。 |

   在篩選器中選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除此篩選器。

4. 您可以選擇排序元件清單，如[對元件清單進行排序](#sort-the-component-list)中所述。

### 排序

<!-- {{release-limited-testing-section}}-->

1. (可選) 依據[篩選元件清單](#filter-the-component-list)中的說明，對元件清單套用任何篩選條件。

2. 選取左側面板中的&#x200B;**元件** ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)」。

3. 選取&#x200B;**排序**![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取以下任一篩選器選項，將元件清單排序。

提供下列排序選項：

{{components-sort-options}}

## 存取權限

在 Analysis Workspace 中，管理員可以[組織](/help/analysis-workspace/curate-share/curate.md)在報告中向使用者公開的元件。
