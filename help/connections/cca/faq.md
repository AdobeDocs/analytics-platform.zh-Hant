---
title: 跨管道分析常見問題集
description: 跨管道分析常見問題集
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '962'
ht-degree: 100%

---

# 常見問題集

## 如何透過跨管道分析，了解人潮在管道間的活動概況？

您可以搭配「資料集 ID」維度使用「流量」視覺效果。

1. 登入 [analytics.adobe.com](https://analytics.adobe.com) 並建立空白的  Workspace 專案。
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

## 如果一個或多個事件中的 Persistent ID 欄位為空白，會發生什麼情況？

如果使用欄位型拼接進行拼接的資料集中事件的 `Persistent ID` 欄位為空白，CCA 會以兩種方式之一填入該事件的 `Stitched ID`：
* 如果 `Transient ID` 欄位非空白，CCA 會使用 `Transient ID` 中的值作為 `Stitched ID`。
* 如果 `Transient ID` 欄位為空白，CCA 也會將 `Stitched ID` 留為空白。 在這種情況下，`Persistent ID`、`Transient ID` 和 `Stitched ID` 將在事件中全部為空白。 在任何使用正在拼接資料集的 CJA 連接中，會從 CJA 捨棄此類事件，其中 `Stitched ID` 被選為 `Person ID`。

## CJA 拼接資料集中的指標與 CJA 非拼接資料集中的類似指標相比，以及與傳統 Adobe Analytics 相比如何？

CJA 中的某些指標與傳統分析中的指標相似，但其他指標則完全不同，具體取決於您要比較的內容。 下表比較了幾個常見的指標：

| **CJA 拼接資料** | **CJA 非拼接資料** | **傳統 Adobe Analytics** | **具有 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人物**= 不同的 `Person ID` 計數，其中 `Stitched ID` 被選為 `Person ID`。 在傳統 Adobe Analytics 中，**人物**&#x200B;可能高於或低於&#x200B;**不重複訪客**，取決於拼接過程的結果。 | **人物** = 不同的 `Person ID` 計數，根據選取為 `Person ID` 的欄位而定。 在 Adobe Analytics Connector (ADC) 資料集中，**人物**&#x200B;類似於傳統 Adobe Analytics 中的&#x200B;**不重複訪客**，如果在 CJA 中 `endUserIDs. _experience. aaid.id` 被選為 `Person ID`。 | **不重複訪客** = 不同訪客 ID 的計數。 注意&#x200B;**不重複訪客**&#x200B;可能與不同 **ECID** 的計數不同。 | 請參閱[人物](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html)。 |
| **工作階段**：根據 CJA 資料檢視中指定的工作階段化設定進行定義。 拼接過程可以將來自多個裝置的各個工作階段合併為單一工作階段。 | **工作階段**：根據 CJA 資料檢視中指定的工作階段化設定進行定義。 | **造訪次數**：請參閱[造訪次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html)。 | **造訪次數**：根據 [CDA 虛擬報告套裝](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html)中指定的工作階段化設定進行定義。  |
| **事件** = CJA 中拼接資料中的列數。一般來說，這應該接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是，請注意上面關於具有空白 `Persistent ID` 的列的常見問題解答。 | **事件** = CJA 中未拼接資料中的列數。一般來說，這應該接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是請注意，如果任何事件在 AEP 資料湖的未拼接資料中具有空白 `Person ID`，在 CJA 中將捨棄 (不包含) 這些事件。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html)。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html)。 |

CJA 和傳統 Adobe Analytics 中的其他指標可能類似。例如，Adobe Analytics [自訂事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html)的總計數 (事件 1-100) 在傳統 Adobe Analytics 和 CJA（無論是拼接還是未拼接）中通常應該非常接近。但是請注意，因為[功能差異](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html)，這可能並不一定都正確，例如 CJA 與傳統 Adobe Analytics 之間的事件重複資料刪除。
