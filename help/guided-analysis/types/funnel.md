---
title: 漏斗分析
description: 比較步驟之間的轉換率。
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 2%

---

# [!UICONTROL 漏斗]分析

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel ]**分析可提供產品中重要使用者歷程的視覺化表示。 水平軸代表使用者必須通過的每個步驟。 垂直軸代表每個步驟的使用者或工作階段百分比。 所有步驟最終必須依序完成，但可在報告期間內隨時執行。

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on){width="90%"}

## 使用案例

此分析的使用案例包括：

* **轉換分析**：您可以分析漏斗每個階段的轉換，例如零售結帳、帳戶註冊、訂閱流程，或產品體驗中的其他重要歷程。 透過追蹤從一個步驟到下一個步驟進行之使用者的數量，您可以識別具有異常或不想要的轉換率的瓶頸。 此資訊對於瞭解您可在何處改善產品歷程以取得即時結果非常有用。
* **實驗分析**：您可以比較漏斗的轉換率，該漏斗有執行A/B實驗的可選步驟或步驟。 此資訊可協助您判斷漏斗的哪些變化會產生最高的轉換率，因此您可以鼓勵更多使用者沿著該路徑前進。
* **上線最佳化**：檢查關鍵事件的使用者行為，以最佳化您產品的上線程式。 您可以識別使用者需努力完成或無法完成的步驟。
* **功能採用和參與**：瞭解使用者如何與您產品中的特定功能互動。 透過功能相關步驟分析使用者的進度，可讓您檢視採用率，並識別使用者可能未充分使用特定功能的區域。 接著，您就可以使用此資訊專注於功能改進，以提升採用率。
* **行銷管道有效性**：測量行銷管道的有效性。 您可以建立一個區段，重點關注與不同行銷管道互動的使用者，例如付費搜尋、顯示、免費搜尋或直接。 然後，您可以比較其歷程，以檢視哪個管道帶來最佳產品結果。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[轉換趨勢](conversion-trends.md)之間切換。
* **[!UICONTROL 步驟]**：您要追蹤的事件接觸點。 圖表中的每個長條代表一個步驟。 您最多可以包含十個步驟。
   * [!UICONTROL 比較]：每個步驟都提供可在單一漏斗步驟中比較多個事件的選項，以建立「分叉漏斗」。 此功能可讓您並排比較兩個歷程的摩擦，而不需建立兩個單獨的分析。 當有步驟選項或在漏斗內執行A/B實驗時，此功能會很有用。 請參閱Customer Journey Analytics教學課程中的[漏斗](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel)，瞭解如何比較漏斗的影片。
* **[!UICONTROL 計為]**：您要套用至漏斗的範圍。 選項包括[!UICONTROL 工作階段]和[!UICONTROL 使用者]。
   * [!UICONTROL 工作階段]：所有步驟必須發生在相同工作階段中才能被計數。
   * [!UICONTROL 使用者]：所有步驟都必須在選取的報表期間發生，才能計算。
* **[!UICONTROL 區段]**：您要比較漏斗的區段。 選取的每個區段會將每個步驟分割成多個長條。 每種顏色代表不同的區段。 您最多可以包含三個區段。

### 圖表設定

[!UICONTROL 漏斗]分析提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 圖表型別]**：您要使用的視覺效果型別。 選項包括[!UICONTROL 步驟]。
* **[!UICONTROL 從]**&#x200B;轉換：決定步驟到步驟的百分比計算。 選項包括從[!UICONTROL 第一個步驟]或[!UICONTROL 上一個步驟]計算轉換。

### 時間比較

{{apply-time-comparison}}



### 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 此設定不會影響非趨勢分析，例如[漏斗](funnel.md)。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
