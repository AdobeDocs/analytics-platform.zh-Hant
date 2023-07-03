---
title: 拼接常見問題集
description: 彙整的常見問題
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 35%

---

# 常見問題

以下是有關拼接的一些常見問題：

+++**如何使用拼接來瞭解人們如何從一個頻道移動到另一個頻道？**

您可以搭配「資料集 ID」維度使用「流量」視覺效果。

1. 登入 [Customer Journey Analytics](https://analytics.adobe.com) 並建立一個空白的工作區專案。
2. 選取 **[!UICONTROL **&#x200B;視覺效果&#x200B;**]** 標籤並拖曳 **[!UICONTROL **&#x200B;流量&#x200B;**]** 視覺效果移至右側的畫布。
3. 選取 **[!UICONTROL **&#x200B;元件&#x200B;**]** 標籤並拖曳維度 **[!UICONTROL **&#x200B;資料集ID **]** 至標示為的中央位置 **[!UICONTROL ** Dimension或專案&#x200B;**]**.
4. 此流量報表為互動式。 若要將流量展開至後續或先前的頁面，請選取任一值。 使用右鍵功能表來展開或收合欄。 同一流量報表中也可使用不同的維度。

如果您要為資料集 ID 維度項目重新命名，可使用查詢資料集。

+++

+++**彙整重播訪客可追溯到多久以前？**

金鑰重設的回顧期間取決於您需要的資料[重播](explained.md)頻率。 例如，如果您將拼接設定為每星期重播資料一次，則金鑰重設的回顧期間為七天。 如果您將拼接設定為每天重播資料，則金鑰重設的回顧期間為一天。

+++

+++**如何處理共用裝置？**

某些情況下，同一部裝置可能會由不同人登入。 例如家中的共用裝置、資料庫中的共用 PC 或零售門市的資訊站。

暫時 ID 會覆寫永久 ID，因此系統會將共用裝置視為不同的使用者 (即便他們都是使用同一部裝置)。

+++

+++**彙整如何處理單一人員擁有多個永久ID的情況？**

在某些情況下，個別使用者可以關聯至多個永久 ID。 例如，個人經常清除瀏覽器的Cookie或使用瀏覽器的私人/無痕模式。

永久 ID 的數量與暫時 ID 無關。 單一使用者可屬於任意數量裝置，不會影響Customer Journey Analytics跨裝置彙整的能力。

+++

+++**在連絡我的Adobe客戶團隊取得所需的資訊後，需要多久才能使用金鑰已重設的資料集？**

Adobe啟用彙整功能後，需要約一週才能使用即時彙整。 能否使用回填功能取決於現有資料的數量。如果是小型資料集 (每天不到 100 萬個事件)，通常需要幾天後才能使用，大型資料集 (每天 10 億個事件) 則需等待一週或更久時間。

+++

+++**跨裝置分析（傳統Analytics中的一項功能）和跨管道分析有何不同？**

[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) 是傳統Adobe Analytics的專屬功能，可讓您瞭解人們如何跨裝置運作。 它提供兩個將裝置資料連結在一起的工作流程：欄位式拚接和裝置圖表。

跨管道分析是Customer Journey Analytics專屬的使用案例，可讓您同時瞭解人們如何跨裝置和管道運作。 它會拼接資料集的人員ID，使該資料集可順暢地與其他資料集結合。 此功能在設計上的運作方式與跨裝置分析欄位式銜接類似，但由於傳統Analytics和Customer Journey Analytics之間的資料架構不同，因此實作方式不同。 另請參閱 [拼接](overview.md) 和 [跨頻道分析](../use-cases/cross-channel/cross-channel.md) 使用案例以取得更多資訊。

+++**彙整如何處理GDPR和CCPA請求？**

Adobe會根據當地及國際法律規範處理GDPR和CCPA要求。 Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)，以供提交資料存取及刪除要求。 這些要求會同時套用至原始資料集和已重設金鑰的資料集。

+++

+++**如果一個或多個事件中的 Persistent ID 欄位為空白，會發生什麼情況？**

如果彙整之資料集中的事件的「永久ID」欄位為空白，該事件的彙整ID會以兩種方式之一確定：

* 如果「暫時ID」欄位非空白，Customer Journey Analytics會使用「暫時ID」中的值作為拼接ID。
* 如果「暫時ID」欄位為空白，Customer Journey Analytics也會將「彙整ID」留空。 在這種情況下，事件中的永久ID、暫時ID和彙整ID都為空白。 使用正在拼接資料集（其中已拼接ID被選為人員ID）的任何Customer Journey Analytics連線中，會捨棄這些型別的事件。

+++

+++**Customer Journey Analytics拼接資料集中的量度與Customer Journey Analytics未拼接資料集中的類似量度以及與Adobe Analytics相比如何？**

Customer Journey Analytics中的某些量度類似於傳統Analytics中的量度，但其他量度則有所不同，具體取決於您要比較的內容。 下表比較了幾個常見的指標：

| **Customer Journey Analytics拼接資料** | **Customer Journey Analytics未彙整的資料** | **Adobe Analytics** | **具有 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人員** =將彙整ID選為人員ID的不同人員ID計數。 在傳統 Adobe Analytics 中，**人物**&#x200B;可能高於或低於&#x200B;**不重複訪客**，取決於拼接過程的結果。 | **人員** =根據選取為人員ID的欄的不同人員ID計數。 **人員** 在Adobe來源聯結器資料集中，類似於 **不重複訪客** 在傳統Adobe Analytics中，如果 `endUserIDs._experience.aaid.id` 在Customer Journey Analytics中作為人員ID使用。 | **不重複訪客** = 不同訪客 ID 的計數。 **不重複訪客**&#x200B;可能與相異 **ECID** 的計數不同。 | 請參閱[人員](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hant)。 |
| **工作階段**：根據Customer Journey Analytics資料檢視中的工作階段設定來定義。 拼接過程可以將來自多個裝置的各個工作階段合併為一個工作階段。 | **工作階段**：根據Customer Journey Analytics資料檢視中指定的工作階段設定來定義。 | **造訪次數**：請參閱[造訪次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hant)。 | **造訪次數**：根據 [CDA 虛擬報告套裝](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hant)中指定的工作階段設定來定義。 |
| **事件** =Customer Journey Analytics中拼接資料中的列數。 這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是，請注意上面關於具有空白永久ID的列的常見問題集。 | **事件** =Customer Journey Analytics中未拼接資料中的列數。 這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是請注意，如果任何事件在Experience Platform資料湖的未拼接資料中具有空白的人員ID，則這些事件不會包含在Customer Journey Analytics中。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 |

Customer Journey Analytics和Adobe Analytics中的其他量度可能類似。 例如，Adobe Analytics的總計數 [自訂事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hant) 1-100在傳統Adobe Analytics和Customer Journey Analytics之間是可比較的（無論是拼接還是未拼接）。 [功能差異](/help/getting-started/aa-vs-cja/cja-aa.md))，例如Customer Journey Analytics與Adobe Analytics之間的事件重複資料刪除，可能會導致兩個產品之間有所出入。

+++

+++**Customer Journey Analytics可以使用「身分對應」欄位嗎？**

否，Customer Journey Analytics目前無法使用「身分對應」欄位進行拼接。

+++
