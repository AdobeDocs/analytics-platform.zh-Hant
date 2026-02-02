---
title: 圖表式銜接
description: 說明圖表式銜接的概念及運作方式。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 79%

---

# 圖表型拼接

在圖表式拚接中，您可以指定事件資料集。 您可以為該事件資料集指定永久ID (Cookie)，並從包含人員ID值的身分圖表指定所需的拼接名稱空間。 圖表型拼接會將拼接後的 ID 的新一欄，新增至事件資料集。永久ID可使用指定的拼接名稱空間，從Experience Platform Identity Service查詢身分圖表，以更新拼接的ID。


![圖表型拼接](/help/stitching/assets/gbs.png)

## 身分識別圖

圖表型拼接支援在下列情境中使用[`identityMap`欄位群組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#identity)：

- 在 `identityMap` 命名空間中使用主要身分識別以定義永久 ID：
   - 如果在不同的名稱空間中找到多個主要身分，則名稱空間中的身分會依字典排序，並會選取第一個身分。
   - 如果在單一命名空間中找到多個主要身分識別，則會選取按照字典順序第一個可用的主要身分識別。

  在以下範例中，命名空間和身分識別會產生經過排序的主要身分識別清單，最後則產生所選的身分識別。

  <table style="table-layout:auto">
     <tr>
       <th>命名空間</th>
       <th>身分識別清單</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>已排序的身分識別清單</th>
      <th>選取的身分識別</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- 使用 `identityMap` 命名空間定義永久 ID：
   - 如果在 `identityMap` 命名空間中找到永久 ID 的多個值，則會使用字母排序下第一個可供使用的身分識別。

  在以下範例中，您已選取 ECID 做為要使用的命名空間。該選取範圍會產生經過排序的身分識別清單，並最後產生選取的身分識別。

  <table style="table-layout:auto">
     <tr>
       <th>命名空間</th>
       <th>身分識別清單</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>已排序的身分識別清單</th>
      <th>選取的身分識別</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## 圖表型拼接的運作方式

拼接會對指定資料集中的資料進行至少兩次傳遞。

- **即時拼接**：嘗試在每個點擊 (事件) 傳入時將其拼接，使用永久 ID 來查詢身分識別圖表，藉此找出所選命名空間的個人 ID。如果透過查詢取得個人 ID，系統會立即拼接此個人 ID。

- **重播拼接**：根據身分識別圖表更新的身分識別&#x200B;*重播*&#x200B;資料。來自先前未知裝置 (永久 ID) 的點擊會在這個階段進行拼接，因為身分識別圖表已解析命名空間的身分識別。兩個引數決定重播： **頻率**&#x200B;和&#x200B;**回顧期間**。 Adobe 提供下列這些參數的組合：
   - **以每日一次的頻率行每日回顧**：資料每天重播，回顧時間範圍是 24 小時。此選項的優點是重播頻率較高，但未驗證的輪廓必須在造訪您網站的當天完成驗證。
   - **以每週一次的頻率進行每週回顧**：資料每週重播一次，回顧時間範圍是一週 (請參閱[選項](#options))。此選項的優點在於，未驗證的工作階段擁有寬裕的時間完成驗證。不過，直到下一次每週重播為止，系統不會重新處理不到一週的未拼接資料。
   - **以每週一次的頻率進行每兩週回顧**：資料每週重播一次，回顧時間範圍是兩週 (請參閱[選項](#options))。此選項的優點在於，未驗證的工作階段擁有寬裕的時間完成驗證。不過，直到下一次每週重播為止，系統不會重新處理不到兩週的未拼接資料。
   - **以每週一次的頻率進行每月回顧**：資料每週重播一次，回顧時間範圍是一個月 (請參閱[選項](#options))。此選項的優點在於，未驗證的工作階段擁有寬裕的時間完成驗證。不過，直到下一次每週重播為止，系統不會重新處理不到一個月的未拼接資料。

- **隱私權**：在收到隱私相關請求時，除了從來源資料集移除所請求的身分識別之外，在未驗證事件中對該身分識別所做的任何拼接都必須還原。此外，身分識別必須從身分識別圖表移除，防止未來對該特定身分識別使用圖表型拚接。

  >[!IMPORTANT]
  >
  >做為隱私請求的一部分，取消拼接程序在 2025 年初有所變更。目前取消拼接的程序使用最新版本的已知身分識別將事件重新拼接。將事件重新指派給另一個身分識別，可能會產生不利的法律後果。為解除這些疑慮，自 2025 年起，新的取消拼接程序將使用永久 ID 更新受到隱私請求影響的事件。
  > 

超出回顧時間範圍的資料不會重播。設定檔必須在指定的回顧期間內通過驗證，才能同時識別未驗證的造訪和已驗證的造訪。 辨識出裝置後，就會從該點開始即時拼接。

請思考下列訪客 A (具有永久 ID`246`) 和訪客 B (具有永久 ID`3579`) 在一段時間內的兩次身分識別圖表更新，以及這些更新如何影響圖表型拼接中的步驟。

![身分識別圖表 3579](assets/identity-graphs.svg)

您可以使用[身分識別圖表檢視器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/identity-graph-viewer)，檢視特定輪廓在一段時間內的身分識別圖表。另請參閱[身分識別服務連結邏輯](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/identity-linking-logic)，更清楚了解連結身分識別時所使用的邏輯。

### 第 1 步：即時拼接

即時拼接會在收集時嘗試將各事件與當時來自身分識別圖表的已知資訊拼接。

+++ 詳細資料

| | 時間 | 永久 ID<br/>`ECID` | 命名空間<br/>`Email` ![資料對應](/help/assets/icons/DataMapping.svg) | 拼接後的 ID (即時拼接後) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) *未定義* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) *未定義* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

您可以深入了解如何針對各事件解析拼接後的 ID。根據時間、永久 ID 和查詢指定命名空間的身分識別圖表 (同時)。
當查詢解析為一個以上的拼接後的 ID 時 (如事件 7)，會選取身分識別圖表傳回 ID 中依字典順序排列的第一個 (在此範例中為 `a.b@yahoo.co.uk`)。

+++

### 第 2 步：重播拼接

重播拼接會定期地 (視選取的回顧時間範圍而定) 根據身分識別圖表的最新版本，在間隔時間重新計算歷史資料。

+++ 詳細資料

當重播拼接發生在 2023-05-13 16:30，且回顧時間範圍設定為 24 小時，範例中的某些事件會重新拼接 (標示為![重播](/help/assets/icons/Replay.svg))。

| | 時間 | 永久 ID<br/>`ECID` | 命名空間<br/>`Email` ![資料對應](/help/assets/icons/DataMapping.svg) | 拼接後的 ID<br/> (即時拼接後) | 拼接後的 ID <br/>(重播 24 小時後) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


當重播拼接發生在 2023-05-13 16:30，且回顧時間範圍設定為 7 天時，來自範例的所有事件都會重新拼接。


| | 時間 | 永久 ID<br/>`ECID` | 命名空間<br/>`Email` ![資料對應](/help/assets/icons/DataMapping.svg) | 拼接後的 ID <br/>(即時拼接後) | 拼接後的 ID <br/>(重播 7 天後) |
|---|---|---|---|---|---|
| ![重播](/help/assets/icons/Replay.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) *未定義* | `246` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 第 3 步：隱私請求

當您收到隱私請求時，作為隱私請求主體的使用者之所有記錄當中的拼接後的 ID 皆會刪除。

+++ 詳細資料

下列表格呈現與以上相同的資料，但顯示隱私請求 (例如，在 2023-05-13 18:00) 對範例事件的影響。

| | 時間 | 永久 ID<br/>`ECID` | 命名空間<br/>`Email` ![資料對應](/help/assets/icons/DataMapping.svg) | 拼接後的 ID (隱私請求後) |
|--:|---|---|---|---|
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圓圈](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 先決條件

下列先決條件專門適用於圖表型拼接：

- Adobe Experience Platform 中您要套用拼接的事件資料集，必須有一欄可在每列識別輪廓，亦即&#x200B;**永久 ID**。例如，Adobe Analytics AppMeasurement 資料庫產生的訪客 ID 或 Experience Platform 身分識別服務產生的 ECID。
- 在啟用圖表式拚接之前，必須先在沙箱層級設定Experience Platform Identity Service的身分圖表。
   - 身分圖表必須有名稱空間（例如`Email`或`Phone`），您想在拼接期間使用它來解析人員ID。
   - 身分圖表必須填入來自任何相關資料集（型別為&#x200B;*event*&#x200B;或&#x200B;*設定檔*，且至少包含兩個具有ID值的有用名稱空間）的身分資訊。
   - 擁有這類相關身分的所有資料集都必須針對身分圖表資料擷取[啟用](faq.md#enable-a-dataset-for-the-identity-service)。 這項啟用可確保隨著時間從所有需要的來源將傳入的身分新增到圖表中。
   - 若已使用即時客戶資料設定檔或Adobe Journey Optimizer一段時間，則應已在一定程度上設定圖表。<br/>若啟用圖表式拚接的資料集也需要歷史拚接回填，圖表應已包含整個期間的歷史身分識別，才能取得想要的拚接結果。
- 如果您想要使用圖表式拼接，而且您預期事件資料集會貢獻身分圖表，您應該[啟用身分服務的資料集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)。
- 永久ID和人員ID可搭配[identityMap](#identitymap)使用。 或者，永久性ID和人員ID可以是XDM結構描述中的欄位，在這種情況下，欄位必須是[在結構描述中定義為身分](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity?lang=en)。

>[!NOTE]
>
>您&#x200B;**不**&#x200B;需要 Real-time Customer Data Platform 授權也可以使用圖表型拼接。Customer Journey Analytics 的 **Prime** 封裝或以上版本包含必要的 Experience Platform 身分識別服務權益。


## 限制

下列限制專門適用於圖表型拼接：

- 使用指定的命名空間查詢個人 ID 時，不會考慮時間戳記。因此，永久 ID 可能會與記錄中時間戳記較早的個人 ID 結合。
- 在共用裝置的情境中，若圖表中的命名空間包含多個身分識別，系統會使用按照字典順序排列第一個的身分識別。如果命名空間限制和優先順序是在圖表連結規則發行時設定，則會使用最後驗證的使用者身分。如需更多資訊，請參閱[共用裝置](/help/use-cases/stitching/shared-devices.md)。
- 在身分識別圖表中回填身分識別，須遵守回溯三個月的硬性限制。若您未使用 Experience Platform 應用程式 (如 Real-time Customer Data Platform) 填入身分識別圖表，建議您使用回填身分識別。
- 適用[身分識別服務護欄](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/guardrails)。檢視下列[靜態限制](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/guardrails#static-limits)範例：
   - 圖表中的最大身分識別數量：50。
   - 單一批次攝取的身分識別連結數上限：50。
   - 用於圖表攝取之 XDM 記錄中的最大身分識別數量：20。
   - 用於圖表攝取之 XDM 記錄中的最低身分識別數量：2。
