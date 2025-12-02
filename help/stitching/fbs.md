---
title: 欄位式拼接
description: 欄位式銜接的概念與運作方式說明
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1776'
ht-degree: 9%

---

# 欄位式拼接

在以欄位為基礎的彙整中，您可以指定事件資料集，以及該資料集的永久ID (Cookie)和人員ID。 以欄位為基礎的彙整會將新的彙整ID欄新增至事件資料集，並根據具有該特定永久ID之人員ID的列更新此彙整ID。 <br/>當您使用Customer Journey Analytics做為獨立解決方案(無法存取Experience Platform Identity Service和相關聯的身分圖表)時，可以使用依欄位彙整。 或者，當您不想使用可用的身分圖表時。

![欄位式拼接](/help/stitching/assets/fbs.png)


## 身分對應

欄位式拚接支援在下列情況下使用[`identityMap`欄位群組](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)：

- 在`identityMap`名稱空間中使用主要身分來定義persistentID：
   - 如果在不同的名稱空間中找到多個主要身分，則名稱空間中的身分會依字典排序，並會選取第一個身分。
   - 如果在單一名稱空間中找到多個主要身分，則會選取第一個字典上可用的主要身分。

  在以下範例中，名稱空間和身分會產生排序的主要身分清單，最後是選取的身分。

  <table style="table-layout:auto">
     <tr>
       <th>命名空間</th>
       <th>身分清單</th>
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
      <th>已排序的身分清單</th>
      <th>選取的身分</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- 使用`identityMap`名稱空間來定義永久ID或人員ID，或同時定義兩者：
   - 如果在`identityMap`名稱空間中找到多個永久ID或人員ID的值，則會使用第一個字典可用的值。
   - 永久ID和人員ID的名稱空間必須互斥。

  在以下範例中，您已選取ECID作為要使用的名稱空間。 該選取範圍會產生排序的身分清單，最後產生選取的身分。

  <table style="table-layout:auto">
     <tr>
       <th>命名空間</th>
       <th>身分清單</th>
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
      <th>已排序的身分清單</th>
      <th>選取的身分</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## 依欄位彙整的運作方式

拼接對指定資料集中的資料進行至少兩次傳遞。

- **即時彙整**：嘗試在每個點選（事件）傳入時將其彙整。 來自資料集&#x200B;*新*&#x200B;裝置（從未驗證）的點選通常不會在此層級結合。 來自已識別裝置的點選會立即結合。

- **重播拼接**： *根據唯一識別碼（人員ID）重播*&#x200B;資料。 在這個階段，來自先前未知裝置（永久ID）的點選會彙整（至人員ID）。 重播由兩個引數決定： **頻率**&#x200B;和&#x200B;**回顧期間**。 Adobe提供下列這些引數的組合：
   - **每日回顧頻率**：資料每天重播，回顧期間為24小時。 此選項的優點是重播頻率較高，但未驗證的設定檔必須在造訪您網站的當天進行驗證。
   - **每週回顧頻率**：資料每週重播一次，回顧期間為每週（請參閱[選項](#options)）。 此選項的優點在於，未驗證的工作階段能有更多時間驗證。不過，系統不會重新處理不到一週的未拼接資料，直到下一次每週重播為止。
   - **每兩週回顧一次每週頻率**：資料每週重播一次，回顧期間為每兩週（請參閱[選項](#options)）。 此選項的優點在於，未驗證的工作階段能有更多時間驗證。不過，兩週內的未拼接資料要等到下一次每週重播時才會重新處理。
   - **每週頻率每月回顧**：資料每週重播一次，回顧期間為每月一次（請參閱[選項](#options)）。 此選項的優點在於，未驗證的工作階段能有更多時間驗證。不過，不到一個月的未拼接資料要等到下一次每週重播才會重新處理。

- **Privacy**：在收到隱私權相關要求時，除了移除要求的身分之外，還必須復原在未驗證事件中對該身分的任何拼接。

  >[!IMPORTANT]
  >
  >作為隱私權請求的一部分，取消拼接過程在2025年初變更。 目前的解除拼接程式使用最新版本的已知身分識別來重設事件。 將事件重新指派給另一個身分可能會產生不良的法律後果。 為了補救這些疑慮，自2025年起，新的解除拼接流程將使用永久性ID更新隱私權請求中的事件。
  > 


超出回顧期間的資料不會重播。 設定檔必須在指定的回顧期間內進行驗證，以便一起識別未經驗證的造訪和經過驗證的造訪。 一旦識別出裝置，就會從該點開始即時彙整該裝置。

### 步驟1：即時彙整

即時彙整會嘗試在收集時將每個事件彙整至已知裝置和頻道。

+++ 詳細內容

請思考以下範例，範例中Bob將不同的事件記錄為事件資料集的一部分。

*資料在收集當天的顯示方式：*

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 人員 ID | 彙整ID （即時彙整後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3個裝置** | | **4人**：<br/>`246`，`Bob`，`3579`，`81911` |

新裝置上未驗證和已驗證的事件會 (暫時) 計為個別訪客。即時彙整已識別裝置上未驗證的事件。

識別出自訂變數繫結至裝置時，歸因功能即會運作。 在上述範例中，除了事件1、8、9和10之外的所有事件都已即時彙整（這些事件都使用`Bob`識別碼）。 即時彙整「解析」活動4、6和12的彙整ID。

延遲的資料（時間戳記超過24小時的資料）會以「盡力而為」的方式處理，同時以最高品質優先拼接目前資料。

+++ 

### 第 2 步：重播彙整作業

重播結合會定期（每週一次或每天一次，視選取的回顧期間而定）根據現在識別的裝置重新計算歷史資料。 如果裝置最初在未驗證時傳送資料然後登入，重播彙整會將那些未驗證的事件與正確的人員繫結。

+++ 詳細內容

下表呈現上文所述的相同資料，但根據重播資料顯示不同的數字。

*重播後的相同資料：*

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 人員 ID | 彙整ID （即時彙整後） | 拼接的ID （重播後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3個裝置** | | **4人**：<br/>`246`，`Bob`，`3579`，`81911` | **2人**：<br/>`Bob`，`3579` |

{style="table-layout:auto"}

識別出自訂變數繫結至裝置時，歸因功能即會運作。 在上述範例中，事件1和10會因重播而拼接，留下僅事件8和9未拼接。 並將人員量度（累計）減少為2。

+++ 

### 步驟3：隱私權請求

當您收到隱私權請求時，隱私權請求之使用者主體的所有記錄中都會刪除拼接的ID。

+++ 詳細內容

下表呈現與上述相同的資料，但顯示Bob的隱私權請求在處理資料後對資料的影響。 會移除Bob已驗證的列（2、3、5、7和11），同時移除Bob作為其他列的人員ID。

*為Bob提出隱私權請求後的相同資料：*

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 人員 ID | 彙整ID （即時彙整後） | 拼接的ID （重播後） | 人員 ID | 彙整ID （隱私權請求後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | 鮑勃![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | 鮑勃![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | 鮑勃![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上箭號](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3個裝置** | | **4人員**：<br/>246，`Bob`，`3579`，`81911` | **2人**：<br/>Bob，`3579` |  | **3人**：<br/>`246`，`3579`，`81911` |

+++ 

## 先決條件

下列先決條件特別適用於依欄位彙整：

- Adobe Experience Platform中的事件資料集（您想要套用拼接）必須有兩個協助識別設定檔的欄：

   - **永久ID**，每一列都有一個識別碼。 例如，Adobe Analytics AppMeasurement資料庫產生的訪客ID或Adobe Experience Platform Identity Service產生的ECID。
   - **人員ID**，此識別碼僅可用於部分列。 例如，設定檔驗證後的雜湊使用者名稱或電子郵件地址。 您幾乎可以使用任何您喜歡的識別碼。 拼接會將此欄位視為儲存實際人員ID資訊。 為獲得最佳的拼接結果，應在資料集的事件中為每個永久ID至少傳送一次人員ID。 如果您打算將此資料集納入Customer Journey Analytics連線，最好讓其他資料集也具有類似的通用識別碼。

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 限制

下列限制特別適用於欄位式拼接：

- 目前金鑰重設功能僅限於一個步驟（永久ID對人員ID）。 不支援多步驟重新輸入金鑰（例如將永久ID轉換為人員ID，然後再轉換為另一個人員ID）。
- 如果一部裝置由多人共用，且使用者之間的切換總數超過50,000，Customer Journey Analytics會停止為該裝置拼接資料。
- 不支援您組織中使用的自訂 ID 地圖。
- 拼接區分大小寫。 對於透過Analytics來源聯結器產生的資料集，Adobe建議檢閱適用於人員ID欄位的任何VISTA規則或處理規則。 此檢閱可確保這些規則都不會引入相同ID的新形式。 例如，您應確保沒有任何VISTA或處理規則僅在一部分事件中，將小寫字母引入人員ID欄位。
- 拼接不會合併或串連欄位。
- 人員ID欄位應包含單一ID型別（來自單一名稱空間的ID）。 例如，人員ID欄位不應包含登入ID和電子郵件ID的組合。
- 如果針對同一永久ID發生了具有相同時間戳記的多個事件，但人員ID欄位中的值不同，則拼接作業會根據字母順序來選取ID。 因此，如果永久ID A有兩個具有相同時間戳記的事件，且其中一個事件指定Bob，而另一個事件指定Ann，則拼接作業會選取Ann。
- 當人員ID包含預留位置值（例如`Undefined`）時，請務必小心。 如需詳細資訊，請參閱[常見問題集](faq.md)。
- 永久ID和人員ID不能使用相同的名稱空間，名稱空間必須互斥。
