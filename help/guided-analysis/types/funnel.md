---
title: 漏斗分析
description: 比較步驟之間的轉換率。
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: 產品分析
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 100%

---

# [!UICONTROL 漏斗]分析 {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="漏斗"
>abstract="比較步驟之間的轉換率。"

<!-- markdownlint-enable MD034 -->

 ![轉換漏斗](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL 漏斗&#x200B;]**分析以直覺的方式呈現您產品中關鍵的使用者歷程。橫軸代表使用者必須傳遞的每個步驟。縱軸表示每個步驟的使用者或工作階段的百分比。所有步驟都必須按最終順序完成，但可以在報告視窗內的任何時間發生。

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?quality=12&learn=on){width="90%"}

## 使用案例

該分析的使用案例包括：

* **轉換分析**：您可以分析漏斗每個階段的轉換，例如零售結帳、帳戶註冊、訂閱流程或產品體驗中的其他關鍵歷程。透過追蹤從一個步驟到下一個步驟的使用者數量，您可以識別具有異常或不理想的轉換率瓶頸。這些資訊對於了解您可以在哪些方面改善產品歷程以獲得即時的效果非常有價值。
* **實驗分析**：您可以比較整個漏斗的轉換率，該漏斗具有可選步驟或正在運行 A/B 實驗的步驟。這些資訊可以幫助您確定漏斗的哪種變化可帶來最高的轉換率，以便您可以鼓勵更多的使用者選擇這種方式。
* **入職最佳化**：透過檢查關鍵事件周圍的使用者行為來最佳化產品的入職流程。您可以確定使用者難以完成或無法完成的步驟。
* **功能採用與參與**：了解使用者如何與產品中的特定功能互動。透過與功能相關的步驟分析使用者的進展，您可以了解採用率並確定使用者可能未充分利用某些功能的部分。然後，您可以使用這些資訊以著重功能改善並提高採用率。
* **行銷管道效率**：衡量行銷管道的效率。您可以針對與不同行銷管道 (例如付費搜尋、顥示、免費搜尋或直接郵件) 互動的使用者，並建立一個以此為主的區段。然後，您可以比較他們的歷程，看看哪個管道可造成最佳產品成效。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[轉換趨勢](conversion-trends.md)之間切換。
* **[!UICONTROL 步驟]**：您想要追蹤的事件接觸點。圖表中的每個長條代表一個步驟。最多可以包含 10 個步驟。
   * [!UICONTROL 比較]：每個步驟都提供了一個選項，可以在單一漏斗步驟中比較多個事件，進而建立一個「分叉漏斗」。此功能可讓您並排比較兩次歷程的摩擦，而無需建立兩個單獨的分析。如果有步驟選項或在漏斗內執行 A/B 實驗時，這項功能會很有用。請參閱 Customer Journey Analytics 教學課程的「[漏斗](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel)」，其中有一個影片介紹如何比較漏斗。
* **[!UICONTROL 計為]**：要套用至漏斗的範圍。選項包括[!UICONTROL 工作階段]和[!UICONTROL 使用者]。
   * [!UICONTROL 工作階段]：所有步驟必須發生在同一個工作階段中才可計算在內。
   * [!UICONTROL 使用者]：所有步驟都必須發生在選取的報告視窗內才可計算在內。
* **[!UICONTROL 區段]**：想要比較漏斗的區段。每個選取的區段會將每個步驟分成多個小節。每種顏色代表不同的區段。最多可包含 3 個區段。

### 圖表設定

[!UICONTROL 漏斗]分析提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 圖表類型]**：您想要使用的視覺效果類型。選項包括[!UICONTROL 步驟]。
* **[!UICONTROL 轉換自]**：確定一步至一步的百分比計算。選項包括計算從[!UICONTROL 第一步]或[!UICONTROL 上一步]的轉換。

### 時間比較

{{apply-time-comparison}}



### 日期範圍

您想要分析的日期範圍。此設定有兩個元件：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。此設定不會影響非趨勢分析，例如[漏斗](funnel.md)。
* **[!UICONTROL 日期]**：開始和結束日期。為方便您使用，我們提供滾動日期範圍預設和先前儲存的自訂範圍，或者您可以使用行事曆選擇器來選擇固定的日期範圍。

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
