---
title: 格式元件設定
description: 設定量度的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: cf9e8c90eec78658e470d3a7a56cb2e3414591d4
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 19%

---

# 格式元件設定

格式可讓您決定指定量度在報表中使用的顯示方式。

## 設定量度的格式設定

您可以調整指定量度的格式設定，以決定其顯示方式。

1. 在Customer Journey Analytics中，選取 [!UICONTROL **資料檢視**] 標籤。

1. 選取包含您要設定其格式設定的元件的資料檢視。

1. 選取「[!UICONTROL **元件**]」索引標籤。

1. 選取要設定的元件，然後展開 [!UICONTROL **格式**] 區段。

   ![格式設定](../assets/format-settings.png)

1. 指定下列資訊：

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 格式]** | 可讓您指定量度的格式，如小數、時間、百分比或貨幣。 |
   | **[!UICONTROL 小數]** | 在整數結構描述資料類型上不可見。可讓您指定量度顯示的小數位數。 |
   | **[!UICONTROL 日期]** | 讓您決定在報告中做為維度使用時如何顯示日期-時間欄位。[了解更多](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日期-時間]** | 讓您決定在報告中做為維度使用時如何顯示日期-時間欄位。[了解更多](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 貨幣]** | 可讓您決定要以哪種貨幣顯示量度。 <p>如果您分析交易以不同貨幣發生的全域資料，請參閱  [使用貨幣轉換](#use-currency-conversion).</p> |
   | **[!UICONTROL 顯示上升趨勢的方式]** | 可讓您指定此量度的上升趨勢是好 (綠色) 或壞 (紅色)。 |
   | **[!UICONTROL True 和]**&#x200B;和 **[!UICONTROL False 值]** | 僅對布林值結構描述資料類型可見。允許您自訂 `true` 和 `false` 值的維度項目標籤。 |

   {style="table-layout:auto"}

## 使用貨幣轉換

Customer Journey Analytics的貨幣轉換對於在國際上營運的企業而言，是極為寶貴的。 透過移除手動貨幣轉換的複雜性，Customer Journey Analytics中的貨幣轉換為財務資料帶來一致性和明確性。 貨幣轉換會追蹤每日歷史匯率，並將這些每日匯率維持在4年。

舉例來說，如果電子商務業務在美國、英國及歐盟營運，銷售資料可自動轉換為美元，確保輕鬆比較及全面瞭解效能。

>[!NOTE]
>
>開始設定貨幣轉換的量度前，請考量下列事項：
>
>* 您為貨幣轉換選取的量度必須具有數值型別（雙精度、長精度、整數、短整數、位元組）。
>* 設定您的Customer Journey Analytics連線，使其至少包含一個事件資料集，該資料集為包含貨幣量度的每個事件保留一個貨幣代碼維度。 該貨幣代碼維度使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 代表貨幣的標準。 這些值應全大寫格式，例如$為USD， €為EUR， £為GBP。

若要決定指定量度貨幣的顯示和轉換方式：

1. 開始設定您要使用貨幣作為格式的量度，如上所述，在 [設定量度的格式設定](#configure-format-settings-for-a-metric).

1. 選取量度後，在 [!UICONTROL **格式**] 頁面右側的區段：

   * 在 [!UICONTROL **格式**] 欄位，選取 [!UICONTROL **貨幣**].

   * 在 [!UICONTROL **小數位數**] 欄位，選擇量度顯示的小數位數。

     只有在量度的數值型別為「兩次」時，才可使用此選項。

   * 選取 [!UICONTROL **轉換貨幣**] 選項。

   * 在 [!UICONTROL **選取貨幣代碼維度**] 欄位中，選取代表您要轉換之貨幣（您的資料所依據的貨幣）的維度。 例如，選取一個維度，稱為 [!UICONTROL **貨幣代碼**].

     如果您目前的資料結構中沒有包含貨幣代碼欄位的維度，您可以使用以下專案建立新的貨幣代碼欄位 [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)， [資料Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)，或 [衍生欄位](/help/data-views/derived-fields/derived-fields.md). 「資料準備」僅適用於新的實作，因為它僅適用於未來用途。 根據組織的設定，可以使用「資料Distiller」和「衍生欄位」來存取歷史上的貨幣代碼值。

   * 在 [!UICONTROL **轉換及顯示貨幣**] 欄位，選擇您要轉換資料的貨幣。

1. 如果您想要將貨幣轉換套用至其他量度，請重複這些步驟。



### 常見問題

+++ 如何執行貨幣轉換？

在報告時間時，量度和原始貨幣代碼的值會轉換為USD，然後轉換為設定用於顯示的貨幣。 對於此轉換，會使用適用於事件時間的每日貨幣匯率。

+++

