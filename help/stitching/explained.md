---
title: 彙整的運作方式
description: 瞭解彙整的概念
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: 73496ea3c8341d9db7e879a4f5ae4f35893c605d
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 24%

---

# 彙整的運作方式

彙整功能會對指定資料集中的資料進行至少兩次傳遞：

* **即時彙整**：會嘗試在每個點選（事件）傳入時將其彙整。 來自資料集「新」裝置（從未驗證）的點選通常不會在此層級結合。 來自已識別裝置的點選會立即結合。

* **重播拼接**：根據已學到的唯一識別碼（暫時ID）「重播」資料。 在這個階段，來自先前未知裝置（永久ID）的點選會彙整（至暫時ID）。 Adobe 提供兩個重播間隔選項：
   * **每日**：資料每天重播，回顧期間為24小時。 此選項的優點是重播頻率較高，但未驗證的訪客必須在造訪您網站的當天完成驗證。
   * **每週**：資料每週重播一次，回顧期間為7天。 此選項的優點在於，未驗證的工作階段能有更多時間驗證。不過，不到一週的未拼接資料要等到下一次每週重播時才會重新處理。

* **隱私權（選擇性）**：收到隱私權相關請求時，除了移除請求的身分之外，還必須復原該身分在未經驗證事件之間的任何拼接。

超出回顧期間的資料不會重播。 訪客必須在指定的回顧期間內進行驗證，以便一起識別未經驗證的造訪和經過驗證的造訪。 識別裝置後，就會從該時間點開始即時彙整。

## 步驟1：即時彙整

即時彙整會嘗試在收集時將每個事件彙整至已知裝置和頻道。 請考慮以下範例，範例中Bob會將不同的事件記錄為事件資料集的一部分。

*資料在收集當天的顯示方式：*

| 事件 | 時間戳記 | 永久性ID (Cookie ID) | 暫時ID （登入ID） | 彙整ID （即時彙整後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3個裝置** | | **4人**：<br/>246， Bob， 3579， 81911 |

{style="table-layout:auto"}

<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Stitched ID after live stitch | Call enter Person ID | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visits your site on a desktop, unauthenticated | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `2` (246 and Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `2` (246 and Bob) |
| `4` | `3579` | - | - | `3579` | Bob accesses your site on a mobile device, unauthenticated | `3` (246, Bob, and 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `3` (246, Bob, and 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `3` (246, Bob, and 3579) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `3` (246, Bob, and 3579) |
-->

新裝置上未驗證和已驗證的事件會 (暫時) 計為個別訪客。已識別裝置上的未驗證事件會即時彙整。

識別的自訂變數繫結至裝置時，歸因功能就會運作。 在上述範例中，除了事件1、8、9和10之外的所有事件都會即時彙整(它們都使用 `Bob` 識別碼)。 即時彙整「解析」活動4、6和12的彙整ID。

## 第 2 步：重播彙整作業

重播彙整會定期（每週一次或每天一次，取決於選擇的回顧期間）根據現在識別的裝置重新計算歷史資料。 如果裝置最初是在未驗證時傳送資料，然後登入，則重播彙整會將那些未驗證的事件與正確的人員繫結。 下表呈現上文所述的相同資料，但根據重播資料顯示不同的數字。

*重播後的相同資料：*

| 事件 | 時間戳記 | 永久性ID (Cookie ID) | 暫時ID （登入ID） | 彙整ID （即時彙整後） | 彙整ID （重播後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **3個裝置** | | **4人**：<br/>246， Bob， 3579， 81911 | **2人**：<br/>Bob， 3579 |

{style="table-layout:auto"}

識別的自訂變數繫結至裝置時，歸因功能就會運作。 在上述範例中，事件1和10會因重播而拼接，留下只有事件8和9未拼接。 並將人員量度（累計）減少為2。

## 步驟3：隱私權請求

當您收到隱私權請求時，包含原始使用者資訊的列會遭到移除，包含此相同人員資訊的任何彙整ID也會一併移除。 下表呈現與上述相同的資料，但顯示Bob的隱私權請求在處理資料後對資料的影響。 會移除Bob已驗證的列（2、3、5、7和11），同時移除Bob作為其他列的暫時ID。

*Bob的隱私權請求後的相同資料：*

| 事件 | 時間戳記 | 永久性ID (Cookie ID) | 暫時ID （登入ID） | 彙整ID （即時彙整後） | 彙整ID （重播後） | 暫時ID （登入ID） | 彙整ID （隱私權請求後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3個裝置** | | **4人**：<br/>246， Bob， 3579， 81911 | **2人**：<br/>Bob， 3579 |  | **3人**：<br/>246， 3579， 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## 摘要

* 拼接會立即拼接來自已知裝置的事件，但不會立即拼接來自新裝置或無法識別的裝置的事件。
* 系統會定期重播資料，並根據已學會如何識別的裝置，適時變更連線中的歷史資料。
* 即時拚接和重播拚接會針對一個資料集執行。 結果是新的提升許可權資料集，最適合與其他資料集（例如客服中心資料）結合使用以執行跨管道分析。
* 隱私權請求會移除散佈至未經驗證之列的身分。
