---
description: 瞭解如何在表格或折線圖中檢視預測。
title: 如何在Analysis Workspace中檢視預測
feature: Visualizations
role: User
source-git-commit: e52cee369be75785a99798d5acfa9cfc5aba2986
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# 在Analysis Workspace中檢視預測

您可以在自由表格或折線圖中檢視預測。

## 在表格中檢視預測

您可以在時間序列自由表格中檢視預測。 當中的自由格式表格已啟用顯示預測時 [使用者偏好設定](../user-preferences.md)，則會針對新增至表格的第一個量度欄自動顯示預測。 對於任何其他欄：

1. 選取欄設定圖示 ![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 在欄標題中，然後確定 **[!UICONTROL 顯示預測]** 在選項清單中選取。 如需詳細資訊，請參閱[欄設定](../visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 按一下 **[!UICONTROL 欄設定]** 功能表以儲存設定並檢視更新後的表格。

預測在表格中顯示如下：

![在表格中顯示預測](assets/show-forecast-table.png)

* 每個儲存格的預測值和百分比會顯示在 **深灰色**.
* 若要指出預測值，請使用預測符號 <img src="./assets/forecast.svg" alt="預測符號" width="20" /> 會顯示在儲存格的右上角。


## 在折線圖中檢視預測

折線圖是唯一可讓您檢視預測的視覺效果。

1. 選取設定圖示 ![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 在視覺效果標題中，確認 **[!UICONTROL 顯示預測]** 在選項清單中選取。

1. （選擇性）若要允許預測正確地縮放圖表，請選取 **[!UICONTROL 允許預測縮放Y軸]**. 此選項預設為未選取，因為它有時會呈現較不清楚的圖表。

1. 按一下 **[!UICONTROL 設定]** 功能表以檢視更新的折線圖。

預測會顯示在折線圖中，如下所示：

![線上圖中顯示預測](assets/show-forecast-linechart.png)

* 折線圖中度量的目前值以垂直長條表示。 如果您將滑鼠懸停在該垂直線上，則會顯示快顯視窗，其中包含最後的目前日期。
* 一或多個度量的預測值會使用虛線從垂直列直接顯示。 您可以將滑鼠移至量度的任何資料點上。 這會顯示快顯視窗，其中包含：
   * 預測日期
   * 量度的預測值
   * 量度的預測值上限
   * 量度的預測值下限
* 著色區域會顯示預測的信賴範圍。

