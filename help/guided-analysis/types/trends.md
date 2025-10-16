---
title: 趨勢分析
description: 測量使用者在一段時間內的參與度。
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 92%

---

# [!UICONTROL 趨勢]分析 {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="趨勢"
>abstract="測量使用者在一段時間內的參與度。"

<!-- markdownlint-enable MD034 -->

![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL 趨勢]** 分析可提供有關您產品效能或使用者隨時間變化的行為深入分析。該報告的橫軸是時間間隔，而縱軸是測量您所期望的事件。


>[!VIDEO](https://video.tv.adobe.com/v/3423438/?captions=chi_hant&quality=12&learn=on)

## 使用案例

該分析的使用案例包括：

* **評估產品效能**：趨勢可讓您評估在特定時間內產品的整體效能。透過分析使用者參與度、採用率或轉換率等量度，您可以確定產品的效能是在提高、停滯還是下降。
* **功能採用**：趨勢可以讓您了解使用者如何採用您發布的新功能或更新。您可以確定哪些功能很受歡迎，以及哪些功能需要改善。這些資訊可以幫助您根據資料做出決策，並確定優先開發哪些功能。
* **使用者行為**：趨勢可對使用者長期使用行為提供深入分析和見解。透過檢查使用者採取的特定行動，您可以識別使用者可能流失的模式。您可以結合這項分析的見解和[漏斗](funnel.md)，以獲得有關行為的更深入見解。
* **A/B 測試和實驗**：如果您在產品內執行 A/B 測試，則可以使用趨勢來判斷長時間下來哪些測試最成功。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 看法]**：在此分析和 [頻率](frequency.md)之間切換。
* **[!UICONTROL 事件和量度]**：您想要測量的事件或量度。每個選擇都以圖表系列和表格列來表示。在查詢中不能將事件和量度結合；一旦做了第一個選擇，其餘的查詢選擇必須是同一類型。最多可包含 5 個選擇。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。 <ul><li>**[!UICONTROL 選項]**&#x200B;包含[!UICONTROL 使用者]、[!UICONTROL 事件]、[!UICONTROL 工作階段]、[!UICONTROL 使用者百分比]、每個工作階段的[!UICONTROL 事件]以及每個使用者的[!UICONTROL 事件]。</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}其他&#x200B;**[!UICONTROL B2B選項]**&#x200B;適用於Customer Journey Analytics B2B edition： [!UICONTROL 全域帳戶]、[!UICONTROL 帳戶]、[!UICONTROL 購買群組]、[!UICONTROL 機會]、[!UICONTROL 全域帳戶的百分比]、[!UICONTROL 帳戶的百分比]、[!UICONTROL 購買群組的百分比]、[!UICONTROL 機會的百分比]、[!UICONTROL 每個全域帳戶的事件]、[!UICONTROL 每個事件的事件帳戶]、每個購買團體的[!UICONTROL 個事件]和每個機會的[!UICONTROL 個事件]。</li></ul>計入選項僅適用於事件查詢，並且量度查詢時會被刪除。
* **[!UICONTROL 區段]**：您要測量的區段。每個選定的區段都會使圖表系列和表格列的數量加倍。最多可包含 5 個區段。
* **[!UICONTROL 劃分屬性]**：根據所選屬性的值細劃分圖表系列和表格列。支援單一的劃分屬性。前 20 個值會顯示在表格中，圖表中最多可查看 10 個值。您可以透過切換 ![顯示隱藏圖示](../assets/hide-in-chart.png) 圖示來隱藏或顯示表格列。

### 圖表設定

[!UICONTROL 趨勢]分析提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 圖表類型]**：您想要使用的視覺效果類型。選項包括折線圖、長條圖、堆積長條圖和堆積區域圖。

### 覆蓋

在圖表中新增附加資料。當圖表上可見多個系列時，只有將滑鼠停留時才會出現覆蓋圖。

* **[!UICONTROL 異常偵測]**：對趨勢分析執行[異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)。離群值顯示為點，您可將滑鼠停留在點上以獲得更多資訊。
* **[!UICONTROL 趨勢線覆蓋]**：在圖表中加入趨勢線，有助於更清晰地描繪資料中的模式。
   * [!UICONTROL 線性 (Linear)]：建立直線迴歸線。最適合以穩定速率增加或減少的簡單線性資料。方程式：`y = a + b * x`
   * [!UICONTROL 對數]：建立彎曲的迴歸線。最適合快速增加或減少，然後變得更加平穩的數據。方程式：`y = a + b * log(x)`
   * [!UICONTROL 移動平均]：根據一組平均值建立平滑趨勢線。移動平均也稱為滾動平均，此值是使用特定數量的先前資料點 (取決於您的選擇)、求取其平均值，並將平均值當做線條中的某個點。 範例包括 7 天移動平均值或 4 週移動平均值。可用的移動平均選項取決於您選擇的間隔和日期範圍。

### 時間比較

{{apply-time-comparison}}


### 日期範圍

您想要分析的日期範圍。此設定有兩個元件：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。有效選項包括每小時、每天、每週、每月和每季。相同的日期範圍可以有不同的間隔，這會影響圖表中的資料點數和表格中的欄數。例如，以每日細度查看跨越三天的分析將僅顯示三個資料點，而以每小時細度查看跨越三天的分析將顯示 72 個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。為方便您使用，我們提供滾動日期範圍預設和先前儲存的自訂範圍，或者您可以使用行事曆選擇器來選擇固定的日期範圍。


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->