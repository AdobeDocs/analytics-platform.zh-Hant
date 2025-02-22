---
title: 發行影響分析
description: 比較發行前和發行後同期的績效。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 10%

---

# [!UICONTROL 發行影響]分析 {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="發行影響"
>abstract="比較發行前和發行後同期的績效。"

<!-- markdownlint-enable MD034 -->

![版本](/help/assets/icons/Release.svg) **[!UICONTROL 版本影響]**&#x200B;分析會顯示指定日期之前與之後關鍵指標執行方式的比較。 此報表的水平軸是時間間隔，而垂直軸則測量所需的索引鍵。 圖表中央的垂直長條代表您要在前後比較的日期。 此日期通常表示您要測量的產品出現重大變更，例如產品更新或促銷活動啟動。

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?quality=12&learn=on)

## 使用案例

此分析的使用案例包括：

* **整體績效評估：**&#x200B;比較整體關鍵指標（例如參與測量）可協助您判斷特定版本是否整體成功。
* **監視**：追蹤您預期在進行變更時保持不變的重要量度，例如載入時間或登入次數。 使用此分析在發行前後進行比較，確保不會產生任何非預期的結果。
* **功能採用**：如果產品更新著重於改善特定功能，您可以使用此分析直接比較產品更新前後該功能的使用情況。
* **錯誤偵測**：追蹤發行前後的錯誤數量可提供客戶問題的早期指標。 如果您在發行後立即發現錯誤增加，您可以與工程或開發團隊合作，以找出並修正問題，避免對客戶造成進一步影響。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[首次使用影響](first-use-impact.md)之間切換。
* **[!UICONTROL 索引鍵]**：您想要依使用者測量的事件。 每個選取的關鍵指標都會以彩色線條表示。 表格中會新增代表事件的列。 您最多可以包含三個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 每位使用者的事件]、[!UICONTROL 使用者百分比]、[!UICONTROL 事件]、[!UICONTROL 工作階段]和[!UICONTROL 使用者]。
* **[!UICONTROL 因數]**：您要比較前後的日期。
* **[!UICONTROL 區段]**：您要測量的區段。 所選的區段會篩選您的資料，以僅聚焦於符合您區段條件的個人。

### 圖表設定

[!UICONTROL 發行影響]分析提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 圖表型別]**：您要使用的視覺效果型別。 選項包括[!UICONTROL 行]和[!UICONTROL 列]。

### 日期範圍

「影響」分析中的日期選取與其他分析的運作方式不同，因為報表會以查詢邊欄中指定的日期為中心。 提供下列選項：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 有效的選項包括[!UICONTROL 每日]、[!UICONTROL 每週]、[!UICONTROL 每月]及[!UICONTROL 每季]。 變更間隔會影響「之前」和「之後」時段可用的選項。
* **[!UICONTROL 時段之前和之後]**：在查詢邊欄中指定的日期之前和之後要分析的時間量。 可用的選項取決於[!UICONTROL 間隔]選擇。


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
