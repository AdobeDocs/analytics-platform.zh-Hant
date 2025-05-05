---
title: 轉換趨勢分析
description: 追蹤一段時間內的轉換率變化。
feature: Adobe Product Analytics, Guided Analysis
keywords: 產品分析
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '536'
ht-degree: 100%

---

# [!UICONTROL 轉換趨勢]分析 {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="轉換趨勢"
>abstract="追蹤一段時間內的轉換率變化。"

<!-- markdownlint-enable MD034 -->


 ![轉換趨勢](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL 轉換趨勢]**&#x200B;分析是提供轉換率隨時間變化的趨勢視覺效果。橫軸是時間間隔，縱軸表示轉換率。


>[!VIDEO](https://video.tv.adobe.com/v/3423485/?quality=12&learn=on&captions=chi_hant)


## 使用案例

該分析的使用案例包括：

* **追蹤最佳化工作**：在使用[漏斗](funnel.md)分析確定您想改善的關鍵瓶頸後，您可以使用此分析來追蹤這些最佳化如何隨時間影響轉換率。
* **A/B 測試評估**：評估漏斗環境中進行的 A/B 測試或實驗的有效性。透過比較不同變化版本之間的轉換率，您可以輕鬆確定哪些測試提供更高的轉換率，進而根據不同變化版本做出資料驅動的決策，以便永久實施這些決策。
* **長期下來的活動評估**：衡量行銷活動長期下來的有效性。您可以針對接觸過行銷活動的使用者建立區段，並將他們的轉換率與其他行銷活動進行比較。您也可以將目前的轉換率與過去進行的類似活動進行比較。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[漏斗](funnel.md)之間切換。
* **[!UICONTROL 步驟]**：您想要追蹤的事件接觸點。圖表中的每個長條代表一個步驟。最多可以包含 10 個步驟。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 使用者]和[!UICONTROL 工作階段]。
* **[!UICONTROL 區段]**：想要比較漏斗的區段。每個選取的區段會將每個步驟分成多個小節。每種顏色代表不同的區段。最多可包含 3 個區段。

### 圖表設定

[!UICONTROL 轉换趨勢]分析提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 圖表類型]**：您想要使用的視覺效果類型。選項包含[!UICONTROL 折線圖]。
* **[!UICONTROL 轉換自]**：確定一步至一步的百分比計算。選項包括計算從[!UICONTROL 第一步]或[!UICONTROL 上一步]的轉換。

>[!NOTE]
>
>轉換趨勢分析表中的「**平均值**」欄與「[漏斗分析](funnel.md)」表中的「**總計**」欄不同。前者是間隔欄的平均值 (例如，每日轉換率的平均值)，而後者是跨整個日期範圍的彙總計算。

### 時間比較

{{apply-time-comparison}}


### 日期範圍

您希望分析的日期範圍。此設定有兩個元件：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。有效選項包括每小時、每天、每週、每月和每季。相同的日期範圍可以有不同的間隔，這會影響圖表中的資料點數和表格中的欄數。例如，以每日細度查看跨越三天的分析將僅顯示三個資料點，而以每小時細度查看跨越三天的分析將顯示 72 個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。為方便您使用，我們提供滾動日期範圍預設和先前儲存的自訂範圍，或者您可以使用行事曆選擇器來選擇固定的日期範圍。

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
