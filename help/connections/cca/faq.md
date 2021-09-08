---
title: 跨管道分析常見問題集
description: 跨管道分析常見問題集
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
source-git-commit: 2be442915587780ce41f33b13e27b8cf44e239a6
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 46%

---

# 常見問題集

## 如何透過跨管道分析，了解人潮在管道間的活動概況？

您可以搭配「資料集 ID」維度使用「流量」視覺效果。

1. 登入[analytics.adobe.com](https://analytics.adobe.com)並建立空白的Analysis Workspace專案。
2. 按一下左側的「視覺效果」索引標籤，然後將「流量」視覺效果拖曳至右側的畫布上。
3. 按一下左側的「元件」索引標籤，然後將「資料集 ID」維度拖曳至標示為「維度或項目」的中央位置。
4. 此流量報表為互動式。按一下任何值，即可將流量展開至接續或先前的頁。使用右鍵功能表來展開或收合欄。同一流量報表中也可使用不同的維度。

如果您要為資料集 ID 維度項目重新命名，可使用查詢資料集。

## 跨管道分析會針對多久以前的訪客重設金鑰？

金鑰重設的回顧期間取決於您需要的資料[重播](replay.md)頻率。舉例來說，如果您設定跨管道分析每週重播資料一次，金鑰重設的回顧期間為 7 天。如果您設定跨管道分析每天重播資料一次，則金鑰重設的回顧期間為 1 天。

## 如何處理共用裝置？

某些情況下，同一部裝置可能會由不同人登入，例如家中的共用裝置、資料庫中的共用 PC 或零售門市的資訊站。

暫時 ID 會覆寫永久 ID，因此系統會將共用裝置視為不同的使用者 (即便他們都是使用同一部裝置)。

## 跨管道分析如何處理單一人員擁有大量永久 ID 的情況？

某些情況下，個別使用者可與大量永久 ID 建立關聯，例如使用者經常清除瀏覽器 Cookie 或使用瀏覽器的私密/無痕模式。

永久 ID 的數量與暫時 ID 無關。單一使用者可使用任意數量的裝置，這不會影響跨管道分析功能彙整不同裝置資料的能力。

## 如果我連絡客戶經理，向對方索取所需資訊，需要多久才能使用金鑰已重設的資料集？

Adobe 啟用跨管道分析後，需要約 1 週才能使用即時彙整功能。能否使用回填功能取決於現有資料的數量。如果是小型資料集 (每天不到 100 萬個事件)，通常需要幾天後才能使用，大型資料集 (每天 10 億個事件) 則需等待一週或更久時間。

## 跨管道分析如何處理 GDPR 和 CCPA 要求？

Adobe 會根據當地及國際法律規範處理 GDPR 和 CCPA 要求。Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)，以供提交資料存取及刪除要求。這些要求會同時套用至原始資料集和已重設金鑰的資料集。

## 若一或多個事件中的「永久ID」欄位空白，會發生什麼事？

如果`Persistent ID`欄位在以欄位匯整結合之資料集中的事件上空白，跨管道分析會以兩種方式之一填入該事件的`Stitched ID`:
* 如果`Transient ID`欄位不空白，跨管道分析會使用`Transient ID`中的值做為`Stitched ID`。
* 如果`Transient ID`欄位空白，跨管道分析也會將`Stitched ID`留空。 在此情況下，事件上的`Persistent ID`、`Transient ID`和`Stitched ID`都會空白。 此類事件會從CJA中，使用匯整的資料集（其中`Stitched ID`選為`Person ID`），從任何CJA連線中刪除。

## CJA匯整資料集中的量度與CJA未匯整資料集中的類似量度以及傳統Adobe Analytics有何不同？

CJA中的某些量度與傳統Analytics中的量度類似，但其他量度則大相逕庭，端視您比較的內容而定。 下表比較數種常見量度：

| **CJA匯整資料** | **CJA未匯整資料** | **傳統Adobe Analytics** | **含CDA的Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People**  =被選 `Person ID`為的不 `Stitched ID` 重複 `Person ID`數。**** 根據匯整程式的結果， **傳** 統Adobe Analytics中的人數可能會高於或低於「不重複訪客」。 | **People**  =根據選 `Person ID`取為的欄計算不同 `Person ID`的。**** 如果您在CJA中選擇「 」，Adobe Analytics Connector(ADC)資 **料集** 中的「獨特訪 `endUserIDs. _experience. aaid.id` 客」與傳統Adobe Analytics `Person ID` 中的「不重複」。 | **不重複訪客** =不重複訪客ID的計數。請注意，**獨特訪客**&#x200B;可能與不同&#x200B;**ECID** s的計數不同。 | 請參閱[People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)。 |
| **工作階段**:是根據CJA資料檢視中指定的工作階段化設定來定義。匯整程式可將多部裝置的個別工作階段合併為單一工作階段。 | **工作階段**:是根據CJA資料檢視中指定的工作階段化設定來定義。 | **瀏覽**:請參閱 [造訪](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)。 | **瀏覽**:是根據CDA虛擬報表套裝中指定的工作階段 [化設定來定義](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en)。 |
| **事件**  = CJA中匯整資料的列數。一般而言，這應該會接近傳統Adobe Analytics中的&#x200B;**發生次數**。 不過，請注意上述關於空白`Persistent ID`列的常見問題集。 | **事件**  = CJA中未匯整資料的列數。一般而言，這應該會接近傳統Adobe Analytics中的&#x200B;**發生次數**。 不過，請注意，如果AEP資料湖的未拼接資料中有任何事件具有空白`Person ID`，則這些事件會（未包含）拖放到CJA中。 | **發生次數**:請參 [閱發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 | **發生次數**:請參 [閱發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 |

CJA和傳統Adobe Analytics中的其他量度可能相似。 例如，在傳統Adobe Analytics和CJA中，Adobe Analytics [自訂事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en)（事件1-100）的總計數通常應非常接近（不論是匯整或取消匯整）。 但請注意，這不一定是真，因為[功能](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en)的差異，例如CJA與傳統Adobe Analytics之間的事件去重複化。
