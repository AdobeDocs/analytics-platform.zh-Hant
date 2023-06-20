---
title: 格式元件設定
description: 設定量度的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 32%

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

2. 從以下專案選取貨幣： **[!UICONTROL 顯示貨幣]** 清單。


### 轉換及顯示貨幣

[!BADGE 新功能]{type=Positive}

{{release-limited-testing-section}}

若要啟用量度的貨幣轉換：

- 設定您的Customer Journey Analytics連線，使其包含至少一個事件資料集，該資料集針對每個包含貨幣量度的事件保留一個貨幣代碼維度。 該貨幣代碼維度會使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 代表貨幣的標準。 例如USD表示$， EUR表示€， GBP表示£。

- 您已（選擇性）套用 [!UICONTROL 貨幣代碼] 一或多個維度的內容標籤，這些維度會定義資料集中可用的貨幣代碼。

  若要套用 [!UICONTROL 貨幣代碼] 內容標籤，在 [!UICONTROL 元件] 資料檢視的索引標籤：

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. 從其中一個包含貨幣代碼的資料集中選取維度。 例如， [!UICONTROL 貨幣代碼].

   2. 選取 **[!UICONTROL 貨幣代碼]** 從 [!UICONTROL 內容標籤] 清單。

  如果您有更多維度包含要用於貨幣轉換的貨幣代碼，請重複這些步驟。

>[!NOTE]
>
>您為貨幣轉換選取的量度必須具有數值型別（雙倍、長、整數、短、位元組）。


若要定義如何轉換和顯示量度的貨幣：

1. 輸入數字 **[!UICONTROL 小數位數]**.

2. 選取 **[!UICONTROL 轉換並行]**.

3. 根據套用的上下文標籤，從以下位置選取適當的維度： **[!UICONTROL 貨幣代碼維度]** 清單會自動選取。 您可以選取任何其他維度，包括您另外套用貨幣代碼內容標籤的維度。

4. 從以下專案選取貨幣： **[!UICONTROL 轉換和顯示貨幣]** 清單。

### 常見問題

+++ 如何執行貨幣轉換？

在報告時間後，量度和原始貨幣代碼的值會轉換為USD，然後轉換為設定用於顯示的貨幣。 對於此轉換，會使用事件時間適用的每日貨幣匯率。

+++

