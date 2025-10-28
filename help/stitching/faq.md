---
title: 拼接常見問題集
description: 銜接的常見問題
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 359fe2a718ccef816377083aceb2652b4a905072
workflow-type: tm+mt
source-wordcount: '2069'
ht-degree: 24%

---

# 常見問題

以下是有關拼接的一些常見問題：

## 跨頻道移動

+++ 如何使用拼接來瞭解人們如何從一個管道移至另一個管道？

您可以搭配「資料集 ID」維度使用「流量」視覺效果。

1. 登入[Customer Journey Analytics](https://analytics.adobe.com)並建立空白的Workspace專案。
2. 選取左側的&#x200B;**[!UICONTROL **&#x200B;視覺效果&#x200B;**]**&#x200B;索引標籤，然後將&#x200B;**[!UICONTROL **&#x200B;流量&#x200B;**]**&#x200B;視覺效果拖曳至右側的畫布。
3. 選取左側的&#x200B;**[!UICONTROL **&#x200B;元件&#x200B;**]**&#x200B;索引標籤，並將維度&#x200B;**[!UICONTROL **&#x200B;資料集ID **]**&#x200B;拖曳至標示為&#x200B;**[!UICONTROL **&#x200B; Dimension或專案&#x200B;**]**&#x200B;的中央位置。
4. 此流量報表為互動式。 若要將流量展開至後續或先前的頁面，請選取任一值。 使用右鍵功能表來展開或收合欄。 同一流量報表中也可使用不同的維度。

如果您要為資料集 ID 維度項目重新命名，可使用查詢資料集。

+++

## 重播

+++ 拼接重播設定檔可以追溯到多久之前？

金鑰重設的回顧期間取決於您需要的資料重播頻率。 例如，如果您設定拚接每週重播資料一次，則金鑰重設的回顧期間為七天。 如果您將拼接設定為每天重播資料一次，則金鑰重設的回顧期間為一天。

+++

## 共用裝置

+++ 如何處理共用裝置？

某些情況下，同一部裝置可能會由不同人登入。 例如家中的共用裝置、資料庫中的共用 PC 或零售門市的資訊站。

人員ID會覆寫永久ID，因此系統會將共用裝置視為不同的人員（即便他們都是使用同一部裝置）。

如需詳細資訊，請參閱[共用裝置](/help/use-cases/stitching/shared-devices.md)使用案例。

+++

## 許多永久ID

+++ 拼接如何處理單一人員擁有多個永久ID的情況？

在某些情況下，個別使用者可以關聯至多個永久 ID。 例如，個人經常清除瀏覽器的Cookie或使用瀏覽器的私人/無痕模式。

對於欄位式拚接，永久ID的數量與人員ID無關。 單一使用者可屬於任意數量裝置，不會影響Customer Journey Analytics跨裝置彙整的能力。

對於圖表式拚接，身分圖表中的單一人員可以有許多永久ID。 圖表式拚接會根據指定的名稱空間使用永久ID。 如果相同名稱空間有較多的永久ID，則會使用字典第一個永久ID。

+++

## 拼接過程

+++ 如果我連絡 Adobe 帳戶團隊，向對方索取所需資訊，需要多久才能使用金鑰已重設的資料集？

Adobe啟用彙整功能後，需要約一週才能使用即時彙整。 能否使用回填功能取決於現有資料的數量。如果是小型資料集 (每天不到 100 萬個事件)，通常需要幾天後才能使用，大型資料集 (每天 10 億個事件) 則需等待一週或更久時間。

+++

## 跨裝置分析對比跨頻道分析

+++ 跨裝置分析（傳統Analytics中的一項功能）和跨管道分析有何不同？

[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)是傳統Adobe Analytics的專屬功能，可讓您瞭解人們如何跨裝置運作。 它提供兩個將裝置資料連結在一起的工作流程：欄位式拚接和裝置圖表。

跨頻道分析是Customer Journey Analytics專屬的使用案例，可讓您同時瞭解人們如何跨裝置和頻道運作。 它會拼接資料集的人員ID，讓該資料集可順暢地與其他資料集結合。 此功能在設計上的運作方式與跨裝置分析欄位式銜接類似，但由於傳統Analytics和Customer Journey Analytics之間的資料架構不同，實施方式也不同。 如需詳細資訊，請參閱[拼接](overview.md)和[跨管道分析](../use-cases/cross-channel/cross-channel.md)使用案例。

+++

## 隱私權

+++ 拼接如何處理隱私權請求？

Adobe會根據當地及國際法處理隱私權要求。 Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)，以供提交資料存取及刪除要求。 這些要求會同時套用至原始資料集和已重設金鑰的資料集。

>[!IMPORTANT]
>
>作為隱私權請求的一部分，取消拼接過程在2025年初變更。 目前的解除拼接程式使用最新版本的已知身分識別來重設事件。 將事件重新指派給另一個身分可能會產生不良的法律後果。 為了補救這些疑慮，自2025年起，新的解除拼接流程將使用永久性ID更新隱私權請求中的事件。
> 

舉例來說，您可以想像下列身分資料、銜接前和銜接後的事件。

| 身分識別對應 | Id | timestamp | 永久ID | 永久名稱空間 | 個人IO | 個人名稱空間 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | 鮑伯 | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件資料集 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | 鮑伯 | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接資料集 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 | 拼接的ID | 拼接的名稱空間 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | 鮑伯 | CustId |
| | 2 | ts1 | 123 | ecid | 鮑伯 | CustId | 鮑伯 | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隱私權要求的目前程式**

當收到具有CustID Bob的客戶的隱私權請求時，會刪除具有刪除線專案的列。 其他事件會使用身分對應來重新設定。 例如，彙整資料集中的第一個彙整ID已更新為&#x200B;**Alex**。

| 身分識別對應 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件資料集 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接資料集 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 | 拼接的ID | 拼接的名稱空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隱私權請求的新程式**

當收到具有CustID Bob的客戶的隱私權請求時，會刪除具有刪除線專案的列。 其他事件會使用永久ID重新設定。 例如，彙整資料集中的第一個彙整ID已更新為&#x200B;**123**。

| 身分識別對應 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件資料集 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接資料集 | Id | timestamp | 永久ID | 永久名稱空間 | 人員ID | 個人名稱空間 | 拼接的ID | 拼接的名稱空間 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## 空白的永久ID值

+++ 如果一個或多個事件中的永久ID欄位為空白，會發生什麼情況？

如果在正在拼接的資料集中的事件上，永久ID欄位為空白，該事件的拼接ID將以兩種方式之一來確定：

* 若暫時ID欄位並非空白，Customer Journey Analytics會將暫時ID中的值視為拼接ID。
* 若暫時ID欄位為空白，Customer Journey Analytics也會將彙整ID保留為空白。 在這種情況下，事件的永久ID、暫時ID和彙整ID全部空白。 使用正在拼接資料集（其中拼接的ID被選為人員ID）的Customer Journey Analytics連線中，會捨棄這些型別的事件。

+++


## 未定義的人員ID值

+++ 如果一或多個事件中的人員ID欄位有預留位置值（例如`Undefined`），會發生什麼情況？

請留意「人員摺疊」，拼接套用至使用暫時ID預留位置值的資料時，就會發生這種情況。 在下列範例表格中，來源於CRM系統的資料集所產生的「未定義」人員ID會填入「未定義」值，導致人員表示不正確。

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 暫時ID | 拼接的ID （重播後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **科里** |
| 2 | 2023-05-12 12:02 | 123 | 科里 | **科里** |
| 3 | 2023-05-12 12:03 | 456 | 未定義 | **未定義** |
| 4 | 2023-05-12 12:04 | 456 | - | **未定義** |
| 5 | 2023-05-12 12:05 | 789 | 未定義 | **未定義** |
| 6 | 2023-05-12 12:06 | 012 | 未定義 | **未定義** |
| 7 | 2023-05-12 12:07 | 012 | - | **未定義** |
| 8 | 2023-05-12 12:03 | 789 | 未定義 | **未定義** |
| 9 | 2023-05-12 12:09 | 456 | - | **未定義** |
| 10 | 2023-05-12 12:02 | 123 | - | **科里** |
| | | **4個裝置** | **2人**：<br/>已捨棄事件1、4、7、9、10 | **2位人員**：<br/>Cory，未驗證（摺疊給一位人員） |

+++

## 量度比較

+++ 與Customer Journey Analytics非拼接資料集中的類似量度和Customer Journey Analytics相比，Adobe Analytics中的量度如何？

Customer Journey Analytics中的某些量度與傳統Analytics中的量度類似，但其他量度則有所不同，端視您要比較的內容而定。 下表比較了幾個常見的量度：

| **Customer Journey Analytics 拼接資料** | **Customer Journey Analytics 未拼接資料** | **Adobe Analytics** | **具有 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人員** =將彙整ID選為人員ID的不同人員ID計數。 在傳統 Adobe Analytics 中，**人物**&#x200B;可能高於或低於&#x200B;**不重複訪客**，取決於拼接過程的結果。 | **人員** =根據選取為人員ID的欄的不同人員ID計數。 在Analytics來源聯結器資料集中，**人員**&#x200B;類似於傳統Adobe Analytics中的&#x200B;**不重複訪客** (如果`endUserIDs._experience.aaid.id`在Customer Journey Analytics中用作人員ID)。 | **不重複訪客** = 不同訪客 ID 的計數。 **不重複訪客**&#x200B;可能與相異 **ECID** 的計數不同。 | 請參閱[人員](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hant)。 |
| **工作階段**：根據 Customer Journey Analytics 資料檢視中的工作階段設定來定義。拼接過程可以將來自多個裝置的各個工作階段合併為一個工作階段。 | **工作階段**：根據 Customer Journey Analytics 資料檢視中指定的工作階段設定來定義。 | **造訪次數**：請參閱[造訪次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hant)。 | **造訪次數**：根據 [CDA 虛擬報告套裝](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hant)中指定的工作階段設定來定義。 |
| **事件**= Customer Journey Analytics 中拼接資料中的列數。這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是，請注意上面關於具有空白永久ID的列的常見問題集。 | **事件**= Customer Journey Analytics 中未拼接資料中的列數。這個量度通常接近傳統 Adobe Analytics 中的&#x200B;**發生次數**。但是請注意，如果任何事件在Experience Platform資料湖的未拼接資料中具有空白的人員ID，則這些事件不會包含在Customer Journey Analytics中。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 | **發生次數**：請參閱[發生次數](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hant)。 |

Customer Journey Analytics和Adobe Analytics中的其他量度可能類似。 例如，Adobe Analytics [自訂事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hant) 1-100的總計數，在傳統Adobe Analytics和Customer Journey Analytics之間可以比較（無論是拼接還是未拼接）。 [功能差異(例如Customer Journey Analytics與Adobe Analytics之間的事件刪除重複資料功能)可能會導致兩個產品之間有所出入。](/help/getting-started/aa-vs-cja/cja-aa.md)

+++

## 身分識別對應

+++ Customer Journey Analytics可以使用「身分對應」欄位嗎？

是，Customer Journey Analytics可針對[欄位型](/help/stitching/fbs.md#identitymap)和[圖表型](/help/stitching/gbs.md#identitymap)拼接使用身分對應欄位。

+++

## 切換到圖表式銜接

+++ 是否需要重新內嵌資料，才能從欄位式拚接切換為圖表式拚接？

資料不需要擷取至Experience Platform，但是需要在Customer Journey Analytics中重新設定。 請依照下列步驟操作：

1. 使用圖表式拚接來設定新的圖表式拚接資料集。
1. 以極小的資料時間範圍建立新的暫時連線。
1. 將新的圖表型資料集設定為此暫時連線的一部分。
1. 使用這個新的臨時連線驗證圖表式拚接是否正常運作。
1. 如果圖表式拚接如預期般運作，請為圖表式資料集要求任何其他回填，然後將原始連線中的欄位式資料集與新的圖表式資料集交換。
1. 移除暫時連線。

+++

## 報告中斷

+++ 現有報告是否會造成任何中斷？

如果您依照上述步驟進行，則不然。 否則，請向Adobe Consulting尋求其他支援。

+++

## 為Identity Service啟用資料集

+++ 如何只為Identity Service啟用資料集？ 

您必須確保為Identity Service啟用資料集，才能在圖表式拚接中使用資料集。

您不需要取得Real-Time Customer Data Platform的授權，就能使用圖表式拚接。 圖表式拚接是以可用的身分圖表為基礎，而不是以即時客戶設定檔為基礎。

若要只為識別服務啟用資料集，請使用只使用`POST`標籤的`/datasets`端點的`unifiedIdentity`要求。 例如：

```shell
curl -X POST \
  https://platform.adobe.io/data/foundation/catalog/dataSets \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
    "schemaRef": {
        "id": "https://ns.adobe.com/{TENANT_ID}/schemas/31670881463308a46f7d2cb09762715",
        "contentType": "application/vnd.adobe.xed-full-notext+json; version=1"
    },
    "tags": {
       "unifiedIdentity": ["enabled:true"]
    }
  }'
```

請求中對`unifiedProfile`標籤的任何使用（雖然您沒有即時客戶資料設定檔的授權），都會傳回錯誤。

如需詳細資訊，請參閱[建立為設定檔和身分啟用的資料集](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#create-a-dataset-enabled-for-profile-and-identity)。

+++ 
