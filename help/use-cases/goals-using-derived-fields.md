---
title: 使用衍生欄位來報告目標
description: 瞭解如何使用衍生欄位來報告工作區專案中的目標（目標）。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: 53cf026531ac5690a3e5a31acaa5654a52747b69
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---


# 使用衍生欄位來報告目標

此使用案例說明如何使用衍生欄位的功能來設定特定維度的目標，然後在您的Workspace專案中使用這些目標。

如果您不熟悉衍生欄位，請參閱 [教學課程](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=en) 和 [檔案](../data-views/derived-fields/derived-fields.md) 以取得簡介。


## 定義目標

若要定義目標，請建立新的衍生欄位，您可在其中使用衍生欄位定義中先前規則所產生的值，直接或間接地明確設定自訂數值。


### 每月贈品憑證訂購目標

您想要明確設定四個月的禮品券訂單目標，範圍從2023年7月到2023年10月。 執行方法：

1. 以名稱建立新的衍生欄位 `Monthly Gift Certificate Orders Goal (Incremental)`.

1. 使用CASE WHEN RULE設定每個月的靜態值，方法為設定 **[!UICONTROL 自訂數值]**. 請參閱下方的每月產品目標規則。

   ![產品目標](assets/goals-derived-field-product-goals-1.png)


### 行銷管道收入目標

您要為每個行銷管道設定每月收入目標。 執行方法：

1. 使用建立新的衍生欄位 [行銷管道功能範本](/help/data-views/derived-fields/derived-fields.md#marketing-channels) 名稱 `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. 定義所有規則，以根據URL PARSE和CASE WHEN規則的組合正確識別每個行銷管道。 例如：

   ![行銷管道衍生欄位的規則定義](assets/goals-derived-field-marketing-channel-1.png)

1. 透過設定「 」以針對最終CASE WHEN規則中的特定行銷管道明確設定代表每月收入目標的靜態值 **[!UICONTROL 自訂數值]**. 請參閱 [!DNL Monthly Goal] 下方的規則。

   ![每月目標](assets/goals-derived-field-marketing-channel-2.png)



## 使用目標

若要在您的Workspace專案中使用目標，請使用計算量度功能，將衍生欄位「標準化」回其原始靜態值。

### 每月贈品憑證訂購目標

1. 建立計算量度欄位，名為 `Monthly Gift Certificate Orders Goal`，定義為：

   ![訂單目標](assets/calculated-metric-ordersgoals.png)

1. 例如，您可以建立其他計算欄位 `% of Monthly Gift Certificate Orders Goal`，顯示目標的實際進度，例如：

   ![訂單目標百分比](assets/calculated-metric-ordersgoalspercent.png)

您可以使用這些計算量度來報告自由表格和視覺效果中的進度。 例如：

![顯示行銷收入目標的自由表格](assets/freeform-table-product-order-goals.png)


### 行銷管道收入目標

1. 建立計算量度欄位，名為 `Marketing Channel Revenue Goal`，定義為：

   ![收入目標](assets/calculated-metric-revenuegoals.png)

1. 例如，您可以建立其他計算欄位 `% of Marketing Channel Revenue Goal`，顯示目標的實際進度，例如：

   ![收入目標百分比](assets/calculated-metric-revenuegoalspercent.png)

您可以使用這些計算量度來報告自由表格和視覺效果中的進度。 例如：

![顯示行銷收入目標的自由表格](assets/freeform-table-marketing-channel-revenue-goals.png)
