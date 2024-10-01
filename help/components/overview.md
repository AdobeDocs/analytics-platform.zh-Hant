---
title: Customer Journey Analytics 中有什麼元件？
description: 了解 Customer Journey Analytics 提供哪些元件，以及如何在報告中使用這些元件。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 33%

---

# 元件概觀

元件是Customer Journey Analytics中的功能，可用於視覺效果（例如自由表格）或補充報表功能。

若要從主要Customer Journey Analytics介面管理元件：

1. 從頂端列選取&#x200B;**[!UICONTROL 元件]**。
1. 選取「**[!UICONTROL 元件]**」以檢視您可以管理的元件概觀，或直接從功能表選取您要管理的元件。

您可以管理下列元件：

* [篩選器](filters/filters-overview.md)：建立、管理、共用強大的且重點明確的客群篩選，並將其套用到您的報告中。篩選器可讓您根據特性或互動來識別人員的子集。
* [計算量度](calc-metrics/calc-metr-overview.md)：將量度和公式作為新元件用於報告中
* [日期範圍](date-ranges/create.md)：自訂和調整 Analysis Workspace 提供的日期範圍。
* [註解](/help/components/annotations/overview.md)：將內容相關的資料細微差別和深入解析傳達給您的組織。
* [智慧型警報](/help/components/c-intelligent-alerts/intelligent-alerts.md)：可讓您根據變更的百分比或特定資料點接收通知。
* [已排程專案](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager)：管理您的已排程專案。
* [偏好設定](/help/analysis-workspace/user-preferences.md)：管理Analysis Workspace的偏好設定。
* [對象](/help/components/audiences/audiences-overview.md)：在Customer Journey Analytics中建立對象，並將其發佈到Experience Platform中的[Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home)，以進行目標定位和個人化。
* [匯出](/help/components/exports/manage-export-locations.md)：管理您的匯出帳戶和位置。


## Analysis Workspace 元件

Analysis Workspace中的元件包含量度、維度、篩選器和日期範圍，您可以將這些元件拖放到Workspace專案的面板和視覺效果上。 您建立的自訂元件會新增至這些面板，例如計算量度或自訂日期範圍。

若要存取「元件」面板，請在按鈕面板中選取![組織](/help/assets/icons/Curate.svg) **[!UICONTROL 元件]**。

![Workspace 面板，醒目提示左側邊欄中的「元件」圖示](assets/components.png)

如需如何在專案中使用元件的詳細資訊，請參閱[建立專案](/help/analysis-workspace/home.md)。


+++ 觀看說明元件可能性的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## 管理元件 {#actions}

您可以使用Analysis Workspace中的&#x200B;**[!UICONTROL 元件]**&#x200B;功能表快速建立新元件。 如需詳細資訊，請參閱[Analysis Workspace功能表](/help/analysis-workspace/home.md#menu)。

您可以管理元件（個別或選取多個元件）。

1. 選取一或多個元件。

1. 從內容功能表或![MoreVertical](/help/assets/icons/MoreVertical.svg)元件動作按鈕（位於元件頂端），選取下列其中一個動作。


   >[!TIP]
   >
   >您可以按住&#x200B;**[!UICONTROL Shift]**，或按住&#x200B;**[!UICONTROL Command]** (在macOS上)或&#x200B;**[!UICONTROL Ctrl]** （在Windows上）來選取多個元件。


   ![元件動作清單顯示「標籤」、「我的最愛」、「核准」、「共用」和「刪除」。](assets/component-menu.gif){width=100%}

   | 元件動作 | 說明 |
   |--- |--- |
   | ![標籤](/help/assets/icons/Label.svg) [!UICONTROL **標籤**] | 以套用標記的方式組織或管理元件。然後，您可以選取![篩選器](/help/assets/icons/Filter.svg)篩選器或輸入`#`，依左側面板中的標籤進行搜尋。 標籤也會當作元件管理員中的篩選器。 |
   | ![星星](/help/assets/icons/Star.svg) [!UICONTROL **我的最愛**] | 將元件新增至我的最愛清單。如同標籤，您可以依左側面板中的「我的最愛」搜尋，並在元件管理員中這些條件篩選。 |
   | ![星形大綱](/help/assets/icons/StarOutline.svg) **[!UICONTROL 取消最愛]** | 從您的最愛清單中移除元件。 |
   | ![核取記號](/help/assets/icons/Checkmark.svg) [!UICONTROL **核准**] | 將元件標示為「已核准」，向您的使用者表示此元件已獲得組織核准。如同標籤，您可以依左側面板的「已核准」進行搜尋和篩選。 ![核取記號](/help/assets/icons/Checkmark.svg)可識別核准的元件。 |
   | ![共用](/help/assets/icons/ShareAlt.svg) [!UICONTROL **共用**] | 與組織中的使用者共用元件。此選項僅適用於自訂元件，例如篩選器或計算量度。 |
   | ![刪除](/help/assets/icons/Delete.svg) [!UICONTROL **刪除**] | 刪除您不再需要的元件。此選項僅適用於自訂元件，例如篩選器或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。例如，請參閱[管理篩選器](/help/components/filters/manage-filters.md)。

## 管理元件清單

您可以在Analysis Workspace的左側面板中搜尋、篩選和排序元件清單，以找出特定元件。

### 搜尋

1. 在左側面板中選取&#x200B;**元件** ![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 在搜尋欄位中開始輸入要用於專案中的元件的名稱。

   顏色和圖示可識別元件型別。 **Dimension** ![Dimension圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)為橘色，**篩選器** ![篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)為藍色，**日期範圍** ![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)為紫色，且&#x200B;**量度** ![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)為綠色。<br/>Adobe圖示![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg)表示計算量度範本或篩選範本。 計算器圖示![計算器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)表示貴組織的管理員已建立的計算量度。

3. 從下拉式清單中選取元件。

### 篩選器

1. 在左側面板中選取&#x200B;**元件**&#x200B;圖示![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 選取&#x200B;**篩選器** ![資料字典篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，或在搜尋欄位中輸入`#`。

3. 選取以下任一篩選器選項以篩選元件清單：

   | 圖示 | 篩選器選項 | 說明 |
   |---------|---|----------|
   | ![核取記號](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 已核准]** | 僅顯示標記為由管理員核准的元件。 |
   | ![顆星](/help/assets/icons/Star.svg) | **[!UICONTROL 我的最愛]** | 僅顯示「我的最愛」清單中的元件。<br/>如需有關新增元件至您最愛清單的資訊，請參閱[管理元件](#manage-components)。 |
   | ![維度](/help/assets/icons/Dimensions.svg) | **[!UICONTROL 維度]** | 僅顯示維度的元件。 |
   | ![事件](/help/assets/icons/Event.svg) | **[!UICONTROL 量度]** | 僅顯示量度的元件。 |
   | ![區段](/help/assets/icons/Segmentation.svg) | **[!UICONTROL 篩選器]** | 僅顯示篩選器的元件。 |
   | ![行事曆](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日期範圍]** | 僅顯示屬於日期範圍的元件。 |
   | ![標籤](/help/assets/icons/Label.svg) | **[!UICONTROL *標籤名稱&#x200B;*]** | 僅顯示具有特定選定標籤的元件。 專用標籤可用於Adobe範本，其為來自Adobe的[預設計算量度](/help/components/calc-metrics/default-calcmetrics.md)。 |

   在篩選中選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除篩選。

4. 您可以選擇排序元件清單，如[排序元件清單](#sort-the-component-list)中所述。

### 排序

<!-- {{release-limited-testing-section}}-->

1. (可選) 依據[篩選元件清單](#filter-the-component-list)中的說明，對元件清單套用任何篩選器。

2. 在左側面板中選取&#x200B;**元件** ![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

3. 選取&#x200B;**排序** ![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取下列任一篩選選項來排序元件清單。

可用的排序選項如下：

{{components-sort-options}}

## 存取許可權

在Analysis Workspace中，管理員可以[組織](/help/analysis-workspace/curate-share/curate.md)哪些元件在報表中向使用者公開。
