---
title: 首次使用影響分析
description: 測量功能首次使用對關鍵指標的影響。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 9%

---

# [!UICONTROL 首次使用影響]分析 {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="首次使用影響"
>abstract="測量功能首次使用對關鍵指標的影響。"

<!-- markdownlint-enable MD034 -->

![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL 首次使用影響]**&#x200B;分析會顯示使用者第一次使用產品功能之前和之後關鍵指標執行方式的比較。 此報表的水平軸是事件前後的相對時間間隔，垂直軸則測量所需的索引鍵指標。 圖表中央的垂直長條代表指定使用者首次使用功能時的第0天。 由於使用者不一定會在同一天採用功能，而您的轉出可能會持續數天，因此第0天對於每位使用者來說可能意味著不同的事情。


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## 使用案例

此分析的使用案例包括：

* **新功能分析**：如果您要在產品中啟動新功能，您可以比較使用者第一次使用新功能之前和之後所執行的關鍵指標。
* **分階段推出**：由於分析會尋找功能的首次使用而非固定日期，因此如果您隨著時間推移分階段推出功能，此分析會很有幫助。
* **新產品版本分析**：如果您要啟動產品的新版本，您可以比較使用者首次公開該新版本之前和之後的關鍵指標執行方式。 選取「任何事件」作為您的首次使用事件，並將其篩選為您的Version number屬性。
* **現有功能改良**：如果您要改良產品中的現有功能，您可以比較使用者首次接觸到這些新改良功能之前和之後的關鍵指標執行方式。 您可以根據特徵檢測以一或多種方式完成此分析。
   * 選取代表改善的事件，作為您的首次使用事件
   * 選取變更開始推出的日期
   * 將分析區隔給暴露在改善中的人員群組
* **行銷活動有效性**：當使用者從指定的行銷活動點進時，您可以比較使用者與該行銷活動互動之前和之後所執行的關鍵指標。

## 介面

請參閱[介面](../overview.md#interface)，以取得引導式分析介面的概觀。 以下設定專用於此分析：

### 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[版本](release-impact.md)之間切換。
* **[!UICONTROL 索引鍵]**：您想要依使用者測量的事件。 每個選取的關鍵指標都會以彩色線條表示。 表格中會新增代表事件的列。 您最多可以包含三個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。選項包括每個使用者的[!UICONTROL 個事件]、[!UICONTROL 個事件]、[!UICONTROL 個工作階段]和[!UICONTROL 個使用者]。
* **[!UICONTROL 因素]**：此分析有兩個因素：
   * **[!UICONTROL 日期]**：您想要回溯多久開始尋找已發生的首次使用事件。
   * **[!UICONTROL 事件]**：您要尋找第一次使用的事件，以集中分析。
* **[!UICONTROL 區段]**：您要測量的區段。 所選的區段會篩選您的資料，以僅聚焦於符合您區段條件的個人。 此分析支援單一區段。

### 圖表設定

[!UICONTROL 首次使用影響]分析提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 圖表型別]**：您要使用的視覺效果型別。 選項包括Line。

### 日期範圍

[!UICONTROL 首次使用影響]分析中的日期選取與其他分析運作方式不同，因為分析會以查詢邊欄中指定的日期為中心。 提供下列選項：

* **[!UICONTROL 間隔]**：您要檢視趨勢資料的日期詳細程度。 有效的選項包括[!UICONTROL 每日]、[!UICONTROL 每週]、[!UICONTROL 每月]及[!UICONTROL 每季]。 變更間隔會影響「之前」和「之後」時段可用的選項。
* **[!UICONTROL 時段之前和之後]**：在查詢邊欄中指定的第一個使用事件之前和之後要分析的時間量。 可用的選項取決於[!UICONTROL 間隔]選擇。

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
