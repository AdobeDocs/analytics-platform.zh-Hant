---
title: 淨增長分析
description: 您正在獲得還是失去使用者？
feature: Adobe Product Analytics, Guided Analysis
keywords: 產品分析
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 93%

---

# [!UICONTROL 淨增長]分析 {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="淨增長"
>abstract="您正在獲得還是失去使用者？"

<!-- markdownlint-enable MD034 -->

![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL 淨成長率]**&#x200B;分析可以讓您深入了解特定時期內獲得或失去使用者的速率。橫軸是時間間隔，縱軸是成長測量值。

每個資料點代表淨增長，這是使用以下公式計算：

`([New users] + [Return users]) / [Dormant users]`

此公式的結果是一個比率。淨成長 `1` 表示平衡；產品獲得與失去使用者的數量相同。淨成長大於 `1` 代表正增長；新 + 回訪的使用者多於休眠使用者。同樣，淨成長率低於 `1` 代表損失；休眠使用者多於新 + 回歸使用者。

類似[活躍](active-growth.md)的分析，使用者定義如下：

* **[!UICONTROL 最新]**：使用者在目前期間內處於活躍狀態，但是之前不活躍。將滑鼠停留在圖表圖例的「[!UICONTROL 新使用者]」上，了解分析可回溯至多久以前以確定新使用者。回溯範圍是根據所選的日期範圍和間隔以動態方式來決定。
* **[!UICONTROL 重新回來]**：使用者在目前期間內處於活躍狀態，且在上個期間內不活躍，但之前曾在某個時間點處於活躍狀態。將滑鼠停留在圖表圖例的「[!UICONTROL 回訪使用者]」上，了解分析可回溯至多久以前以確定回訪使用者。回溯範圍是根據所選的日期範圍和間隔以動態方式來決定。
* **[!UICONTROL 休眠]**：使用者在上個期間內處於活躍狀態，但在目前期間內不活躍。休眠使用者未計入活躍使用者總數。

>[!NOTE]
>
>重複使用者不會計入此計算，因為這些數字不代表使用者增加或減少。

>[!VIDEO](https://video.tv.adobe.com/v/3423459/?quality=12&learn=on&captions=chi_hant)


## 使用案例

該分析的使用案例包括：

* **績效評估**：允許您評估產品在贏取新使用者方面的整體表現。透過追蹤成長趨勢，您可以更了解您的產品是否以期望的速度吸引和留住使用者。
* **使用者贏取分析**：允許您評估使用者贏取策略的有效性。分析使用者成長來源 (例如搜尋引擎、廣告活動或其他行銷管道) 可讓您確定最重要的成長來源，以便您根據分析來分配資源。
* **流失分析**：淨成長公式中包含了流失使用者 (休眠使用者)。您可以長期評估使用者的整體健康狀況。如果淨成長率持續低於 `1`，這顯示員工流動率很高，這可能促使實施留任策略。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[正成長](active-growth.md)之間切換。
* **[!UICONTROL 事件]**：您要測量的事件。由於此分析是以使用者為主，因此在期間內與事件互動一次的使用者將被視為活躍使用者。您可以在查詢中列入一個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。 <ul><li>**[!UICONTROL 選項]**&#x200B;包含[!UICONTROL 使用者數目]和[!UICONTROL 使用者百分比]。</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}其他&#x200B;**[!UICONTROL B2B選項]**&#x200B;適用於Customer Journey Analytics B2B edition： [!UICONTROL 全域帳戶]、[!UICONTROL 帳戶]、[!UICONTROL 購買群組]、[!UICONTROL 機會]、[!UICONTROL 全域帳戶的百分比]、[!UICONTROL 帳戶的百分比]、[!UICONTROL 購買群組的百分比]，以及[!UICONTROL 機會的百分比]。</li></ul>
* **[!UICONTROL 區段]**：您要測量的區段。您可以在查詢中列入一個區段。

### 時間比較

{{apply-time-comparison}}

### 日期範圍

您想要分析的日期範圍。此設定有兩個元件：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。有效選項包括每小時、每天、每週、每月和每季。相同的日期範圍可以有不同的間隔，這會影響圖表中的資料點數和表格中的欄數。例如，以每日細度查看跨越三天的分析將僅顯示三個資料點，而以每小時細度查看跨越三天的分析將顯示 72 個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。為方便您使用，我們提供滾動日期範圍預設和先前儲存的自訂範圍，或者您可以使用行事曆選擇器來選擇固定的日期範圍。

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
