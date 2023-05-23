---
description: Analysis Workspace 中的資料字典允許使用者對 Analysis Workspace 中的各種元件建立目錄和追蹤，包括其預定用途、已核准的元件、重複的元件等等。
title: 檢視資料字典
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: b38b5b54ebbf301a3e59156d484bf5d69974b4a4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 51%

---

# 檢視資料字典中的元件資訊

資料字典允許您檢視有關元件的資訊，包括元件說明、類似的元件、經常搭配元件使用的其他元件等。

若要檢視資料字典中關於元件的資訊：

1. 前往包含要檢視之元件的 Analysis Workspace 專案。

1. 選取 Analysis Workspace 左邊欄的&#x200B;[!UICONTROL **資料字典**]&#x200B;圖示。(存取資料字典的替代方法說明請見[資料字典概觀](/help/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 確保在下拉菜單中選擇了包含要查看的元件的資料視圖。 預設情況下，將顯示您已在的資料視圖。

1. (可選) 在搜尋欄位中開始鍵入要檢視的元件名稱。

   元件類型可以同時用顏色和表徵圖來標識。 **Dimension** ![Dimension表徵圖](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 是橙色的， **段** ![段表徵圖](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 是藍色的， **日期範圍** ![日期範圍表徵圖](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 是紫色的 **度量** ![度量表徵圖](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 是綠色的。 Adobe表徵圖 ![Adobe表徵圖](assets/default-calc-metric-icon.png) 指示計算的度量模板或段模板，以及計算器表徵圖 ![計算器表徵圖](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 指明了由組織中的分析管理員建立的計算度量。

{{dd-filter-criteria}}

1. （可選）選擇 **排序** 表徵圖 ![「排序元件」表徵圖](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選擇下列任何篩選器選項對元件清單進行排序：

   {{components-sort-options}}

1. 從元件清單中選取您要檢視的元件。

   顯示有關該元件的以下資訊：

   {{dd-component-information}}

1. (可選) 將元件從資料字典拖曳至 Analysis Workspace 中。
