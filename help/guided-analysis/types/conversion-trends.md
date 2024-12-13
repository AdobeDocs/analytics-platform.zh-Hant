---
title: 轉換趨勢分析
description: 追蹤轉換率在一段時間內的變化。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 7%

---

# [!UICONTROL 轉換趨勢]分析 {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="轉換趨勢"
>abstract="追蹤一段時間內的轉換率變化。"

<!-- markdownlint-enable MD034 -->


![轉換趨勢](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL 轉換趨勢]**&#x200B;分析可提供轉換率隨時間變化的趨勢視覺效果。 水平軸是時間間隔，而垂直軸則代表轉換率。


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)


## 使用案例

此分析的使用案例包括：

* **追蹤最佳化工作**：使用[漏斗](funnel.md)分析找出要改善的主要瓶頸之後，您可以使用此分析來追蹤這些最佳化在一段時間內對轉換率的影響。
* **A/B測試評估**：評估在漏斗內容中執行的A/B測試或實驗的有效性。 透過比較不同變異之間的轉換率，您可以輕鬆判斷哪些測試提供較高的轉換率，進而做出資料導向的決定，決定永久實施哪些變異。
* **一段時間內的行銷活動評估**：測量一段時間內的行銷活動有效性。 您可以建立區段，著重於接觸特定行銷活動的使用者，並將其轉換率與其他行銷活動進行比較。 您也可以將目前的轉換率與過去執行的類似行銷活動進行比較。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[漏斗](funnel.md)之間切換。
* **[!UICONTROL 步驟]**：您要追蹤的事件接觸點。 圖表中的每個長條代表一個步驟。 您最多可以包含十個步驟。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 使用者]和[!UICONTROL 工作階段]。
* **[!UICONTROL 區段]**：您要比較漏斗的區段。 選取的每個區段會將每個步驟分割成多個長條。 每種顏色代表不同的區段。 您最多可以包含三個區段。

### 圖表設定

[!UICONTROL 轉換趨勢]分析提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 圖表型別]**：您要使用的視覺效果型別。 選項包括[!UICONTROL 行]。
* **[!UICONTROL 從]**&#x200B;轉換：決定步驟到步驟的百分比計算。 選項包括從[!UICONTROL 第一個步驟]或[!UICONTROL 上一個步驟]計算轉換。

>[!NOTE]
>
>「轉換趨勢」分析表格中的&#x200B;**平均**&#x200B;資料行與[漏斗分析](funnel.md)表格中的&#x200B;**總計**&#x200B;資料行不同。 前者是間隔欄的平均值（例如，每日轉換率的平均值），而後者則是整個日期範圍的彙總計算。

### 時間比較

{{apply-time-comparison}}


### 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 有效的選項包括每小時、每日、每週、每月和每季。 相同日期範圍可以有不同的間隔，這會影響圖表中的資料點數以及表格中的欄數。 例如，以每日詳細程度檢視橫跨3天的分析只會顯示3個資料點，而以每小時詳細程度橫跨3天的分析則會顯示72個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
