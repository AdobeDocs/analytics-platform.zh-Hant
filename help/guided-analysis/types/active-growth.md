---
title: 積極成長分析
description: 識別哪些使用者是新的、保留的、回訪的或非活躍的。
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 92%

---

# [!UICONTROL 積極成長]分析 {#active-growth}

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="積極成長"
>abstract="識別哪些使用者是新的、保留的、回訪的或非活躍的。"



![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL 積極成長]**&#x200B;分析可讓您深入了解使用者在特定期間內的成長和獲取情況。橫軸是時間間隔，縱軸是使用者測量值。使用者分為四大類：

* **[!UICONTROL 最新]**：使用者在目前期間內處於活躍狀態，但是之前不活躍。若要了解這項分析可回溯至多久以前，請將滑鼠停留在圖例中的「_[!UICONTROL 全新使用者]_」。回溯範圍是根據所選的日期範圍和間隔以動態方式來決定。
* **[!UICONTROL 重複]**：使用者在目前和上個期間內處於活躍狀態。
* **[!UICONTROL 重新回來]**：使用者在目前期間內處於活躍狀態，且在上個期間內不活躍，但之前曾在某個時間點處於活躍狀態。若要了解這項分析可回溯至多久以前，請將滑鼠停留在圖例中的「_[!UICONTROL 重新回來的使用者]_」。回溯範圍是根據所選的日期範圍和間隔以動態方式來決定。
* **[!UICONTROL 休眠]**：使用者在上個期間內處於活躍狀態，但在目前期間內不活躍。休眠使用者未計入活躍使用者總數。

所有活躍使用者 (新使用者 + 重複使者 + 重新回來使用者) 在橫軸上方顯示為青色，而所有休眠使用者在橫軸下方顯示為橙色。


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## 使用案例

該分析的使用案例包括：

* **使用者保留和流失：** 以視覺效果清楚呈現高或低使用者保留率的期間。了解這些高或低保留率的期間可以幫助您做出產品決策，以鼓勵高保留率或幫助盡量減少客戶流失。
* **促銷活動評估**：查看特定的促銷活動可以幫助您了解活動產生了多少流量，以及活動如何有效幫助使用者繼續參與。
* **使用者生命週期分析**：分析整個使用者生命週期中的活躍使用者成長，有助於查出使用者參與度下降的具體階段。例如，如果個人是在上線階段，而休眠使用者的比例很高，這可能表示產品可用性有問題或需要更好的產品內指導。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 檢視]**：在此分析和[淨成長](net-growth.md)之間切換。
* **[!UICONTROL 事件]**：您要測量的事件。由於此分析是以使用者為主，因此在期間內與事件互動一次的使用者將被視為活躍使用者。您可以在查詢中列入一個事件。
* **[!UICONTROL 計為]**：要套用至所選取事件的計算方法。 <ul><li>**[!UICONTROL 選項]**&#x200B;包含[!UICONTROL 使用者數目]和[!UICONTROL 使用者百分比]。</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}其他&#x200B;**[!UICONTROL B2B選項]**&#x200B;適用於Customer Journey Analytics B2B edition： [!UICONTROL 全域帳戶]、[!UICONTROL 帳戶]、[!UICONTROL 購買群組]、[!UICONTROL 機會]、[!UICONTROL 全域帳戶的百分比]、[!UICONTROL 帳戶的百分比]、[!UICONTROL 購買群組的百分比]，以及[!UICONTROL 機會的百分比]。</li></ul>
* **[!UICONTROL 區段]**：您要將資料作為分段依據的區段。 您可以在查詢中列入一個區段。

### 圖表設定

[!UICONTROL 積極成長]分析會提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 圖表類型]**：您想要使用的視覺效果類型。選項包括[!UICONTROL 堆疊長條圖]和[!UICONTROL 堆疊區域]。

### 時間比較

{{apply-time-comparison}}

### 日期範圍

您想要分析的日期範圍。此設定有兩個元件：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。有效選項包括每小時、每天、每週、每月和每季。相同的日期範圍可以有不同的間隔，這會影響圖表中的資料點數和表格中的欄數。例如，以每日細度查看跨越三天的分析將僅顯示三個資料點，而以每小時細度查看跨越三天的分析將顯示 72 個資料點。
* **[!UICONTROL 日期]**：開始和結束日期。為方便您使用，我們提供滾動日期範圍預設和先前儲存的自訂範圍，或者您可以使用行事曆選擇器來選擇固定的日期範圍。

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
