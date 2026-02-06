---
title: 拼接常見問題
description: 瞭解關於銜接的常見問題。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: d1ba2d203738ca9bf74d17bb93712eff26f88f25
workflow-type: tm+mt
source-wordcount: '2149'
ht-degree: 84%

---

# 常見問題集

以下是有關拼接的一些常見問題：

## 跨管道移動

+++ 如何透過拼接深入了解人員在各個管道之間的移動？

您可以搭配「資料集 ID」維度使用「流量」視覺化圖表。

1. 登入 [Customer Journey Analytics](https://analytics.adobe.com) 並建立空白的 Workspace 專案。
2. 選取左側的「**[!UICONTROL **&#x200B;視覺化圖表&#x200B;**]**」索引標籤，然後將「**[!UICONTROL **&#x200B;流量&#x200B;**]**」視覺化圖表拖曳至右側的畫布上。
3. 選取左側的「**[!UICONTROL **&#x200B;元件&#x200B;**]**」索引標籤並將「**[!UICONTROL **&#x200B;資料集 ID **]**」維度拖曳到標記為「**[!UICONTROL **&#x200B;維度或項目&#x200B;**]**」的中心位置。
4. 此流量報告為互動式。若要將流量擴展至接續或先前的頁面，請選取任何值。使用右鍵功能表來展開或收合欄。 同一流量報告中也可使用不同的維度。

如果您要為資料集 ID 維度項目重新命名，可使用查詢資料集。

+++

## 重播

+++ 拼接重播輪廓可以追溯到多久以前？

重新編號的回顧時間範圍取決於您需要的資料重播頻率。例如，如果您設定拼接為每週重播資料一次，則重新編號的回顧時間範圍是 7 天。如果您設定拼接為每天重播資料一次，則重新編號的回顧時間範圍為 1 天。

+++

## 共用裝置

+++ 如何處理共用裝置？

某些情況下，同一部裝置可能會由不同人登入。 例如家中的共用裝置、資料庫中的共用 PC 或零售門市的資訊站。

個人 ID 會覆寫永久 ID，因此系統會將各個共用裝置視為獨立的人員 (即便他們都是使用同一部裝置)。

如需更多資訊，請參閱[共用裝置](/help/use-cases/stitching/shared-devices.md)使用案例。

+++

## 許多永久 ID

+++ 拼接如何處理一個人擁有多個永久 ID 的情況？

在某些情況下，個別使用者可以與多個永久 ID 關聯。例如，個人經常清除瀏覽器的Cookie或使用瀏覽器的私人/無痕模式。

對於欄位型拼接，永久 ID 的數量並不重要，取而代之的是個人 ID。單一使用者可使用任何數量的裝置，這不會影響 Customer Journey Analytics 功能拼接不同裝置資料的能力。

對於圖表式拚接，單一人員可以在身分圖表中有許多永久ID。 圖表型拼接會根據指定的命名空間使用永久 ID。如果同一名稱空間有較多永久ID，則會使用字典法第一個永久ID。

+++

## 拼接過程

+++ 如果我聯絡 Adobe 帳戶團隊，向對方索取所需資訊，需要多久才能使用重新編號的資料集？

Adobe 啟用拼接後，需要約一週才能使用即時拼接功能。能否使用回填功能取決於現有資料的數量。如果是小型資料集 (每天不到 100 萬個事件)，通常需要幾天後才能使用，大型資料集 (每天 10 億個事件) 則需等待一週或更久時間。

+++

## 跨裝置分析與跨管道分析的比較

+++ 跨裝置分析 (傳統 Analytics 中的一項功能) 和跨管道分析有何差異？

[跨裝置分析](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)是傳統 Adobe Analytics 的專屬功能，可讓您了解人們如何在多個裝置之間操作。其提供兩個工作流程將裝置資料連結在一起：欄位型拼接和裝置圖表。

跨管道分析是 Customer Journey Analytics 的專屬使用案例，可讓您了解使用者在不同裝置以及不同管道之間如何操作。其會拼接資料集的個人 ID，讓該資料集可順暢地與其他資料集合併。此功能的操作設計類似於跨裝置分析的欄位型拼接，但實施方式不同，因為傳統 Analytics 和 Customer Journey Analytics 之間的資料架構不同。如需更多資訊，請參閱[拼接](overview.md)和[跨管道分析](../use-cases/cross-channel/cross-channel.md)使用案例。

+++

## 隱私權

+++ 拼接如何處理隱私請求？

Adobe 會根據本地和國際法律來處理隱私請求。Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/home)，以供提交資料存取及刪除要求。 這些要求會同時套用至原始資料集和已重設金鑰的資料集。

>[!IMPORTANT]
>
>做為隱私請求的一部分，取消拼接程序在 2025 年初有所變更。目前取消拼接的程序使用最新版本的已知身分識別將事件重新拼接。將事件重新指派給另一個身分識別，可能會產生不利的法律後果。為解除這些疑慮，自 2025 年起，新的取消拼接程序將使用永久 ID 更新受到隱私請求影響的事件。
> 

舉例來說，您可以想像下列身分識別資料、拼接前和拼接後的事件。

| 身分識別圖 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件資料集 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接後的資料集 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 | 產生的ID | 拼接後的命名空間 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隱私權要求的目前程式**

當收到具有 CustID Bob 的客戶之隱私請求時，帶有刪除線項目的列將被刪除。其他事件會使用身分識別圖來重新拼接。例如，拼接後的資料集中的第一個拼接後的 ID 已更新為 **Alex**。

| 身分識別圖 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 |
|:---:|---|---|---|---|---|---|
| ![刪除輪廓](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件資料集 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![刪除輪廓](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接後的資料集 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 | 產生的ID | 拼接後的命名空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![刪除輪廓](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**新的隱私請求程序**

當收到具有 CustID Bob 的客戶之隱私請求時，帶有刪除線項目的列將被刪除。其他事件會使用永久 ID 重新拼接。例如，拼接後的資料集中的第一個拼接後的 ID 已更新為 **123**。

| 身分識別圖 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 |
|:---:|---|---|---|---|---|---|
| ![刪除輪廓](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件資料集 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![刪除輪廓](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接後的資料集 | ID | 時間戳記 | 永久 ID | 永久命名空間 | 個人 ID | 個人命名空間 | 產生的ID | 拼接後的命名空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![刪除輪廓](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## 空白的永久 ID 值

+++ 如果一個或多個事件中的永久 ID 欄位為空白，會發生什麼情況？

如果在正在拼接的資料集中的事件中，永久ID欄位為空白，該事件的結果ID會以兩種方式之一確定：

* 如果人員ID欄位非空白，Customer Journey Analytics會使用人員ID中的值作為產生的ID。
* 如果人員ID欄位為空白，Customer Journey Analytics也會將產生的ID保留為空白。 在這種情況下，事件的永久ID、人員ID和產生的ID全部空白。 使用正在拼接資料集（其中將產生的ID選為人員ID）的Customer Journey Analytics連線中，會捨棄這些型別的事件。

+++


## 未定義的個人 ID 值

+++ 如果一個或多個事件中的個人 ID 欄位具有預留位置值，例如 `Undefined`，會發生什麼情況？

請留意「個人收合」，這是將拼接套用至使用預留位置值做為暫時 ID 的資料時會發生的情況。在下列範例表格中，來自 CRM 系統的資料集所產生的未定義個人 ID 填入「未定義」值，導致錯誤呈現個人數量。

| 事件 | 時間戳記 | 永久 ID (Cookie ID) | 暫時 ID | 產生的ID （重播後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | 未定義 | **未定義** |
| 4 | 2023-05-12 12:04 | 456 | - | **未定義** |
| 5 | 2023-05-12 12:05 | 789 | 未定義 | **未定義** |
| 6 | 2023-05-12 12:06 | 012 | 未定義 | **未定義** |
| 7 | 2023-05-12 12:07 | 012 | - | **未定義** |
| 8 | 2023-05-12 12:03 | 789 | 未定義 | **未定義** |
| 9 | 2023-05-12 12:09 | 456 | - | **未定義** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 個裝置** | **2 名人員**：<br/>已捨棄事件 1、4、7、9、10 | **2 名人員**：<br/>Cory，未驗證 (收合成一個人) |

+++

## 量度比較

+++ Customer Journey Analytics 拼接後的資料集中的量度，與 Customer Journey Analytics 未拼接的資料集中的類似量度相比，以及與 Adobe Analytics 相比如何？

Customer Journey Analytics 中的某些量度與傳統 Analytics 中的量度類似，但其他量度則有所不同，具體取決於您要比較的內容。下表比較了幾個常見的量度：

| **Customer Journey Analytics 拼接資料** | **Customer Journey Analytics 未拼接資料** | **Adobe Analytics** | **具有 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人員** =不同人員ID的數量，其中產生的ID被選為人員ID。 在傳統 Adobe Analytics 中，**人員**&#x200B;可能多於或少於&#x200B;**不重複訪客數**，取決於拼接程序的結果。 | **人員** = 根據選定為個人 ID 的欄所計算的獨立個人 ID 數量。如果在 Customer Journey Analytics 中 `endUserIDs._experience.aaid.id` 被用做個人 ID，則 Analytics 來源連接器資料集中的&#x200B;**人員**，類似於傳統 Adobe Analytics 中的&#x200B;**不重複訪客**。 | **不重複訪客** = 不同訪客 ID 的計數。 **不重複訪客**&#x200B;可能與相異 **ECID** 的計數不同。 | 請參閱[人員](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/people)。 |
| **工作階段**：根據 Customer Journey Analytics 資料檢視中的工作階段設定來定義。拼接過程可以將來自多個裝置的各個工作階段合併為一個工作階段。 | **工作階段**：根據 Customer Journey Analytics 資料檢視中指定的工作階段設定來定義。 | **造訪次數**：請參閱[造訪次數](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/visits)。 | **造訪次數**：根據 [CDA 虛擬報告套裝](https://experienceleague.adobe.com/en/docs/analytics/components/cda/setup)中指定的工作階段設定來定義。 |
| **事件**= Customer Journey Analytics 中拼接資料中的列數。這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是，請注意上述常見問題中關於永久 ID 為空白的列的說明。 | **事件**= Customer Journey Analytics 中未拼接資料中的列數。這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是請注意，如果在 Experience Platform 資料湖的未拼接資料中，有任何事件的個人 ID 為空白，則 Customer Journey Analytics 不會包含這些事件。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences)。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences)。 |

Customer Journey Analytics 和 Adobe Analytics 中的其他量度可能相似。例如，Adobe Analytics [自訂事件](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/custom-events) 1-100 的總計數，在傳統 Adobe Analytics 和 Customer Journey Analytics 之間是相當的 (無論是拼接後或未拼接)。[功能差異](/help/getting-started/aa-vs-cja/cja-aa.md)，例如 Customer Journey Analytics 與 Adobe Analytics 之間刪除重複事件的功能，可能會導致兩個產品之間產生資料落差。

+++

## 身分識別圖

+++ Customer Journey Analytics 能否使用身分識別圖欄位？

是，Customer Journey Analytics 可於[欄位型](/help/stitching/fbs.md#identitymap)和[圖表型](/help/stitching/gbs.md#identitymap)拼接中使用身分識別圖欄位。

+++

## 切換到圖表型拼接

+++ 從欄位型拼接切換為圖表型拼接時，是否需要重新攝取資料？

資料不需要擷取至Experience Platform。 不過，資料需要在Customer Journey Analytics中重新設定。 請依照下列步驟操作：

1. 使用圖表型拼接設定新的圖表型拼接後的資料集。
1. 以極小的資料時間範圍建立新的暫時連線。
1. 將新的圖表型資料集設定為此暫時連線的一部分。
1. 使用這個新的臨時連線，驗證圖表型拼接是否正常運作。
1. 若圖表型拼接如常運作，請要求對圖表型資料集進行任何額外回填，然後將原始連線中的欄位型資料集與新的圖表型資料集交換。
1. 移除暫時連線。

+++

## 報告中斷

+++ 是否會造成現有報告中斷？

如果您依照上述步驟進行，便不會發生中斷。否則，請向 Adobe Consulting 尋求其他支援。

+++

## 針對身分識別服務啟用資料集

+++ 如何只針對身分識別服務啟用資料集？ 

確認已為Identity Service啟用資料集，以便使用圖表式拚接中的資料集。

您不需要取得 Real-Time Customer Data Platform 的授權，也可以使用圖表型拼接。圖表型拼接是以可用的身分識別圖表而不是即時客戶輪廓為基礎。

若要檢查現有的資料集並僅啟用身分服務的資料集，請使用對僅使用`PATCH`標籤的`/datasets`端點的`unifiedIdentity`要求。 例如：

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedProfile", "value": ["enabled:true"] }
      ]'
```

在請求中使用 `unifiedProfile` 標記的任何情形，若您沒有即時客戶資料輪廓的授權，都會傳回錯誤。

如需更多資訊，請參閱[建立針對輪廓和身分識別啟用的資料集](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset)。

+++ 


## 拼接的名稱空間值

+++ 為何拚接的名稱空間值並非總是符合您在CJA連線中其他資料集中可能使用的身分名稱空間值？

依預設，拼接的名稱空間值為小寫。 因此，`custEmail`會變成`custemail`。 如果您有另一個資料集的身分名稱空間值為`custEmail`，則兩個值不相符。 若要解決報告中的這個行為，您可以使用[lowercase()](/help/data-views/derived-fields/derived-fields.md#lowercase)衍生欄位函式來比對身分名稱空間值。

