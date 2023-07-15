---
title: 格式元件設定
description: 設定量度的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 3626a9f97048b68a57fca25fec396684c4f95449
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 30%

---

# 格式元件設定

格式可讓您確定給定量度的顯示方式。

![格式設定](../assets/format-settings.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 格式]** | 可讓您指定量度的格式，如小數、時間、百分比或貨幣。 |
| **[!UICONTROL 小數位數]** | 在整數結構描述資料類型上不可見。可讓您指定量度顯示的小數位數。 |
| **[!UICONTROL 日期]** | 讓您決定在報告中做為維度使用時如何顯示日期-時間欄位。[了解更多](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 日期-時間]** | 讓您決定在報告中做為維度使用時如何顯示日期-時間欄位。[了解更多](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 貨幣]** | 可讓您確定您希望量度以哪種貨幣顯示。另請參閱 [貨幣](#currency) 更多詳細資料。 |
| **[!UICONTROL 顯示上升趨勢的方式]** | 可讓您指定此量度的上升趨勢是好 (綠色) 或壞 (紅色)。 |
| **[!UICONTROL True 和]**&#x200B;和 **[!UICONTROL False 值]** | 僅對布林值結構描述資料類型可見。允許您自訂 `true` 和 `false` 值的維度項目標籤。 |

{style="table-layout:auto"}


## 貨幣

當您選取 **[!UICONTROL 貨幣]** 作為 [!UICONTROL 格式] 對於量度，您可以決定如何顯示和轉換貨幣。

### 顯示貨幣

若要顯示量度的貨幣：

1. 輸入數字 **[!UICONTROL 小數位數]**.

1. 從以下專案選取貨幣： **[!UICONTROL 顯示貨幣]** 清單。


### 轉換及顯示貨幣

{{release-limited-testing-section}}

若要啟用一或多個量度的貨幣轉換：

- 設定您的Customer Journey Analytics連線，使其包含至少一個事件資料集，該資料集針對每個包含貨幣量度的事件保留一個貨幣代碼維度。 該貨幣代碼維度會使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 代表貨幣的標準。 這些值應全大寫格式，例如$為USD，€為EUR，英鎊為$GBP。

   1. 從其中一個包含貨幣代碼的資料集中選取維度。 例如， [!UICONTROL 貨幣代碼].

   1. 選取 **[!UICONTROL 貨幣代碼]** 從維度清單中。

- 如果您有更多維度包含要用於貨幣轉換的貨幣代碼，請重複這些步驟。

>[!NOTE]
>
>您為貨幣轉換選取的量度必須具有數值型別（雙倍、長、整數、短、位元組）。


若要定義如何轉換和顯示量度的貨幣：

1. 輸入數字 **[!UICONTROL 小數位數]**.

1. 選取 **[!UICONTROL 轉換並行]**.

1. 從包含貨幣代碼欄位的維度清單中選取適當的維度。

1. 從以下專案選取貨幣： **[!UICONTROL 轉換和顯示貨幣]** 清單。

### 常見問題

+++ 如何執行貨幣轉換？

在報告時間後，量度和原始貨幣代碼的值會轉換為USD，然後轉換為設定用於顯示的貨幣。 對於此轉換，會使用事件時間適用的每日貨幣匯率。

+++


+++ 每日轉換率可維持多久以前？

每日轉換率維持在過去四年嗎？

+++


+++ 如果我沒有貨幣代碼欄位做為目前資料結構描述的一部分，該怎麼辦？

建立新貨幣代碼欄位有數個選項，包括「資料準備」、「資料Distiller」和「衍生欄位」。 「資料準備」非常適合新的實作，因為它只會持續進行。 根據組織的設定，可以使用「資料Distiller」和「衍生欄位」來存取歷史貨幣代碼值。

+++

