---
title: 依欄位彙整
description: 說明欄位式銜接的概念及運作方式。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 2e2620bdc6875b13492013f4ec108bae0302a25a
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 81%

---

# 欄位型拼接

在以欄位為基礎的彙整中，您可以指定事件資料集，以及該資料集的永久ID (Cookie)和人員ID。 依欄位彙整會針對任何具有特定永久ID的匿名事件，嘗試將人員ID資訊用於Customer Journey Analytics資料分析。  系統會從具有該特定永久ID之人員ID的列擷取該資訊。

如果無法擷取事件的人員ID資訊，則會使用永續性ID來取代該&#x200B;*未拼接*&#x200B;事件。 因此，在與包含已啟用拼接資料集的[連線](/help/data-views/data-views.md)相關聯的[資料檢視](/help/connections/overview.md)中，人員ID元件包含人員ID值或事件層級的永久ID值。

使用Customer Journey Analytics做為獨立解決方案(無法存取Experience Platform Identity Service和相關聯的身分圖表)時，您可以使用依欄位彙整。 或者，當您不想使用可用的身分識別圖表時。

![欄位型拼接](/help/stitching/assets/fbs.svg)


## 身分識別圖

欄位型拼接支援在下列情境中使用 [`identityMap` 欄位群組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#identity)：

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


- 使用 `identityMap` 命名空間定義永久 ID 或個人 ID，或同時定義兩者：
   - 如果在 `identityMap` 命名空間中找到多個永久 ID 或個人 ID 的值，則會使用按照字典順序第一個可用的值。
   - 永久 ID 和個人 ID 的命名空間必須是互斥的。

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

## 欄位型拼接是如何運作

拼接會對指定資料集中的資料進行至少兩次傳遞。

- **即時拼接**：嘗試在每個點擊 (事件) 傳入時進行拼接。來自資料集中&#x200B;*新出現*&#x200B;裝置 (不曾經過驗證) 的點擊通常不會在此層級拼接。來自已識別裝置的點擊則會立即拼接。

- **重播拼接**：*根據唯一識別碼 (個人 ID) 重播*&#x200B;資料。來自先前未知裝置 (永久 ID) 的點擊會在這個階段進行拼接 (變成個人 ID)。兩個引數決定重播： **頻率**&#x200B;和&#x200B;**回顧期間**。 Adobe 提供下列這些參數的組合：
   - **以每日一次的頻率行每日回顧**：資料每天重播，回顧時間範圍是 24 小時。此選項的優點是重播頻率較高，但未驗證的輪廓必須在造訪您網站的當天完成驗證。
   - **以每週一次的頻率進行每週回顧**：資料每週重播一次，回顧時間範圍是一週 (請參閱[選項](overview.md#options))。此選項的優點在於，未驗證的工作階段擁有寬裕的時間完成驗證。不過，直到下一次每週重播為止，系統不會重新處理不到一週的未拼接資料。
   - **以每週一次的頻率進行每兩週回顧**：資料每週重播一次，回顧時間範圍是兩週 (請參閱[選項](overview.md#))。此選項的優點在於，未驗證的工作階段擁有寬裕的時間完成驗證。不過，直到下一次每週重播為止，系統不會重新處理不到兩週的未拼接資料。
   - **以每週一次的頻率進行每月回顧**：資料每週重播一次，回顧時間範圍是一個月 (請參閱[選項](overview.md#options))。此選項的優點在於，未驗證的工作階段擁有寬裕的時間完成驗證。不過，直到下一次每週重播為止，系統不會重新處理不到一個月的未拼接資料。

- **隱私權**：在收到隱私權相關要求時，除了移除要求的身分識別之外，在未驗證事件中對該身分識別所做的任何拼接都必須還原。

  >[!IMPORTANT]
  >
  >做為隱私請求的一部分，取消拼接程序在 2025 年初有所變更。目前取消拼接的程序使用最新版本的已知身分識別將事件重新拼接。將事件重新指派給另一個身分識別，可能會產生不利的法律後果。為解除這些疑慮，自 2025 年起，新的取消拼接程序將使用永久 ID 更新受到隱私請求影響的事件。
  > 


超出回顧時間範圍的資料不會重播。設定檔必須在指定的回顧期間內通過驗證，才能同時識別未驗證的造訪和已驗證的造訪。 只要成功辨識裝置，該裝置便從那時候開始進行即時拼接。

### 第 1 步：即時拼接

即時拼接會在收集時將各事件拼接到已知裝置和管道。

+++ 詳細資料

請思考以下範例，範例中 Bob 將不同的事件記錄為事件資料集的一部分。

*資料以收集當天的原始樣貌呈現：*

| 事件 | 時間戳記 | 永久 ID (Cookie ID) | 個人 ID | 產生的ID （即時彙整後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 個裝置** | | **4 名人員**：<br/>`246`、`Bob`、`3579`、`81911` |

新裝置上未驗證和已驗證的事件會 (暫時) 計為不同的人員。已識別裝置上的未驗證事件會進行即時拼接。

當所識別的自訂變數與裝置相互繫結時，歸因功能便會發揮作用。在上述範例中，除了事件 1、8、9 和 10 之外的所有事件皆是即時拼接 (這些事件皆使用 `Bob` 識別碼)。即時彙整「解析」事件4、6和12的結果ID。

延遲的資料 (時間戳記超過 24 小時的資料) 會以「盡力而為」的方式處理，同時以最高品質優先拼接目前資料。

+++ 

### 第 2 步：重播拼接

重播拼接會定期 (一週一次或一天一次，視所選回顧時間範圍而定) 根據現在辨識的裝置重新計算歷史資料。如果裝置最初是在未驗證的狀態下傳送資料並登入，重播拼接會將這些未驗證的事件與正確的個人繫結。

+++ 詳細資料

下表呈現上文所述的相同資料，但根據重播資料顯示不同的數字。

*重播後的相同資料：*

| 事件 | 時間戳記 | 永久 ID (Cookie ID) | 個人 ID | 產生的ID （即時彙整後） | 產生的ID （重播後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![向上箭頭](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) | `Bob` ![向上箭頭](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 個裝置** | | **4 名人員**：<br/>`246`、`Bob`、`3579`、`81911` | **2 名人員**：<br/>`Bob`、`3579` |

{style="table-layout:auto"}

當所識別的自訂變數與裝置相互繫結時，歸因功能便會發揮作用。在上述範例中，事件 1 和 10 會因重播而拼接，只剩下事件 8 和 9 未拼接。並將人員量度 (累計) 減少為 2。

+++ 

### 第 3 步：隱私請求

當您收到隱私權請求時，拼接程式設定給人員ID值的任何識別碼資訊都會在所有記錄中更新為隱私權請求之使用者主體的永久ID值。

+++ 詳細資料

下表呈現與上述相同的資料，但呈現在處理 Bob 的隱私請求之後對資料的影響。Bob 已通過驗證的列 (2、3、5、7 和 11) 會被刪除，並同時移除其他列中 Bob 的個人 ID。

*在針對 Bob 提出隱私請求後的相同資料：*

| 事件 | 時間戳記 | 永久 ID (Cookie ID) | 個人 ID | 產生的ID （即時彙整後） | 產生的ID （重播後） | 個人 ID | 產生的ID （在隱私權請求後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![向上箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![移除圓圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) | `Bob` | ![移除圓圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) | `Bob` | ![移除圓圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![移除圓圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭頭](/help/assets/icons/ArrowRight.svg) | `Bob` ![向下箭頭](/help/assets/icons/ArrowDown.svg) | `Bob` ![向上箭頭](/help/assets/icons/ArrowUp.svg) | ![移除圓圈](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 個裝置** | | **4 名人員**：<br/>246、`Bob`、`3579`、`81911` | **2 名人員**：<br/>Bob、`3579` |  | **3 名人員**：<br/>`246`、`3579`、`81911` |

+++ 

## 先決條件

下列先決條件專門適用於欄位型拼接：

- Adobe Experience Platform 中的事件資料集，即您想要套用拼接的事件資料集，必須有兩個協助識別輪廓的欄：

   - **永久 ID**，每一列的可用識別碼。例如，Adobe Analytics AppMeasurement 資料庫產生的訪客 ID 或 Adobe Experience Platform 身分識別服務產生的 ECID。
   - **個人 ID**，僅有部分列可用的識別碼。例如輪廓驗證後雜湊的使用者名稱或電子郵件地址。您可以使用任何您喜歡的識別碼。拼接會認定這個欄位儲存實際個人 ID 資訊。為獲得最佳的拼接結果，對於每個永久 ID，在資料集的事件中應至少傳送一次個人 ID。如果您打算將此資料集納入 Customer Journey Analytics 連線，其他資料集最好也具有類似的通用識別碼。

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 限制

下列限制專門適用於欄位型拼接：

- 目前，重新編號功能僅限於一個步驟 (永久 ID 改成個人 ID)。不支援多步驟重新編號 (例如從永久 ID 改成個人 ID，之後又改成另一個個人 ID)。
- 如果多人共用一部裝置，且使用者之間的轉換總數超過50,000，Customer Journey Analytics會停止為該裝置拼接資料。
- 不支援您組織中使用的自訂 ID 地圖。
- 拼接會區分大小寫。對於透過 Analytics 來源連接器產生的資料集，Adobe 建議審閱適用於個人 ID 欄位的任何 VISTA 規則或處理規則。經過此審閱，確保這些規則均未引進相同 ID 的新格式。例如，您應確保沒有任何 VISTA 或處理規則僅在事件的一小部分，針對個人 ID 欄位引進小寫。
- 拼接不會合併或串連欄位。
- 個人 ID 欄位應包含單一 ID 類型 (來自單一命名空間的 ID)。例如，個人 ID 欄位不應包含登入 ID 和電子郵件 ID 的組合。
- 如果針對同一永久 ID 發生了具有相同時間戳記的多個事件，但個人 ID 欄位中的值不同，則拼接將根據字母順序選取 ID。因此，如果永久 ID A 有兩個時間戳記相同的事件，且其中一個事件指定 Bob、另一個事件指定 Ann，則拼接會選取 Ann。
- 當個人 ID 包含預留位置值 (例如 `Undefined`) 時，請務必謹慎處理。如需更多資訊，請參閱[常見問題集](faq.md)。
- 永久ID和人員ID不能使用相同的名稱空間，名稱空間必須互斥。
