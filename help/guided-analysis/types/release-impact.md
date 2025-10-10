---
title: 發行影響分析
description: 比較發行前和發行後同期的績效。
feature: Adobe Product Analytics, Guided Analysis
keywords: 產品分析
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 100%

---

# [!UICONTROL 發行影響]分析 {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="發行影響"
>abstract="比較發行前和發行後同期的績效。"

<!-- markdownlint-enable MD034 -->

![發行](/help/assets/icons/Release.svg) **[!UICONTROL 發行影響]**&#x200B;分析顯示關鍵指標在特定日期之前和之後如何表現的比較。該報告的橫軸是時間間隔，而縱軸是測量期望的關鍵指標。圖表中間的垂直長條圖代表您想要比較前後的日期。此日期通常代表您想要衡量比較的產品顯著變化，例如產品更新或行銷活動展開。

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?quality=12&learn=on)

## 使用案例

該分析的使用案例包括：

* **整體效能評估：** 比較整體關鍵指標 (例如參與度衡量) 可以幫助您確定特定發行整體上是否成功。
* **監控**：追蹤您希望在進行變更時維持不變的重要量度，例如載入時間或登入次數。使用此分析來比較發行前後的情況，以確保不會產生任何意外後果。
* **功能採用**：如果產品更新是著重在改善某項功能，則可以使用此分析直接比較產品更新前後該功能的使用情況。
* **錯誤偵測**：追蹤發行前後的錯誤數量可以提供客戶問題的早期指標。如果您發現發行後錯誤立即增加，您可以與工程或開發團隊合作來識別並糾正問題，預防對客戶造成進一步影響。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[首次使用影響](first-use-impact.md)之間切換。
* **[!UICONTROL 關鍵指標]**：您想要衡量每位使用者的事件。每個選取的關鍵指標都以一條彩色線來表示。將代表該事件的資料列加入表格中。最多可包含 3 個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括 [!UICONTROL 每個用戶的事件數]、[!UICONTROL 使用者百分比]， [!UICONTROL 事件]， [!UICONTROL 工作階段]和[!UICONTROL 使用者]。
* **[!UICONTROL 因素]**：您要比較前後的日期。
* **[!UICONTROL 區段]**：您要測量的區段。選取的區段會篩選您的資料，以便只著重符合您區段條件的個人。

### 圖表設定

[!UICONTROL 發行影響]分析會提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 圖表類型]**：您想要使用的視覺效果類型。選項包括[!UICONTROL 折線圖]和[!UICONTROL 條狀圖]。

### 日期範圍

影響分析中的日期選擇的運作與其他分析不同，因為報告是以查詢欄中指定的日期為中心。提供下列選項：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。有效選項包括[!UICONTROL 每日]、 [!UICONTROL 每週]、 [!UICONTROL 每月]和 [!UICONTROL 每季]。變更間隔會影響之前和之後期間可用的選項。
* **[!UICONTROL 之前和之後期間]**：查詢欄中指定的日期之前和之後要分析的時間量。可用選項取決於[!UICONTROL 間隔] 的選擇。


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
