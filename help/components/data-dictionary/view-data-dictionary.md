---
description: Analysis Workspace 中的資料字典允許使用者對 Analysis Workspace 中的各種元件建立目錄和追蹤，包括其預定用途、已核准的元件、重複的元件等等。
title: 檢視資料字典
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 75%

---

# 檢視資料字典中的元件資訊

資料字典允許您檢視有關元件的資訊，包括元件說明、類似的元件、經常搭配元件使用的其他元件等。

若要檢視資料字典中關於元件的資訊：

1. 前往包含要檢視之元件的 Analysis Workspace 專案。

1. 選取Analysis Workspace左側面板中的&#x200B;[!UICONTROL **資料字典**]&#x200B;圖示。 (存取資料字典的替代方法說明請見[資料字典概觀](/help/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![資料字典視窗顯示Dimension、量度、區段和日期範圍的快速篩選器](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 確定已在下拉式選單中選取包含您要檢視之元件的資料檢視。 依預設，會顯示您已所在的資料檢視。

1. (可選) 在搜尋欄位中開始鍵入要檢視的元件名稱。

   元件的類型可依據顏色和圖示加以識別。**Dimension** ![Dimension圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)為橘色，**篩選器** ![區段圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)為藍色，**日期範圍** ![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)為紫色，且&#x200B;**量度** ![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)為綠色。 Adobe 圖示 ![Adobe 圖示](assets/default-calc-metric-icon.png) 代表計算量度範本或篩選器範本，計算機圖示 ![計算機圖示 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)則代表由您組織中的 Analytics 管理員建立的計算量度。

{{dd-filter-criteria}}

1. (可選) 選取「**排序**」圖示 ![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取以下任一篩選器選項以將元件清單排序：

   {{components-sort-options}}

1. 從元件清單中選取您要檢視的元件。

   顯示有關該元件的以下資訊：

   {{dd-component-information}}

1. (可選) 將元件從資料字典拖曳至 Analysis Workspace 中。
