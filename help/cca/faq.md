---
title: 跨管道分析常見問題集
description: 跨管道分析常見問題集
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 8e902022c07376fb3c13cad5fd5b1efa655c9424
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 95%

---

# 常見問題集

## 如何透過跨管道分析，了解人潮在管道間的活動概況？

您可以搭配「資料集 ID」維度使用「流量」視覺效果。

1. 登入 [analytics.adobe.com](https://analytics.adobe.com) 並建立空白的  Workspace 專案。
2. 按一下左側的「視覺效果」索引標籤，然後將「流量」視覺效果拖曳至右側的畫布上。
3. 按一下左側的「元件」索引標籤並將維度的「資料集 ID」拖曳到標記為「維度或項目」的中心位置。
4. 此流量報表為互動式。 按一下任何值，即可將流量展開至接續或先前的頁面。 使用右鍵功能表來展開或收合欄。 同一流量報表中也可使用不同的維度。

如果您要為資料集 ID 維度項目重新命名，可使用查詢資料集。

## 跨管道分析會針對多久以前的訪客重設金鑰？

金鑰重設的回顧期間取決於您需要的資料[重播](replay.md)頻率。 例如，如果您設定 CCA 每週重播資料一次，則重新輸入的回顧期間為 7 天。 如果您設定 CCA 每天重播資料一次，則重新輸入的回顧期間為 1 天。

## 如何處理共用裝置？

某些情況下，同一部裝置可能會由不同人登入。 例如家中的共用裝置、資料庫中的共用 PC 或零售門市的資訊站。

暫時 ID 會覆寫永久 ID，因此系統會將共用裝置視為不同的使用者 (即便他們都是使用同一部裝置)。

## CDA 如何處理一個人擁有多個永久 ID 的情況？

在某些情況下，個別使用者可以關聯至多個永久 ID。 例如使用者經常清除瀏覽器 Cookie 或使用瀏覽器的私密/無痕模式。

永久 ID 的數量與暫時 ID 無關。 單一使用者可使用任意數量的裝置，這不會影響跨管道分析功能彙整不同裝置資料的能力。

## 我聯絡Adobe帳戶團隊並取得所需資訊後，重新輸入的資料集需要多久才能使用？

Adobe 啟用跨頻道分析後，需要約一週才能使用即時彙整功能。能否使用回填功能取決於現有資料的數量。小型資料集（每天少於100萬個事件）通常需要數天，而大型資料集（每天10億個事件）則可能需要一週或更久。

## 跨裝置分析 (傳統 Analytics 中的一項功能) 和跨頻道分析有何差異？

[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)是傳統 Adobe Analytics 的專屬功能，可讓您了解人們如何跨裝置運作。 它提供兩個將裝置資料連結在一起的工作流程：欄位式拚接和裝置圖表。

[跨頻道分析](/help/cca/overview.md)是 CJA 的專屬功能，可讓您同時了解人們如何跨裝置和頻道運作。 它會重新輸入資料集的人員 ID，讓該資料集可順暢地與其他資料集合併。 此功能在設計上的運作類似於 CDA 的欄位式拚接，但實作方式不同，因為傳統 Analytics 和 CJA 之間的資料架構不同。

## 跨管道分析如何處理 GDPR 和 CCPA 要求？

Adobe 會根據當地及國際法律規範處理 GDPR 和 CCPA 要求。Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)，以供提交資料存取及刪除要求。 這些要求會同時套用至原始資料集和已重設金鑰的資料集。

## 如果一個或多個事件中的 Persistent ID 欄位為空白，會發生什麼情況？

如果使用欄位型拼接進行拼接的資料集中事件的 `Persistent ID` 欄位為空白，CCA 會以兩種方式之一填入該事件的 `Stitched ID`：

* 如果 `Transient ID` 欄位非空白，CCA 會使用 `Transient ID` 中的值作為 `Stitched ID`。
* 如果 `Transient ID` 欄位為空白，CCA 也會將 `Stitched ID` 留為空白。 在這種情況下，事件中的 `Persistent ID`、`Transient ID` 和 `Stitched ID` 全部空白。 使用正在拼接資料集 (其中 `Stitched ID` 被選為 `Person ID`) 的 CJA 連線中，會從 CJA 捨棄這些類型的事件。

## CJA 拼接資料集中的指標與 CJA 非拼接資料集中的類似指標相比，以及與傳統 Adobe Analytics 相比如何？

CJA 中的某些指標與傳統分析中的指標相似，但其他指標則完全不同，具體取決於您要比較的內容。 下表比較了幾個常見的指標：

| **CJA 拼接資料** | **CJA 非拼接資料** | **傳統 Adobe Analytics** | **具有 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人物**= 不同的 `Person ID` 計數，其中 `Stitched ID` 被選為 `Person ID`。 在傳統 Adobe Analytics 中，**人物**&#x200B;可能高於或低於&#x200B;**不重複訪客**，取決於拼接過程的結果。 | **人物** = 不同的 `Person ID` 計數，根據選取為 `Person ID` 的欄位而定。 在 Adobe 來源連接器資料集中，**「人員」**&#x200B;類似於傳統 Adobe Analytics 中的&#x200B;**「不重複訪客」**，如果在 CJA 中 `endUserIDs._experience.aaid.id` 被選為 `Person ID`。 | **不重複訪客** = 不同訪客 ID 的計數。 **不重複訪客**&#x200B;可能與相異 **ECID** 的計數不同。 | 請參閱[人員](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hant)。 |
| **工作階段**：根據 CJA 資料檢視中的工作階段設定來定義。 拼接過程可以將來自多個裝置的各個工作階段合併為一個工作階段。 | **工作階段**：根據 CJA 資料檢視中指定的工作階段設定來定義。 | **造訪次數**：請參閱[造訪次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hant)。 | **造訪次數**：根據 [CDA 虛擬報告套裝](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hant)中指定的工作階段設定來定義。 |
| **事件** = CJA 中拼接資料中的列數。 這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是，請注意上面關於具有空白 `Persistent ID` 的列的常見問題解答。 | **事件** = CJA 中未拼接資料中的列數。 這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是請注意，如果任何事件在 Experience Platform 資料湖的未拼接資料中具有空白 `Person ID`，則 CJA 中不會包含這些事件。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 |

CJA 和傳統 Adobe Analytics 中的其他量度可能類似。 例如，Adobe Analytics [自訂事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hant) 1-100 的總計數，通常在傳統 Adobe Analytics 和 CJA 之間可以比較 (無論是拼接還是未拼接)。 [功能差異](/help/getting-started/aa-vs-cja/cja-aa.md) (例如 CJA 與傳統 Adobe Analytics 之間的事件刪除重複資料功能) 可能會導致兩個產品之間有所出入。

## CCA 可以使用「身分對應」欄位嗎？

否，CCA 目前無法使用「身分對應」欄位。
