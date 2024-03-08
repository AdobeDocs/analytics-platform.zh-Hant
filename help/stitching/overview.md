---
title: 拼接概述
description: 銜接概觀。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 18%

---

# 拼接概述

身分拼接（或簡單地說，拼接）是一項強大的功能，可提升事件資料集對於跨管道分析的適用性。 跨管道分析是Customer Journey Analytics可以處理的主要使用案例，可讓您根據通用識別碼（人員ID），順暢地合併和執行來自不同管道的多個資料集的報告。

合併人員 ID 相似的資料集時，系統會跨裝置和管道套用原本的歸因。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站，但後來遇到訂單問題，於是他打電話給您的客戶服務團隊，期能解決問題。透過跨管道分析，您可以將客服中心事件歸因於使用者原本點選的廣告。

不幸的是，並非所有屬於您在Customer Journey Analytics中的連線之事件型資料集都已填入足夠的資料，以立即支援此歸因。 尤其以網頁或行動為基礎的體驗資料集，通常沒有可用於所有事件的實際人員ID資訊。

拼接功能允許在一個資料集的列內重新輸入身分，確保每個事件都可使用人員ID （拼接的ID）。 拼接會檢視已驗證和未驗證工作階段的使用者資料，以決定可用作拼接ID的共同暫時ID值。 此金鑰重設允許將不同的記錄解析為單一彙整ID，以便在人員層級而不是裝置或Cookie層級進行分析。

如果在定義Customer Journey Analytics連線時，將一或多個拼接資料集與其他資料集（例如客服中心資料）結合，即可受益於跨管道分析。 這假設其他資料集在每一列都包含人員ID，類似於拼接ID。


## 先決條件

{{select-package}}

>[!IMPORTANT]
>
>若未符合所有必要條件，可能會導致無法正確進行跨管道分析。

使用拚接前，請確認您的組織已做好下列準備：

* 將所需的資料匯入Adobe Experience Platform：

   * 如需Adobe Analytics資料，請參閱 [在Customer Journey Analytics中利用Adobe Analytics報表套裝資料](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * 如為其他類型資料，請參閱 Adobe Experience Platform 文件中的[建立綱要](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)和[匯入資料](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hant)。

* Adobe Experience Platform中您要套用拚接的事件資料集必須具有兩個協助識別訪客的欄：

   * **永久 ID**，每列都會顯示這個識別碼，例如，Adobe AnalyticsAppMeasurement庫產生的訪客ID或Adobe Experience Cloud Identity Service產生的ECID。
   * **暫時 ID**，僅部分列會顯示這個識別碼，例如訪客驗證後雜湊的使用者名稱或電子郵件地址。您幾乎可以使用任何您喜歡的識別碼。 拼接會考量此欄位來儲存實際的人員ID資訊。 為獲得最佳拼接結果，每個永久ID應在資料集事件中至少傳送一次「暫時ID」 。 如果您打算將此資料集納入Customer Journey Analytics連線，最好讓其他資料集也具有類似的通用識別碼。

  這兩欄（永久ID和暫時ID）都必須在您要拼接的資料集基礎結構描述中，定義為具有身分名稱空間的身分欄位。 在Real-time Customer Data Platform中使用身分拼接時，使用 [identityMap欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#identity)，您仍需要新增具有身分名稱空間的身分欄位，因為本節討論的Customer Journey Analytics拼接不支援identityMap欄位群組。 在結構描述中新增身分欄位並同時使用identityMap欄位群組時，請勿將額外的身分欄位設定為主要身分，因為這會干擾用於Real-time Customer Data Platform的identityMap欄位群組。

* 拼接包括合併已驗證和未驗證的使用者資料。 在事件資料集上啟用連結之前，請確定您遵守適用的法律和法規，包括取得必要的一般使用者許可權。 另請參閱 [在UI中定義身分欄位](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#) 以取得詳細資訊。


## 使用拼接

當您的組織符合所有先決條件並瞭解 [限制](#limitations)，您可以依照下列步驟開始在Customer Journey Analytics中使用拼接：

### 要求支援

1. 請聯絡 Adobe 客戶支援，提供下列資訊：

   * 啟用銜接的要求。
   * 您要重新輸入金鑰之資料集的資料集ID。
   * 所需資料集的永久ID欄名稱（顯示於每列的識別碼）。
   * 所需資料集的暫時ID欄名稱（人員識別碼，也會做為連線內容中資料集之間的連結）。
   * 您的[重播](explained.md)頻率和回顧時間長度偏好設定，包括每週重播一次，回顧期間為 7 天，或每天重播一次，回顧期間為 1 天。
   * 沙箱名稱。


2. Adobe客戶支援與Adobe工程部門合作，以便在收到您的請求時啟用拼接。 啟用後，Adobe Experience Platform中會出現一個包含新彙整ID欄的新的重設金鑰資料集。 Adobe客戶支援可提供新資料集的ID。

3. 首次開啟時，Adobe會提供回填60天以前的彙整資料。

4. 如果您想在跨管道分析中使用新的拼接資料集，則需要將其新增到 [連線](../connections/overview.md) 與其他所需資料集一起進行Customer Journey Analytics。 為每個資料集選擇正確的人員 ID。

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


## 限制

>[!IMPORTANT]
>
>* 將您對全域事件資料集結構描述所做的任何變更也套用至新拼接資料集結構描述，否則這會中斷拼接的資料集。
>
>* 如果您移除來源資料集，拼接的資料集將停止處理並被系統移除。
>
>* 資料使用標籤不會自動傳播到拼接的資料集結構描述。 如果您已將資料使用標籤套用至來源資料集結構描述，則需要手動將這些資料使用標籤套用至拼接的資料集結構描述。 另請參閱 [管理Experience Platform中的資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=zh-Hant) 以取得詳細資訊。

拚接是一項具突破性的完善功能，但其使用方式有所限制。

* 目前，金鑰重設功能僅限於一個步驟 (永久 ID 改成暫時 ID)。不支援多步驟重設金鑰 (例如從永久 ID 改成暫時 ID，之後又改成另一個暫時 ID)。
* 僅支援事件資料集。其他資料集概不支援，例如查詢資料集。
* 不支援您組織中使用的自訂 ID 地圖。
* 拼接不會以任何方式轉換用於拼接的欄位。 拼接使用指定欄位中的值，因為該值存在於資料湖中未拼接的資料集中。 拚接程序區分大小寫。例如，如果有時在欄位中出現「Bob」一詞，有時又出現「BOB」一詞，則這些id會被視為兩個不同的人。
* 拼接區分大小寫。 對於透過Analytics來源聯結器產生的資料集，Adobe建議審查適用於暫時ID欄位的任何VISTA規則或處理規則。 此檢閱可確保這些規則都不會引入相同ID的新形式。 例如，您應確保沒有任何 VISTA 或處理規則僅在一部分事件中，將小寫字母引入暫時 ID 欄位。
* 拼接不會合併或串連欄位。
* 暫時ID欄位應包含單一ID型別（來自單一名稱空間的ID）。 例如，暫時 ID 欄位不應包含登入 ID 和電子郵件 ID 的組合。
* 如果針對同一永久ID發生了具有相同時間戳記的多個事件，但暫時ID欄位中的值不同，則拼接作業會根據字母順序來選取ID。 因此，如果永久ID A有兩個具有相同時間戳記的事件，且其中一個事件指定Bob，而另一個事件指定Ann，則拼接作業會選取Ann。
* 如果裝置由多人共用，且使用者之間的轉換總數超過50,000，Customer Journey Analytics會停止為該裝置拼接資料。
* 請小心暫時ID包含預留位置值（例如「未定義」）的情況。 另請參閱 [常見問題集](faq.md) 以取得詳細資訊。

請勿將拼接與下列混淆：

* 兩個或多個資料集的合併。 拼接僅適用於一個資料集。 設定Customer Journey Analytics連線，並在連線中選取的資料集中選取相同的人員ID，會造成資料集合併。

* 兩個資料集的聯結。 在Customer Journey Analytics中，聯結通常用於Analysis Workspace中的查閱或分類。 雖然銜接使用連線功能，但程式本身涉及的不只是連線。
