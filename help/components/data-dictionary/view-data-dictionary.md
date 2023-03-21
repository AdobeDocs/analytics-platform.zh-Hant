---
description: Analysis Workspace 中的資料字典允許使用者對 Analysis Workspace 中的各種元件建立目錄和追蹤，包括其預定用途、已核准的元件、重複的元件等等。
title: 檢視資料字典
feature: Components
role: User, Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 75%

---

# 檢視資料字典中的元件資訊

資料字典允許您檢視有關元件的資訊，包括元件說明、類似的元件、經常搭配元件使用的其他元件等。

若要檢視資料字典中關於元件的資訊：

1. 前往包含要檢視之元件的 Analysis Workspace 專案。

1. 選取 Analysis Workspace 左邊欄的&#x200B;[!UICONTROL **資料字典**]&#x200B;圖示。(存取資料字典的替代方法說明請見[資料字典概觀](/help/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 確保在下拉選單中選取包含您要檢視的元件報告套裝。依預設情況下，會顯示您已使用的報告套裝。

1. (可選) 在搜尋欄位中開始鍵入要檢視的元件名稱。

   元件類型可透過顏色和圖示來識別。 **Dimension** ![Dimension圖示](assets/dimension-icon.png) 是橙色的， **區段** ![區段圖示](assets/segment-icon.png) 是藍色的， **日期範圍** ![日期範圍圖示](assets/date-range-icon.png) 是紫色的， **量度** ![量度圖示](assets/default-metric-icon.png) 為綠色。 Adobe圖示 ![Adobe圖示](assets/default-calc-metric-icon.png) 指出計算量度範本或區段範本，以及計算器圖示 ![計算器表徵圖](assets/calculated-metric-icon-created.png) 指出貴組織中的Analytics管理員所建立的計算量度。

{{dd-filter-criteria}}

1. 從元件清單中選取您要檢視的元件。

   顯示有關該元件的以下資訊：

   {{dd-component-information}}

1. (可選) 將元件從資料字典拖曳至 Analysis Workspace 中。