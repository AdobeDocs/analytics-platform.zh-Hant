---
title: 格式元件設定
description: 設定量度的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# 格式元件設定 {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="格式"
>abstract="判斷元件在報告中使用時的顯示方式。"

<!-- markdownlint-enable MD034 -->


格式可讓您決定指定元件在報告中使用時的顯示方式。

## 設定元件的格式設定

您可以調整指定元件的格式設定，以決定其顯示方式。

1. 在 Customer Journey Analytics 中，選取「[!UICONTROL **資料檢視**]」索引標籤。

1. 選取含有您要設定格式設定的元件資料檢視。

1. 選取「[!UICONTROL **元件**]」索引標籤。

1. 選取要設定的元件，然後展開頁面右側的「[!UICONTROL **格式**]」部分。

   ![格式設定](../assets/format-settings.png)

1. 註明下列資訊：

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 格式]** | 可讓您指定元件的格式，如小數、時間、百分比或貨幣。 |
   | **[!UICONTROL 小數]** | 在整數結構描述資料類型上不可見。可讓您指定元件顯示的小數位數。 |
   | **[!UICONTROL 日期]** | 讓您決定在報告中做為維度使用時如何顯示日期-時間欄位。[了解更多](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日期-時間]** | 讓您決定在報告中做為維度使用時如何顯示日期-時間欄位。[了解更多](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 貨幣]** | 可讓您決定要元件以哪種貨幣顯示。 <p>如果您要分析以不同貨幣進行交易的全球資料，請參閱「[使用貨幣換算](#use-currency-conversion)」。</p> |
   | **[!UICONTROL 顯示上升趨勢的方式]** | 可讓您指定此元件的上升趨勢是好（綠色）或壞（紅色）。 |
   | **[!UICONTROL True 和]**&#x200B;和 **[!UICONTROL False 值]** | 僅對布林值結構描述資料類型可見。允許您自訂 `true` 和 `false` 值的維度項目標籤。 |

   {style="table-layout:auto"}

## 使用貨幣轉換 {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="貨幣轉換"
>abstract="選取一個貨幣代碼維度，以所選貨幣類型設定及顯示貨幣。"

<!-- markdownlint-enable MD034 -->

對在國際營運的企業來說，Customer Journey Analytics 的貨幣轉換功能非常重要。Customer Journey Analytics 免除了手動轉換貨幣的複雜程序，其貨幣轉換功能可提供統一和清晰的財務資料。貨幣轉換會追蹤每日的歷史匯率，並將這些每日匯率維持 4 年的時間。

例如，如果一家電子商務企業在美國、英國和歐盟營運，銷售數據可以自動轉換為美元，確保企業可輕鬆比較數據並全面了解業績。

>[!NOTE]
>
>在開始設定貨幣換算量度之前，請考慮以下事項：
>
>* 您為貨幣轉換選取的量度必須有數字類型 (雙精度浮點數、長整數、整數、位元組)。
>* 設定您的 Customer Journey Analytics 連線以包含至少一個事件資料集，其中每個包含貨幣量度的事件都有貨幣代碼維度。此貨幣代碼維度是使用符合[ ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 標準 (表示貨幣) 的字母貨幣代碼。這些值應以全大寫格式，例如 USD 代表 $、EUR 代表 €、GBP 代表 £。

若要確定如何顯示和轉換指定量度的貨幣：

1. 開始設定要使用貨幣作為格式的量度，如上所述 (在[進行量度的格式設定](#configure-format-settings-for-a-metric)中)。

1. 選取了量度後，在頁面右側的「[!UICONTROL **格式**]」部分進行下列選擇：

   * 在「[!UICONTROL **格式**]」欄位中，選取「[!UICONTROL **貨幣**]」。

   * 在「[!UICONTROL **小數位數**]」欄位中，選擇度量顯示的小數位數。

     只有量度的數字類型為雙精度時才有此選項。

   * 選取「[!UICONTROL **轉換貨幣**]」選項。

   * 在「[!UICONTROL **選取貨幣代碼維度**]」欄位中，選取代表您要轉換貨幣所用 (您的資料所依據的貨幣) 的維度。例如，選取名為&#x200B;[!UICONTROL **貨幣代碼**]&#x200B;的維度。

     如果您目前資料結構描述中沒有包含貨幣代碼欄位的維度，則您可以使用[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)， [資料蒸餾器](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)或[衍生欄位](/help/data-views/derived-fields/derived-fields.md)建立新的貨幣代碼欄位。資料準備只適用於新的實施，因為這只能以往前為基礎。根據組織的設定，可以使用資料蒸餾器和衍生欄位來存取歷史貨幣代碼值。

   * 在「[!UICONTROL **以此類型轉換和顯示貨幣：**]」欄位中，選取您想要轉換資料的貨幣。

1. 如果您想將貨幣轉換套用至其他量度，請重複這些步驟。



### 常見問題

+++ 貨幣兌換如何進行？

報告時，量度值和原始貨幣代碼將轉換為美元，然後轉換為所設定要顯示的貨幣。此轉換會使用每日貨幣匯率 (適用於事件發生時)。

+++

