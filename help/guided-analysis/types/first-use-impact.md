---
title: 首次使用影響分析
description: 測量功能首次使用對關鍵指標的影響。
feature: Adobe Product Analytics, Guided Analysis
keywords: 產品分析
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '674'
ht-degree: 100%

---

# [!UICONTROL 首次使用影響]分析 {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="首次使用影響"
>abstract="測量功能首次使用對關鍵指標的影響。"

<!-- markdownlint-enable MD034 -->

 ![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL 首次使用影響]**&#x200B;分析顯示使用者首次使用產品功能之前和之後關鍵指標的表現對比。本報告的橫軸是事件前後的相對時間間隔，縱軸則是測量所需的關鍵指標。圖表中間的垂直條表示特定使用者首次使用某項功能的第 0 天。由於使用者並不總是在同一天採用功能，並且您的功能推出可能會持續數天，因此第 0 天對每個使用者來說可能意味著不同的事情。


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## 使用案例

該分析的使用案例包括：

* **新功能分析**：如果您在產品中推出新功能，您可以比較使用者首次接觸該新功能之前和之後關鍵指標的表現。
* **分階段功能推出**：由於分析會尋找功能的首次使用情況而非固定日期，因此如果您分階段逐步推出功能，此分析將很有幫助。
* **新產品版本分析**：如果您要推出產品的新版本，您可以比較使用者首次接觸新版本前後的關鍵指標表現。選取「任何事件」作為您的首次使用事件，並將其篩選至您的版本編碼屬性。
* **現有功能改善**：如果您正進行產品現有功能改善，則可以比較使用者首次接觸這些新改善之前和之後的關鍵指標表現。您可以根據您的功能檢測採用一種或多種方式完成此分析。
   * 選取代表改善的事件作為首次使用事件
   * 選取變更開始實施的日期
   * 將分析細分為接觸到改善事件的人群
* **行銷活動有效性**：當使用者點進特定行銷活動時，您可以比較使用者與該行銷活動互動之前和之後的關鍵指標表現。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[版本](release-impact.md)之間切換。
* **[!UICONTROL 關鍵指標]**：您想要衡量每位使用者的事件。每個選取的關鍵指標都以一條彩色線來表示。將代表該事件的資料列加入表格中。最多可包含 3 個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括[!UICONTROL 每個使用者的事件]、 [!UICONTROL 事件]、 [!UICONTROL 工作階段]和[!UICONTROL 使用者]。
* **[!UICONTROL 因素]**：本次分析有兩個因素：
   * **[!UICONTROL 日期]**：您想要從多久以前開始尋找首次使用事件的發生時間。
   * **[!UICONTROL 事件]**：您想要尋找首次使用的事件 (作為分析的中心)。
* **[!UICONTROL 區段]**：您要測量的區段。選取的區段會篩選您的資料，以便只著重符合您區段條件的個人。此分析支援單一區段。

### 圖表設定

[!UICONTROL 首次使用影響]分析會提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 圖表類型]**：您想要使用的視覺效果類型。選項包含折線圖。

### 日期範圍

 [!UICONTROL 首次使用影響]分析中的日期選擇與其他分析不同，因為此分析是以查詢邊欄中指定的日期為中心。提供下列選項：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。有效選項包括[!UICONTROL 每日]、 [!UICONTROL 每週]、 [!UICONTROL 每月]和 [!UICONTROL 每季]。變更間隔會影響之前和之後期間可用的選項。
* **[!UICONTROL 前後期間]**：查詢邊欄中指定的首次使用事件前後要分析的時間量。可用選項取決於[!UICONTROL 間隔] 的選擇。

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
