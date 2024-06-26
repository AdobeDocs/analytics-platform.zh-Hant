---
title: 拼接概述
description: 銜接概觀。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 83e568d686a541bb6472a33dc0a7400cf6e8de2a
workflow-type: tm+mt
source-wordcount: '3712'
ht-degree: 12%

---

# 拼接

{{select-package}}

身分拼接（或簡單地說，拼接）是一項強大的功能，可提升事件資料集對於跨管道分析的適用性。 跨管道分析是Customer Journey Analytics可以處理的主要使用案例，可讓您根據通用識別碼（人員ID），針對不同管道的多個資料集無縫合併和執行報表。

合併人員 ID 相似的資料集時，系統會跨裝置和管道套用原本的歸因。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站，但後來遇到訂單問題，於是他打電話給您的客戶服務團隊，期能解決問題。透過跨管道分析，您可以將客服中心事件歸因於使用者原本點選的廣告。

不幸的是，並非所有屬於您在Customer Journey Analytics中的連線之事件型資料集都已填入足夠的資料，以立即支援此歸因。 尤其以網頁或行動為基礎的體驗資料集，通常沒有可用於所有事件的實際人員ID資訊。

拼接功能允許在一個資料集的列內重新輸入身分，確保每個事件都可使用人員ID （拼接的ID）。 拼接會檢視已驗證和未驗證工作階段的使用者資料，以決定可用作拼接ID的共同暫時ID （人員ID）值。 此金鑰重設允許將不同的記錄解析為單一彙整ID，以便在人員層級而不是裝置或Cookie層級進行分析。

Customer Journey Analytics支援兩種彙整型別：欄位式彙整和圖表式彙整。

## 先決條件

>[!IMPORTANT]
>
>若未符合所有必要條件，可能會導致無法正確進行跨管道分析。

使用拚接前，請確認您的組織已做好下列準備：

- 拼接包括合併已驗證和未驗證的使用者資料。 在事件資料集上啟用連結之前，請確定您遵守適用的法律和法規，包括取得必要的一般使用者許可權。 有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。

- 將所需的資料匯入Adobe Experience Platform：

   - 如需Adobe Analytics資料，請參閱 [在Customer Journey Analytics中利用Adobe Analytics報表套裝資料](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - 如為其他類型資料，請參閱 Adobe Experience Platform 文件中的[建立綱要](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)和[匯入資料](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)。

如果在定義Customer Journey Analytics連線時，將一或多個拼接資料集與其他資料集（例如客服中心資料）結合，即可受益於跨管道分析。 此連線設定假設其他資料集每一列都包含人員ID，類似於拼接ID。


## 限制

>[!IMPORTANT]
>
>- 不支援使用 `identityMap` 作為永久ID。 您必須在資料集中定義特定識別碼(例如， `ECID`)作為永久ID。
>
>- 將您對來源事件資料集結構描述所做的任何變更也套用至新拼接資料集結構描述，否則這會中斷拼接的資料集。
>
>- 如果您移除來源資料集，拼接的資料集將停止處理並被系統移除。
>
>- 資料使用標籤不會自動傳播到拼接的資料集結構描述。 如果您已將資料使用標籤套用至來源資料集結構描述，則需要手動將這些資料使用標籤套用至拼接的資料集結構描述。 另請參閱 [管理Experience Platform中的資料使用標籤](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) 以取得詳細資訊。

拚接是一項具突破性的完善功能，但其使用方式有所限制。

- 僅支援事件資料集。其他資料集概不支援，例如查詢資料集。
- 拼接不會以任何方式轉換用於拼接的欄位。 拼接使用指定欄位中的值，因為該值存在於資料湖中未拼接的資料集中。
- 拚接程序區分大小寫。例如，如果有時在欄位中出現「Bob」一詞，有時又出現「BOB」一詞，則這些id會被視為兩個不同的人。

請勿將拼接與下列混淆：

- 兩個或多個資料集的合併。 拼接僅適用於一個資料集。 設定Customer Journey Analytics連線並在連線中選取的資料集中選取相同的人員ID，會造成資料集合併。

- 兩個資料集的聯結。 在Customer Journey Analytics中，聯結通常用於Analysis Workspace中的查閱或分類。 雖然銜接使用連線功能，但程式本身涉及的不只是連線。


## 欄位式拚接

您可以指定事件資料集，以及該資料集的永久ID (Cookie)和暫時ID （人員ID）。 以欄位為基礎的彙整會在新彙整的資料集中建立新的彙整ID欄，並根據具有該特定永久ID的暫時ID的列更新此彙整ID欄。 <br/>將Customer Journey Analytics用作獨立解決方案(無法存取Experience Platform身分服務和關聯的身分圖表)時，您可以使用依欄位彙整。 或者，當您不想使用可用的身分圖表時。

![依欄位彙整](/help/stitching/assets/fbs.png)

### 依欄位彙整的運作方式

拼接對指定資料集中的資料進行至少兩次傳遞。

- **即時彙整**：會嘗試在每個點選（事件）傳入時將其彙整。 來自對資料集「新的」（從未驗證）之裝置的點選通常不會在此層級結合。 來自已識別裝置的點選會立即結合。

- **重播拼接**：根據已學到的唯一識別碼（暫時ID）「重播」資料。 在這個階段，來自先前未知裝置（永久ID）的點選會彙整（至暫時ID）。 Adobe 提供兩個重播間隔選項：
   - **每日**：資料每天重播，回顧期間為24小時。 此選項的優點是重播頻率較高，但未驗證的訪客必須在造訪您網站的當天完成驗證。
   - **每週**：資料會以您選取的回顧期間每週重播一次(請參閱 [選項](#options))。 此選項的優點在於，未驗證的工作階段能有更多時間驗證。不過，系統不會重新處理不到一週的未拼接資料，直到下一次每週重播為止。

- **隱私權**：在收到隱私權相關請求時，除了移除請求的身分之外，還必須復原該身分在未經驗證事件之間的任何拼接。

超出回顧期間的資料不會重播。 訪客必須在指定的回顧期間內進行驗證，以便一起識別未經驗證的造訪和經過驗證的造訪。 一旦識別出裝置，就會從該時間點開始即時彙整。

#### 步驟1：即時彙整

即時彙整會嘗試在收集時將每個事件彙整至已知裝置和頻道。

+++ 詳細資料

請思考以下範例，範例中Bob將不同的事件記錄為事件資料集的一部分。

*資料在收集當天的顯示方式：*

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 暫時ID （登入ID） | 彙整ID （即時彙整後） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3個裝置** | | **4人**：<br/>`246`， `Bob`， `3579`， `81911` |

新裝置上未驗證和已驗證的事件會 (暫時) 計為個別訪客。即時彙整已識別裝置上未驗證的事件。

識別出自訂變數繫結至裝置時，歸因功能即會運作。 在上述範例中，除了事件1、8、9和10之外的所有事件都已即時彙整(這些事件都使用 `Bob` 識別碼)。 即時彙整「解析」活動4、6和12的彙整ID。

延遲的資料（時間戳記超過24小時的資料）會以「盡力而為」的方式處理，同時以最高品質優先拼接目前資料。

+++

#### 第 2 步：重播彙整作業

重播結合會定期（每週一次或每天一次，視選取的回顧期間而定）根據現在識別的裝置重新計算歷史資料。 如果裝置最初在未驗證時傳送資料然後登入，重播彙整會將那些未驗證的事件與正確的人員繫結。

+++ 詳細資料

下表呈現上文所述的相同資料，但根據重播資料顯示不同的數字。

*重播後的相同資料：*

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 暫時ID （登入ID） | 彙整ID （即時彙整後） | 拼接的ID （重播後） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3個裝置** | | **4人**：<br/>`246`， `Bob`， `3579`， `81911` | **2人**：<br/>`Bob`， `3579` |

{style="table-layout:auto"}

識別出自訂變數繫結至裝置時，歸因功能即會運作。 在上述範例中，事件1和10會因重播而拼接，留下僅事件8和9未拼接。 並將人員量度（累計）減少為2。

+++

#### 步驟3：隱私權請求

當您收到隱私權請求時，隱私權請求之使用者主體的所有記錄中都會刪除拼接的ID。

+++ 詳細資料

下表呈現與上述相同的資料，但顯示Bob的隱私權請求在處理資料後對資料的影響。 會移除Bob已驗證的列（2、3、5、7和11），同時移除Bob作為其他列的暫時ID。

*Bob的隱私權請求後的相同資料：*

| 事件 | 時間戳記 | 永久ID (Cookie ID) | 暫時ID （登入ID） | 彙整ID （即時彙整後） | 拼接的ID （重播後） | 暫時ID （登入ID） | 彙整ID （隱私權請求後） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭頭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上鍵](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3個裝置** | | **4人**：<br/>246， `Bob`， `3579`， `81911` | **2人**：<br/>鮑勃， `3579` |  | **3人**：<br/>`246`， `3579`， `81911` |

+++

### 先決條件

下列先決條件特別適用於依欄位彙整：

- Adobe Experience Platform中的事件資料集（您想要套用拼接）必須有兩個協助識別訪客的欄：

   - A **永久ID**，每列都可使用的識別碼。 例如，Adobe AnalyticsAppMeasurement庫產生的訪客ID或Adobe Experience Cloud Identity Service產生的ECID。
   - A **暫時ID**，此識別碼僅可用於部分列。 例如訪客驗證後雜湊的使用者名稱或電子郵件地址。您幾乎可以使用任何您喜歡的識別碼。 拼接會將此欄位視為儲存實際人員ID資訊。 為獲得最佳拼接結果，每個永久ID應在資料集事件中至少傳送一次「暫時ID」 。 如果您打算將此資料集納入Customer Journey Analytics連線，最好讓其他資料集也具有類似的通用識別碼。

- 針對您要拼接的資料集，資料行（永久ID和暫時ID）都必須定義為在結構描述中具有身分名稱空間的身分欄位。 在Real-time Customer Data Platform中使用身分拼接時，使用 [`identityMap` 欄位群組](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)，您仍需新增具有身分名稱空間的身分欄位。 由於Customer Journey Analytics拼接不支援 `identityMap` 欄位群組。 在結構描述中新增身分欄位時，同時使用 `identityMap` 欄位群組，請勿將其他身分欄位設定為主要身分。 設定其他身分欄位作為主要身分會干擾 `identityMap` Real-time Customer Data Platform使用的欄位群組。

### 限制

下列限制特別適用於欄位式拼接：

- 目前，金鑰重設功能僅限於一個步驟 (永久 ID 改成暫時 ID)。不支援多步驟重設金鑰 (例如從永久 ID 改成暫時 ID，之後又改成另一個暫時 ID)。
- 如果裝置由多人共用，且使用者之間的轉換總數超過50,000，Customer Journey Analytics會停止為該裝置拼接資料。
- 不支援您組織中使用的自訂 ID 地圖。
- 拼接區分大小寫。 對於透過Analytics來源聯結器產生的資料集，Adobe建議審查適用於暫時ID欄位的任何VISTA規則或處理規則。 此檢閱可確保這些規則都不會引入相同ID的新形式。 例如，您應確保沒有任何 VISTA 或處理規則僅在一部分事件中，將小寫字母引入暫時 ID 欄位。
- 拼接不會合併或串連欄位。
- 暫時ID欄位應包含單一ID型別（來自單一名稱空間的ID）。 例如，暫時 ID 欄位不應包含登入 ID 和電子郵件 ID 的組合。
- 如果針對同一永久ID發生了具有相同時間戳記的多個事件，但暫時ID欄位中的值不同，則拼接作業會根據字母順序來選取ID。 因此，如果永久ID A有兩個具有相同時間戳記的事件，且其中一個事件指定Bob，而另一個事件指定Ann，則拼接作業會選取Ann。
- 請小心暫時ID包含預留位置值的情況，例如 `Undefined`. 請參閱 [常見問題集](faq.md) 以取得詳細資訊。


## 圖表式銜接

您可以指定事件資料集，以及該資料集的永久ID (Cookie)和暫時ID （人員ID）的名稱空間。 圖表式拚接會在新的拚接資料集中為拚接ID建立新欄。 然後使用永久ID來查詢來自Experience Platform身分服務的身分圖表，使用指定的名稱空間來更新拼接的ID。

![圖表式銜接](/help/stitching/assets/gbs.png)

### 圖表式拚接的運作方式

拼接對指定資料集中的資料進行至少兩次傳遞。

- **即時彙整**：嘗試在每個點選（事件）傳入時將其彙整，使用永久ID透過查詢身分圖表來查詢所選名稱空間的暫時ID。 如果暫時ID可從查詢取得，系統會立即結合此暫時ID。

- **重播拼接**：根據身分圖表中的更新身分「重播」資料。 這個階段會連結來自先前未知裝置（永久ID）的點選，因為身分圖表已解析名稱空間的身分。 Adobe 提供兩個重播間隔選項：
   - **每日**：資料每天重播，回顧期間為24小時。 此選項的優點是重播頻率較高，但未驗證的訪客必須在造訪您網站的當天完成驗證。
   - **每週**：資料每週會在回顧期間重播一次(請參閱 [選項](#options))。 此選項的優點在於，未驗證的工作階段能有更多時間驗證。不過，系統不會重新處理不到一週的未拼接資料，直到下一次每週重播為止。

- **隱私權**：收到隱私權相關請求時，除了從來源資料集中移除請求的身分之外，必須復原該身分在未經驗證事件之間的任何拼接。 此外，身分必須從身分圖表移除，以防止未來對該特定身分使用圖表式拚接。

超出回顧期間的資料不會重播。 訪客必須在指定的回顧期間內進行驗證，以便一起識別未經驗證的造訪和經過驗證的造訪。 一旦識別出裝置，就會從該時間點開始即時彙整。

請考量下列兩個持續性ID的身分圖表 `246` 和 `3579`、這些身分圖表如何隨著時間更新，以及這些更新如何影響圖表式拚接中的步驟。

![身分圖表246](assets/identity-graph-246.svg)
![身分圖表3579](assets/identity-graph-3579.svg)

您可以使用檢視特定設定檔在一段時間內的身分圖表 [身分圖表檢視器](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). 另請參閱 [Identity Service連結邏輯](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) 以更能瞭解連結身分識別時所使用的邏輯。

#### 步驟1：即時彙整

即時彙整會在收集時嘗試將每個事件與當時來自身分圖表的已知資訊彙整。

+++ 詳細資料

| | 時間 | 永久ID<br/>`ECID` | 名稱空間<br/>`Email` ![圖表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 彙整ID （即時彙整後） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定義* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定義* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

您可以檢視如何針對每個事件解析彙整ID。 根據時間、永久ID和查詢指定名稱空間的身分圖表（同時）。
當查詢解析為一個以上的彙整ID （例如事件7）時，會選取身分圖表傳回的字典首碼(`a.b@yahoo.co.uk` 在範例中)。

+++

#### 第 2 步：重播彙整作業

重播彙整會定期地（視選取的回顧期間而定）根據識別圖形的最新版本，在間隔時間重新計算歷史資料。

+++ 詳細資料

當重播結合發生於2023-05-13 16:30，具有24小時回顧視窗設定，則會重新結合範例的某些事件(以 ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg))。

| | 時間 | 永久ID<br/>`ECID` | 名稱空間<br/>`Email` ![圖表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼接的ID<br/>（即時彙整之後） | 拼接的ID<br/>（重播24小時後） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


當重播結合於2023-05-13 16:30進行，且回顧視窗設定為7天時，所有範例事件都會重新結合。


| | 時間 | 永久ID<br/>`ECID` | 名稱空間<br/>`Email` ![圖表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼接的ID<br/>（即時彙整之後） | 拼接的ID<br/>（重播7天後） |
|---|---|---|---|---|---|
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定義* | `246` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### 步驟3：隱私權請求

當您收到隱私權請求時，隱私權請求之使用者主體的所有記錄中都會刪除拼接的ID。

+++ 詳細資料

下表呈現與以上相同的資料，但顯示隱私權請求（例如，在2023-05-13 18:00）對範例事件具有的影響。

| | 時間 | 永久ID<br/>`ECID` | 名稱空間<br/>`Email` ![圖表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 彙整ID （隱私權請求後） |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![連結](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### 先決條件

下列先決條件尤其適用於圖表式銜接：

- Adobe Experience Platform中的事件資料集（您想要套用拼接）必須有一欄可識別每列的訪客，且 **永久ID**. 例如，Adobe AnalyticsAppMeasurement庫產生的訪客ID或Adobe Experience Cloud Identity Service產生的ECID。
- 來自Experience Cloud身分服務的身分圖表必須具有名稱空間(例如 `Email`，或 `Phone`)，您想在連結期間使用來解析 **暫時ID**. 另請參閱 [Experience PlatformIdentity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) 以取得詳細資訊。


### 限制

下列限制尤其適用於圖表式拚接：

- 使用指定的名稱空間查詢暫時ID時，不會考慮時間戳記。 因此，永久性ID可能會從時間戳記較早的記錄拼接暫時ID。
- 不支援共用裝置。 當傳回多個身分時，透過使用名稱空間查詢身分圖表，將使用第一個字典表型身分。
- 在身分圖表中有三個月回填身分的硬性限制。 若您未使用Experience Platform應用程式(例如Real-time Customer Data Platform)填入身分圖表，您可以使用回填身分。
- 此 [Identity Service護欄](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) 套用。 例如，請參閱下列內容 [靜態限制](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits)：
   - 圖表中的最大身分數量： 50。
   - 單一批次擷取的身分連結數上限： 50。
   - 用於圖表擷取的XDM記錄中的最大身分數量： 20。
   - 用於圖表擷取的XDM記錄中的最小身分數量： 2。


## 使用拼接

當您的組織滿足所有條件時 [必備條件](#prerequisites) 並瞭解常見問題 [限制](#limitations) 和拼接方法特定的([欄位型](#limitations-1) 和 [圖表式](#limitations-2))限制下，您可以依照下列步驟，開始在Customer Journey Analytics中使用拼接。

### 選項

選取拼接選項。 Customer Journey Analytics套件會決定初始回填持續時間、回顧期間、重播頻率以及拼接時允許的資料集數目上限的可用選項。

| | Customer Journey Analytics<br/>選取 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 一次性拼接回填持續時間 | 13 個月 | 13 個月 | 25 個月 |
| 回顧期間和重播頻率 | <li>1天，每天</li><li>最長7天，每週</li> | <li>1天，每天</li><li>最長14天，每週</li> | <li>1天，每天</li><li>最長30天，每週</li> |
| 拼接允許的資料集數量上限 | 5 | 10 | 15 |

### 要求支援

1. 請聯絡 Adobe 客戶支援，提供下列資訊：

   - 啟用銜接的要求。
   - 您要重新輸入金鑰之資料集的資料集ID。
   - 所需資料集的永久ID欄名稱（身分路徑和名稱空間） （每列顯示的識別碼）。
   - 對於欄位式拚接，所需資料集的暫時ID欄名稱（人員ID，也會作為連線內容中資料集之間的連結）。 對於圖表式拚接，為用於查詢身分圖表的身分名稱空間。
   - 您的回顧視窗和重播頻率偏好設定。 請參閱您的Customer Journey Analytics套件，以瞭解 [選項](#options) 可用。
   - 沙箱名稱。


2. Adobe客戶支援與Adobe工程部門合作，以便在收到您的請求時啟用拼接。 啟用後，Adobe Experience Platform中會出現一個包含新拼接ID欄的新的重設金鑰資料集。 Adobe客戶支援可提供新資料集的ID。

3. 首次開啟時，Adobe會提供拼接資料的回填。 請參閱您的Customer Journey Analytics套件，以瞭解 [選項](#options) 可用。

4. 如果您想在跨管道分析中使用新的拼接資料集，您需要將新的拼接資料集新增到 [連線](../connections/overview.md) 在Customer Journey Analytics中。 然後新增跨管道分析所需的任何其他資料集，並為每個資料集選取正確的人員ID。

5. 根據連線[建立資料檢視](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

設定資料檢視後，您可以跨管道和裝置執行Customer Journey Analytics報表分析。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

