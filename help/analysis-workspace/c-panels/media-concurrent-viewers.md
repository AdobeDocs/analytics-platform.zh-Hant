---
title: 媒體同時檢閱者面板
description: 如何使用和解讀Analysis Workspace中的「媒體同時檢閱者」面板。
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 43%

---

# 媒體同時檢閱者面板 {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="媒體同時檢視者"
>abstract="建立面板以分析特定時段內的同時檢閱者。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="媒體同時檢視者"
>abstract="分析特定時間內的同時檢閱者、檢視最高同時檢閱者數，並可選擇性使用篩選器、維度、維度項目或日期範圍進行劃分與比對。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文會在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_&#x200B;中記錄媒體同時檢閱者面板。<br/>_檢視此文章的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[媒體同時檢閱者面板](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers)。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>「媒體平均每分鐘觀眾數」面板僅適用於已購買Customer Journey Analytics適用的串流媒體收集附加元件的客戶。
>
>如需詳細資訊，請聯絡您的Adobe銷售代表或Adobe客戶團隊。
>

**[!UICONTROL 媒體同時檢閱者]**&#x200B;面板可讓您分析一段時間內的同時檢閱者，並取得尖峰同時檢閱的詳細資訊，並可加以劃分及比較。

您可以分析同時觀看人數，以瞭解人數高峰或趨勢反轉的時間，以針對內容品質和檢視者參與度提供重要解析。 以及協助疑難排解或規劃數量或規模。

在Analysis Workspace中，「同時檢閱者」量度指的是在特定時間點檢視您媒體串流的不重複人數，而不計工作階段數量。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [媒體同時檢閱者面板](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]

## 使用

若要使用&#x200B;**[!UICONTROL 媒體同時檢閱者]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 媒體同時檢閱者]**&#x200B;面板。 有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 請確定您為面板選取資料檢視，該面板具有從串流媒體收集設定的元件。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

### 面板輸入

您可以使用以下輸入設定來設定「媒體同時檢閱者」面板：

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 面板日期範圍]** | 面板的日期範圍預設為「今天」。您可編輯為一次檢視一天或多個月。<br> <br>此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和詳細程度組合結果超過 1440 行，則詳細程度會自動更新以符合完整的日期範圍。 |
| **[!UICONTROL 粒度]** | 粒度的預設為「分鐘」。<br>此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和詳細程度組合結果超過 1440 行，則詳細程度會自動更新以符合完整的日期範圍。 |
| **[!UICONTROL 面板摘要數字]** | 若要查看同時檢閱者的日期或時間詳細資訊，可使用累加數。「最大值」是顯示尖峰同時檢閱的詳細資訊。**[!UICONTROL 最小值]**&#x200B;顯示低谷期的詳細資訊。  面板預設僅會顯示「最大值」，但您可變更為顯示「最小值」或「最大值和最小值」兩者。<br><br>如果您使用劃分功能，每項會顯示累加數。 |
| **[!UICONTROL 序列劃分]** | 您可視需要將視覺效果劃分為篩選器、維度、維度專案或日期範圍。<br>一次最多可檢視10行。 劃分限於單一層級。<br>拖曳維度時，系統會自動根據選取的面板日期範圍選取最上層的維度專案。<br>若要比較日期範圍，請將2個或多個日期範圍拖放到序列劃分篩選器。 |

以下是設定為&#x200B;**[!UICONTROL 分鐘]**&#x200B;詳細程度的面板範例，其中最多&#x200B;**[!UICONTROL 個摘要數字，僅限]**&#x200B;個。 並依&#x200B;**[!UICONTROL 其他]**、**[!UICONTROL 表格]**、**[!UICONTROL 行動電話]**、**[!UICONTROL 遊戲主機]**、**[!UICONTROL 媒體播放器]**、**[!UICONTROL 機上盒]**、**[!UICONTROL 電視]**&#x200B;劃分。

![媒體同時檢閱者系列劃分檢視畫面顯示10個維度、區段或日期範圍中的7個。](assets/concurrent-viewers-series-breakdown.png)

### 面板輸出

「媒體同時檢閱者」面板會傳回一個線圖和累加數，以含有最大和/或最小同時檢閱者的詳細資訊。面板頂端會提供一個摘要行，為您提示您所選取的面板設定。

在任何時候，選取![編輯媒體同時檢閱者面板](/help/assets/icons/Edit.svg)以編輯並重新建置面板。

如果您選取序列劃分，線圖上會顯示一條線，且每項會顯示累加數：

![媒體同時檢閱者輸出。](assets/concurrent-viewers-output.png)

### 資料來源

此面板中能使用的唯一量度是&#x200B;**[!UICONTROL 同時檢閱者]**：

| 量度 | 說明 |
|---|---|
| **[!UICONTROL 同時檢閱者]** | 在特定時間點檢視您媒體串流的不重複人數，而不計工作階段數量。 |

本檢視中不提供自由表格。若要檢視資料來源，您可以從折線圖視覺效果內容功能表下載資料來源，並選取&#x200B;**[!UICONTROL 將資料下載為CSV檔]**。  包含數列劃分。

![反白顯示「將資料下載為CSV檔」的「同時檢閱者」輸出選項。](assets/concurrent-viewers-download-csv.png)

## 常見問題

| 問題 | 回答 |
|---|---|
| 自由表格在哪裡？我如何可看到資料來源？ | 本檢視中無法使用自由表格。您可以從折線圖內容功能表下載資料來源，並選取&#x200B;**[!UICONTROL 將資料下載為CSV檔]**。 |
| 我的詳細程度為何會變更？ | 此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和粒度組合結果超過 1440 列，則粒度會自動更新以符合完整的日期範圍。<br><br>從較大的日期範圍變更為較小的日期範圍時，一旦日期範圍改變，詳細程度就會更新為允許的最低詳細程度。 若要查看更高的粒度，請編輯面板並重建。 |
| 如何比較視訊名稱、篩選器、內容型別和其他專案？ | 若要在單一視覺效果中比較這些專案，請將篩選器、維度或特定維度專案拖曳至系列劃分篩選器中。<br><br>此檢視限於 10 項劃分。若要檢視超過 10 項，您必須使用多個面板。 |
| 我如何比較日期範圍？ | 若要比較單一視覺效果中的日期範圍，可拖動 2 個或多個日期範圍並使用序列劃分篩選器。日期範圍會覆寫面板日期範圍。 |
| 如何改變視覺效果類型？ | 此面板僅允許進行時間序列的線圖視覺效果。 |
| 我是否可執行異常偵測？ | 否。 異常偵測不適用於此面板。 |
| 為何使用不重複人員而非作用中工作階段？ | 使用不重複人員可移除顯示邊界（工作階段同時結束和開始所在處）不需要的「尖峰」。 |
| 讓同時檢閱者檢閱的詳細程度高於分鐘是什麼意思？ | 以大於一分鐘為詳細程度的單位時，同時檢閱者人數是指該時間範圍內所有分鐘數的不重複同時檢閱者的總和。例如，以一小時層級為詳細程度的同時檢閱者，其人數是指該小時內所有分鐘數的不重複同時檢閱者的總和。 |
| Workspace 面板是否會顯示與「同時檢閱者報告」相同的資訊？ | 否。 在Analysis Workspace中，「同時檢閱者」量度的定義是在特定時間點檢視您媒體流的不重複人數。 無論工作階段數量多寡。<br><br>此量度不同於「報告」部分中使用「同時作用中工作階段」的「同時檢閱者」報告。 使用不重複人員可移除顯示邊界（工作階段同時結束和開始所在處）不需要的尖峰。 |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[媒體播放時間面板](media-playback-time-spent.md)
>[媒體平均每分鐘觀眾數面板](average-minute-audience-panel.md)
>