---
title: 使用衍生欄位報告目標
description: 瞭解如何使用衍生欄位來報告Workspace專案中的目標（目標）。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 39d3a233166e2ce2035df2ce821dd16181e5e13e
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 6%

---

# 使用衍生欄位報告目標

此使用案例說明如何使用衍生欄位的強大功能來設定特定維度的目標，然後在您的Workspace專案中使用這些目標。

如果您不熟悉衍生欄位，請參閱[教學課程](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=zh-Hant)和[檔案](../data-views/derived-fields/derived-fields.md)以取得簡介。


## 定義目標

若要定義目標，請建立新的衍生欄位，您可在其中使用衍生欄位定義中先前規則所產生的值，直接或間接地明確設定自訂數值。


### 每月贈品憑證訂購目標

您想要明確設定四個月的禮品券訂單目標，範圍從2023年7月到2023年10月。 執行方法：

1. 建立名稱為`Monthly Gift Certificate Orders Goal (Incremental)`的新衍生欄位。

1. 設定&#x200B;**[!UICONTROL 自訂數值]**，以使用CASE WHEN RULE設定每個月的靜態值。 請參閱下方的每月產品目標規則。

   ![每月產品目標](assets/goals-derived-field-product-goals-1.png)


### 行銷管道收入目標

您要為每個行銷管道設定每月收入目標。 執行方法：

1. 使用名稱為[的](/help/data-views/derived-fields/derived-fields.md#marketing-channels)行銷管道功能範本`Monthly Marketing Channel Revenue Goal (Incremental)`，建立新的衍生欄位。

1. 定義所有規則，以根據URL PARSE和CASE WHEN規則的組合正確識別每個行銷管道。 例如：

   ![行銷管道衍生欄位的規則定義](assets/goals-derived-field-marketing-channel-1.png)

1. 透過設定&#x200B;**[!UICONTROL 自訂數值]**，為最終CASE WHEN規則中的特定行銷管道明確設定代表每月收入目標的靜態值。 請參閱下方的[!DNL Monthly Goal]規則。

   ![每月目標](assets/goals-derived-field-marketing-channel-2.png)



## 使用目標

若要在Workspace專案中使用目標，您可使用計算量度功能，將衍生欄位「標準化」回其原始靜態值。 您必須進行這項標準化，因為您為定義目標的衍生欄位設定的靜態值，會隨著每個事件而增加。

### 每月贈品憑證訂購目標

1. 建立名為`Monthly Gift Certificate Orders Goal`的計算量度欄位，定義為：

   ![訂單目標](assets/calculated-metric-ordersgoals.png)

1. 您可以建立其他計算欄位，例如`% of Monthly Gift Certificate Orders Goal`，以顯示目標的實際進度，例如：

   ![訂單目標百分比](assets/calculated-metric-ordersgoalspercent.png)

您可以使用這些計算量度來報告自由表格和視覺效果中的進度。 例如：

![顯示行銷收入目標的自由表格](assets/freeform-table-marketing-channel-revenue-goals.png)




### 行銷管道收入目標

1. 建立名為`Marketing Channel Revenue Goal`的計算量度欄位，定義為：

   ![收入目標](assets/calculated-metric-revenuegoals.png)

1. 您可以建立其他計算欄位，例如`% of Marketing Channel Revenue Goal`，以顯示目標的實際進度，例如：

   ![收入目標百分比](assets/calculated-metric-revenuegoalspercent.png)

您可以使用這些計算量度來報告自由表格和視覺效果中的進度。 例如：

![顯示行銷收入目標的自由表格](assets/freeform-table-product-order-goals.png)
