---
title: 跨管道分析常見問題集
description: 跨管道分析常見問題集
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 5eede8eeb5d7e8632dc0d7d580f01ccc7ac8106c
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 59%

---

# 常見問題集

## 如何透過跨管道分析，了解人潮在管道間的活動概況？

您可以搭配「資料集 ID」維度使用「流量」視覺效果。

1. 登入 [analytics.adobe.com](https://analytics.adobe.com) 並建立空白的  Workspace 專案。
2. 按一下左側的「視覺效果」索引標籤，然後將「流量」視覺效果拖曳至右側的畫布上。
3. 按一下左側的「元件」頁籤，將維「資料集ID」拖到標有「Dimension」或「項」的中心位置。
4. 此流量報表為互動式。 按一下任何值，即可將流量展開至接續或先前的頁面。 使用右鍵功能表來展開或收合欄。 同一流量報表中也可使用不同的維度。

如果您要為資料集 ID 維度項目重新命名，可使用查詢資料集。

## 跨管道分析會針對多久以前的訪客重設金鑰？

金鑰重設的回顧期間取決於您需要的資料[重播](replay.md)頻率。 例如，如果將CCA設定為每週重放一次資料，則重新鍵控的回望窗口為七天。 如果設定CCA以每天重播資料，則重新鍵控的回望窗口為一天。

## 如何處理共用裝置？

在某些情況下，可能有多人從同一設備登錄。 例如家中的共用裝置、資料庫中的共用 PC 或零售門市的資訊站。

暫時 ID 會覆寫永久 ID，因此系統會將共用裝置視為不同的使用者 (即便他們都是使用同一部裝置)。

## CCA如何處理單個人擁有多個持久ID的情況？

在某些情況下，單個用戶可以與許多持久ID關聯。 例如使用者經常清除瀏覽器 Cookie 或使用瀏覽器的私密/無痕模式。

永久 ID 的數量與暫時 ID 無關。 單一使用者可使用任意數量的裝置，這不會影響跨管道分析功能彙整不同裝置資料的能力。

## 如果我連絡客戶經理，向對方索取所需資訊，需要多久才能使用金鑰已重設的資料集？

Adobe啟用跨渠道分析後大約一週內即可進行即時縫合。 能否使用回填功能取決於現有資料的數量。如果是小型資料集 (每天不到 100 萬個事件)，通常需要幾天後才能使用，大型資料集 (每天 10 億個事件) 則需等待一週或更久時間。

## 跨設備分析（傳統分析中的一項功能）和跨渠道分析之間有何區別？

[跨設備分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) 是傳統Adobe Analytics特有的功能，使您能夠瞭解人們如何跨設備操作。 它提供了兩個將設備資料連結在一起的工作流：基於場的縫合和設備圖。

[跨渠道分析](../overview.md) 是CJA特有的功能，使您能夠瞭解人們如何跨設備和渠道操作。 它重新鍵入資料集的個人ID，允許該資料集與其他資料集無縫地組合。 該功能在設計上與CDA的基於現場的拼接類似，但在傳統分析和CJA之間的不同資料體系結構上，實現是不同的。

## 跨管道分析如何處理 GDPR 和 CCPA 要求？

Adobe 會根據當地及國際法律規範處理 GDPR 和 CCPA 要求。Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)，以供提交資料存取及刪除要求。 這些要求會同時套用至原始資料集和已重設金鑰的資料集。

## 如果一個或多個事件中的 Persistent ID 欄位為空白，會發生什麼情況？

如果使用欄位型拼接進行拼接的資料集中事件的 `Persistent ID` 欄位為空白，CCA 會以兩種方式之一填入該事件的 `Stitched ID`：

* 如果 `Transient ID` 欄位非空白，CCA 會使用 `Transient ID` 中的值作為 `Stitched ID`。
* 如果 `Transient ID` 欄位為空白，CCA 也會將 `Stitched ID` 留為空白。 在這個例子中， `Persistent ID`。 `Transient ID`, `Stitched ID` 在事件上全部為空。 這些類型的事件是使用正在縫合的資料集從任何CJA連接中刪除的 `Stitched ID` 被選為 `Person ID`。

## CJA 拼接資料集中的指標與 CJA 非拼接資料集中的類似指標相比，以及與傳統 Adobe Analytics 相比如何？

CJA 中的某些指標與傳統分析中的指標相似，但其他指標則完全不同，具體取決於您要比較的內容。 下表比較了幾個常見的指標：

| **CJA 拼接資料** | **CJA 非拼接資料** | **傳統 Adobe Analytics** | **具有 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人物**= 不同的 `Person ID` 計數，其中 `Stitched ID` 被選為 `Person ID`。 在傳統 Adobe Analytics 中，**人物**&#x200B;可能高於或低於&#x200B;**不重複訪客**，取決於拼接過程的結果。 | **人物** = 不同的 `Person ID` 計數，根據選取為 `Person ID` 的欄位而定。 **人物** 在Adobe源連接器資料集中與 **獨特訪問者** 傳統Adobe Analytics `endUserIDs._experience.aaid.id` 選擇為 `Person ID` 在CJA中。 | **不重複訪客** = 不同訪客 ID 的計數。 **獨特訪問者** 可能與不同的計數不同 **ECID** s | 請參閱[人物](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hant)。 |
| **會話**:根據CJA資料視圖中的會話設定定義。 拼接過程可以將來自多個裝置的各個工作階段合併為單一工作階段。 | **會話**:根據CJA資料視圖中指定的會話設定定義。 | **造訪次數**：請參閱[造訪次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hant)。 | **訪問**:根據在 [CDA虛擬報告套件](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hant)。 |
| **事件** = CJA 中拼接資料中的列數。 此度量通常接近 **具體值** 傳統Adobe Analytics。 但是，請注意上面關於具有空白 `Persistent ID` 的列的常見問題解答。 | **事件** = CJA 中未拼接資料中的列數。 此度量通常接近 **具體值** 傳統Adobe Analytics。 但是，請注意，如果任何事件都為空 `Person ID` 在Experience Platform資料湖中未縫合的資料中，這些事件不包括在CJA中。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html)。 |

其他指標在CJA和傳統Adobe Analytics也可以類似。 例如，Adobe Analytics的總計 [自定義事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hant) 1-100通常可以與傳統的Adobe Analytics和CJA（不管是縫製還是未縫製）相媲美。 [功能差異](/help/getting-started/aa-vs-cja/cja-aa.md))，如CJA與傳統Adobe Analytics之間的事件重複消除可能導致兩種產品之間的差異。

## CCA 可以使用「身分對應」欄位嗎？

否，CCA當前無法使用「標識映射」欄位。
