---
title: 媒體同時檢閱者面板
description: 如何使用和解讀 Analysis Workspace 中的「媒體同時檢閱者」面板。
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 75%

---

# 「媒體同時檢閱者」面板

您可以分析同時觀看人數，以了解發生高峰期同時觀看人數或客戶流失的時間，以針對內容品質和檢視者參與度提供重要解析，並有助於疑難排解或完成數量和規模的相關規劃。

在Analysis Workspace中，「同時檢閱者」指的是在特定時間點檢視您媒體串流的不重複人數，而不計工作階段數量。

「媒體同時檢閱者」面板可啟用長時間進行的同時檢閱者分析，並可提供尖峰同時檢閱的詳細資訊，以及具備分項和比較的能力。若要存取「媒體同時檢閱者」面板，可瀏覽至具有從串流媒體收集附加元件啟用的元件的資料檢視。 然後，按一下最左側的面板圖示，並將面板拖放到您的 Analysis Workspace 專案中。

以下是這個面板的影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## 面板輸入 {#Input}

您可以使用下列輸入設定來設定「媒體同時檢閱者」面板：

| 設定 | 說明 |
|---|---|
| 面板日期範圍 | 面板的日期範圍預設為「今天」。您可編輯為一次檢視一天或多個月。<br> <br>此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和詳細程度組合結果超過 1440 行，則詳細程度會自動更新以符合完整的日期範圍。 |
| 詳細程度 | 詳細程度的預設為「分鐘」。<br> <br>此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和詳細程度組合結果超過 1440 行，則詳細程度會自動更新以符合完整的日期範圍。 |
| 面板摘要數字 | 若要查看同時檢閱者的日期或時間詳細資訊，可使用累加數。「最大值」是顯示尖峰同時檢閱的詳細資訊。「最小值」是顯示低谷的詳細資訊。面板預設僅會顯示「最大值」，但您可變更為顯示「最小值」或「最大值和最小值」兩者。<br><br>如果您使用劃分功能，每項會顯示累加數。 |
| 序列劃分 | 您可視需要將視覺效果劃分為篩選器、維度、維度專案或日期範圍。 <br><br>- 一次最多可檢視多達 10 行。劃分限於單一層級。<br><br>- 拖動一個維度時，系統將根據所選面板日期範圍自動選擇最上層維度項目。<br><br>- 若要比較日期範圍，請將 2 個或多個日期範圍拖放到序列劃分篩選器。 |

### 預設視圖

![媒體同時檢閱者預設檢視。](assets/concurrent-viewers-default.png)


### 序列劃分檢視

![媒體同時檢閱者系列劃分檢視畫面顯示10個維度、區段或日期範圍中的7個。](assets/concurrent-viewers-series-breakdown.png)

## 面板輸出 {#Output}

「媒體同時檢閱者」面板會傳回一個線圖和累加數，以含有最大和/或最小同時檢閱者的詳細資訊。面板頂端會提供一個摘要行，為您提示您所選取的面板設定。

您可以隨時按一下右上方的編輯鉛筆來編輯和重建面板。

如果您已選取序列劃分、線圖上的一條線，則每項會顯示累加數：

![媒體同時檢閱者輸出。](assets/concurrent-viewers-output.png)

### 資料來源

此面板中使用的唯一量度是「同時檢閱者」：

| 量度 | 說明 |
|---|---|
| 同時檢閱者 | 在特定時間點檢視您媒體流的不重複人數，而不計工作階段數量。<br><br>這與「報告」部分中使用「同時作用中工階段」的「同時檢閱者」報告不同。使用不重複人員可移除顯示邊界（工作階段同時結束和開始所在處）不需要的「尖峰」。 |

本檢視中不提供自由表格。為了查看資料來源，您可以在線圖按一下右鍵並下載為 .csv 檔。系列劃分會包含在內。


![反白顯示「將資料下載為CSV檔」的「同時檢閱者」輸出選項。](assets/concurrent-viewers-download-csv.png)

## 常見問題 {#FAQ}

| 問題 | 回答 |
|---|---|
| 自由表格在哪裡？我如何可看到資料來源？ | 本檢視中無法使用自由表格。您可以在線圖按一下右鍵並下載為 CSV 檔，即可下載資料來源。 |
| 我的詳細程度為何會變更？ | 此視覺效果僅限 1440 列資料 (例如以分鐘為最小單位測量 24 小時)。如果日期範圍和詳細程度組合結果超過 1440 行，則詳細程度將自動更新以符合完整的日期範圍。<br><br>從較大的日期範圍內變更為較小的日期範圍時，一旦日期範圍改變，詳細程度將更新為允許的最低詳細程度。若要查看更高的詳細程度，請編輯面板並重建。 |
| 如何比較視訊名稱、篩選器、內容型別等？ | 若要在單一視覺效果中比較這些，請將篩選器、維度或特定維度專案拖曳至系列劃分篩選器中。<br><br>此檢視限於 10 項劃分。若要檢視超過 10 項，您必須使用多個面板。 |
| 我如何比較日期範圍？ | 若要比較單一視覺效果中的日期範圍，可拖動 2 個或多個日期範圍並使用序列劃分篩選器。這些日期範圍將覆蓋面板日期範圍。 |
| 如何改變視覺效果類型？ | 此面板僅允許進行時間序列的線圖視覺效果。 |
| 我是否可執行異常偵測？ | 否。 異常偵測不適用於此面板。 |
| 為何使用不重複人員而非作用中工作階段？ | 使用不重複人員可移除顯示邊界（工作階段同時結束和開始所在處）不需要的「尖峰」。 |
| 讓同時檢閱者檢閱的詳細程度高於分鐘是什麼意思？ | 以大於一分鐘為詳細程度的單位時，同時檢閱者人數是指該時間範圍內所有分鐘數的不重複同時檢閱者的總和。例如，以一小時層級為詳細程度的同時檢閱者，其人數是指這小時所有分鐘數的不重複同時檢閱者的總和。 |
| Workspace 面板是否會顯示與「同時檢閱者報告」相同的資訊？ | 否。 在Analysis Workspace中，「同時檢閱者」的定義是在特定時間點檢視您媒體流的不重複人數，而不計工作階段數量。<br><br>這與「報告」部分中使用「同時作用中工階段」的「同時檢閱者」報告不同。使用不重複人員可移除顯示邊界（工作階段同時結束和開始所在處）不需要的「尖峰」。 |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
