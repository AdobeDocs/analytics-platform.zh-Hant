---
description: Analysis Workspace中的預測功能會使用一系列進階的統計技術來決定預測值。
title: 預測中所使用的統計技術
feature: Visualizations
role: User
source-git-commit: 1bd24ee1163e4615bf5626c51aec9f167352f2f6
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 5%

---


# 預測服務中使用的統計技術

預測服務目前支援Prophet，並且已證明對大多數資料有效且可靠地運作。 Prophet是由Meta所開發的廣泛使用的開放原始碼預測套件。 它會分解資料為趨勢、季節性和事件元件。 Prophet模型非常有效率，並且適用於許多預測應用程式。 此外，模型對於離群值和遺失資料有強大的運作能力。

未來有計畫根據啟發式選取模型，例如針對串流資料選擇「線上近似高斯處理」，或當使用者指定最佳預測準確度且可容許較長的等待時間時，選擇NeuralProphet。

當資料點過多時，服務會自動縮減資料，以確保回應時間。 目標回應時間設為~3秒。 目前，當資料點數量超過5500時，時間序列資料會根據資料長度適當地縮減取樣。 輸出會轉換回原始資料頻率，因此最適化取樣程式不會影響使用者體驗。

可使用多年資料時，可考量假日效應。 目前考慮的假日清單為：

* 馬丁·路德·金日
* 總統日
* 陣亡將士紀念日
* 7 月 4 日
* 感恩節
* 黑色星期五
* 網路星期一
* 聖誕節

此服務也可以執行簡單的異常（離群值）移除作業，例如移除超出六西格瑪範圍的資料點。 預設不會啟用此功能，因為假設所有資料點都是有效的。 異常可能會對模型品質產生負面影響，即使Prophet模型通常可復原異常值。

此服務接受使用者指定的季節性設定，例如每日和每週的季節性設定。 否則，模型會自動選取季節性。 對於不同的資料粒度，此服務會使用不同長度的歷史資料來建立預測模型。 例如，對於每日資料，這會提取超過一年的資料（如果有的話）。 對於每小時資料，此功能會提取八週的資料（如果有的話）。 提取資料可能很耗時，而且有時會導致較長的等待時間。

不同時間詳細程度所需的歷史資料：

| 詳細程度 | 需要歷史資料 |
|---|--:|
| 分鐘 | 3 天 |
| 小時 | 2 週 |
| 日 | 8 週 |
| 週 | 2 年 |
| 月 | 2 年 |
| 季 | 8 季 |
| 年 | 8 年 |


每個指定時間的預測結果都帶有一個預測間隔（由下限和上限定義），預計其中有95%的時間會包含未來觀察值，通常稱為信賴區間。 服務未來的預測範圍沒有限制。 然而，預測的不確定性會隨著更遠的未來日期而增加，反映在較寬的預測間隔中。

此服務不對使用者資料進行任何假設。 例如，服務不會假設資料為非負數。 這表示如果資料呈現強烈向下趨勢，即使所有觀察到的資料點都不是負數，預測和/或其範圍可以是負數。


## 引用

1. 泰勒、肖恩·J和本傑明·萊瑟姆： *大規模預測。* 美國統計師72.1 (2018)：37-45。
1. Triebe、Oskar等： *Neuralprophet：可大規模解釋的預測。* arXiv預先列印arXiv：2111.15397(2021)。
1. 張嘉伯： *時間序列異常偵測。* 美國專利申請#18/057883。
