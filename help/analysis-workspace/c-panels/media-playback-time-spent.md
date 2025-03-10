---
title: 「媒體播放時間」面板
description: 如何使用和解讀Analysis Workspace中的「媒體播放時間」面板。
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 51%

---

# 媒體播放時間面板 {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="媒體播放時間"
>abstract="建立一個面板來分析一段時間內的視訊觀看量，包括各種詳細程度等級以及劃分和比較的功能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="媒體播放時間"
>abstract="分析特定時間內的影片觀看趨勢、選取不同詳細程度，並可選擇性使用篩選器、維度、維度項目或日期範圍進行劃分與比對。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文記錄了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_&#x200B;中的媒體播放時間面板。<br/>_請參閱這篇文章的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[媒體播放時間面板](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent)。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>「媒體平均每分鐘觀眾數」面板僅適用於已購買Customer Journey Analytics適用的串流媒體收集附加元件的客戶。
>如需詳細資訊，請聯絡您的Adobe銷售代表或Adobe客戶團隊。
>

**[!UICONTROL 媒體播放時間]**&#x200B;面板可啟用一段時間的播放分析，提供尖峰同時觀看人數的詳細資訊，並可加以劃分及比較。

在Analysis Workspace中，「播放時間」是指在特定時間點觀看您的媒體串流所花費的時間。 其中包含暫停、緩衝和開始時間。

已購買串流媒體收集附加元件的客戶可分析所花費的播放時間，以獲得內容品質和檢視者參與度的寶貴見解。 以及在疑難排解或規劃數量或規模時提供協助。

播放時間可協助您瞭解：

* 尖峰同時觀看人數的發生位置。

* 下降發生在何處。


>[!BEGINSHADEBOX]

如需示範視訊，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [媒體播放時間](https://video.tv.adobe.com/v/338699){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


## 使用

若要使用&#x200B;**[!UICONTROL 媒體播放時間]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 媒體播放時間]**&#x200B;面板。 有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 請確定您為面板選取資料檢視，該面板具有從串流媒體收集設定的元件。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。


### 面板輸入

您可使用以下這些輸入設定來設定「媒體播放時間」面板。

| 設定 | 說明 |
|---|---|
| 面板日期範圍 | 面板的日期範圍預設為「今天」。您可將其編輯為一次檢視一天或多個月。<br>此視覺效果僅限 1440 列資料 (例如，以分鐘為最小單位測量 24 小時)。如果日期範圍和粒度組合結果超過 1440 行，則粒度會自動更新以符合完整的日期範圍。 |
| 粒度 | 粒度的預設為「分鐘」。<br>此視覺效果僅限 1440 列資料 (例如，以分鐘為最小單位測量 24 小時)。如果日期範圍和粒度組合結果超過 1440 行，則粒度會自動更新以符合完整的日期範圍。 |
| 面板摘要數字 | 若要查看播放時間的日期或時間詳細資訊，可使用摘要數字。「最大值」會顯示高峰期同時觀看人數的詳細資訊。「最小值」會顯示低谷期的詳細資訊。「總和」會加總選取範圍所花費的總播放時間。面板預設僅顯示「最大值」，但您可加以改變，以顯示「最小值」、「總和」或三者的任何組合。<br>如果您使用劃分功能，每項會顯示累加數。 |
| 序列劃分 | 您可視需要將視覺效果劃分為篩選器、維度、維度專案或日期範圍。<p>- 一次最多可檢視 10 行。劃分限於單一層級。</p><p> — 拖曳維度時，系統會自動根據所選面板日期範圍選取最上層的維度專案。</p>- 若要比較日期範圍，請將 2 個或多個日期範圍拖放到序列劃分篩選器。 |
| 時間格式 | 您可以在`Hours:Minutes:Seconds` （預設）或`Minutes` （以整數顯示，四捨五入為0.5）中檢視播放時間。 |
| 日期序列顯示 | 如果您選擇至少兩個日期範圍篩選作為系列劃分，您將看到選取覆蓋（預設）或序列的選項。 覆蓋顯示具有常見x軸起點的線條，以便它們平行執行，而序列顯示具有特定x軸起點的線條。 如果資料排列整齊（例如，篩選器1在下午8:44結束，而篩選器2在下午8:45開始），則這些線條會依序顯示。 |


![媒體劇本逗留時間預設檢視。](assets/mpts_default_view.png)

### 面板輸出

「媒體播放時間」面板會返回折線圖和摘要數字，以包括播放時間最大值、最小值和/或總和的詳細資訊。面板頂端會提供一個摘要行，為您提示您所選取的面板設定。

在任何時候，選取![編輯媒體播放時間花費面板](/help/assets/icons/Edit.svg)以編輯和重建面板。

如果您選取序列劃分，線圖上會顯示一條線，且每項會顯示累加數：

![媒體播放時間輸出顯示折線圖和摘要。](assets/mpts_outputs1.png)

### 資料來源

此面板中能使用的唯一量度是「播放時間」。

| 量度 | 說明 |
|---|---|
| 播放時間 | 在選取的粒度期間檢視的內容總數`hours:minutes:seconds` （或`minutes`），包括暫停、緩衝和開始時間。 |

## 常見問題

| 問題 | 回答 |
|---|---|
| 自由表格在哪裡？我如何可看到資料來源？ | <p></p><p>本檢視中無法使用自由表格。若要下載資料來源，請從折線圖中的快顯選單中選取下載CSV檔案的選項。</p> |
| <p>為什麼我的粒度改變了？</p> | <p>此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和粒度組合結果超過 1440 列，則粒度會自動更新以符合完整的日期範圍。</p><p></p><p>從較大的日期範圍變更為較小的日期範圍時，一旦日期範圍改變，詳細程度將更新為允許的最低詳細程度。 若要查看更高的粒度，請編輯面板並重建。</p> |
| <p></p><p>如何比較視訊名稱、篩選器、內容型別等？</p> | <p>若要在單一視覺效果中比較這些，請將篩選器、維度或特定維度專案拖曳至系列劃分篩選器中。</p><p></p><p>此檢視限於 10 項劃分。若要檢視超過 10 項，您必須使用多個面板。</p> |
| 我如何比較日期範圍？ | 若要比較單一視覺效果中的日期範圍，可拖動 2 個或多個日期範圍以使用系列劃分。這些日期範圍會覆寫面板日期範圍。 |
| 如何改變視覺效果類型？ | <p></p><p>此面板僅允許進行時間序列的線圖視覺效果。</p> |
| 我是否可執行異常偵測？ | <p></p><p>否。 異常偵測不適用於此面板。</p> |


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[媒體平均每分鐘觀眾數面板](average-minute-audience-panel.md)
>[媒體同時檢閱者面板](media-concurrent-viewers.md)
>
