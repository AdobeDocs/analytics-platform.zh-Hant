---
title: 行為元件設定
description: 指定維度或量度在報告中的行為。
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 100%

---

# 行為元件設定 {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="行為"
>abstract="判斷如何彙總此維度中的條列項目。指定欄位中的字串值是否應為小寫。"

<!-- markdownlint-enable MD034 -->


行為設定可用於維度和量度。設定適用性取決於元件類型和結構描述資料類型。

![行為設定](../assets/behavior-settings.png)

## 維度行為設定

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 小寫] | 對擁有相同值但大小寫不同的列刪除重複資料。如果啟用，一個維度具有相同值的所有執行個體皆會回報為小寫。例如，您的資料在字串維度中包含值 `"liverpool"`、`"Liverpool"` 和 `"LIVERPOOL"`。如果啟用[!UICONTROL 小寫]，則所有三個值都會合併至 `"liverpool"`。如果停用，則所有三個值都會視為相異。 |

{style="table-layout:auto"}

>[!NOTE]
>
>如果在查閱資料集維度上啟用[!UICONTROL 小寫]，則同一識別碼可以存在多個查閱值。如果發生這種衝突，Customer Journey Analytics 將使用第一個 ASCII 整理值 (大寫值在小寫值之前)。Adobe 建議不要在啟用[!UICONTROL 小寫]時使用包含相同值的查閱資料集。

![區分大小寫維度](../assets/case-sens-workspace.png)

## 量度行為設定

| 設定 | 說明/使用案例 |
| --- | --- |
| [!UICONTROL 計數值] | 在整數和雙精確度結構描述資料類型上可見。將量度增加指定的量。例如，如果該欄的值為 `50`，則將量度增加 50。 |
| [!UICONTROL 計數實例] | 在整數和雙精確度結構描述資料類型上可見。無論值如何，都將量度增加 1。任何值的存在都會增加量度。例如，如果欄的值為 `50`，則將量度增加 1。 |
| [!UICONTROL 要計數的值] | 在布林值結構描述資料類型上可見。允許您透過計數 `true`、`false` 或兩者來決定量度是否增加。 |

{style="table-layout:auto"}

您可以使用具有不同行為的相同事件資料集欄，在 Analysis Workspace 中產生「訂單」和「收入」量度。將「收入」資料集欄拖入資料檢視兩次，並將一個設定為「計數值」，另一個設定為「計數實例」。「訂單」量度計算實例，而「收入」量度計算值。
