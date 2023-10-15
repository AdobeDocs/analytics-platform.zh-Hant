---
title: 範例B2B專案
description: 瞭解如何設定、設定和報告B2B資料
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: 980afb6d8344c04b431c596d39a8f0003b7201ba
workflow-type: tm+mt
source-wordcount: '1822'
ht-degree: 15%

---

# 範例B2B專案

本文透過範例說明如何在Customer Journey Analytics中設定、設定及報告B2B資料。

## 連線

定義您的連線以包含Experience Platform中所有相關的B2B資料集。 這包括Experience Platform中典型B2B設定所需的重要查詢資料集。 另請參閱 [新增帳戶層級資料作為查詢資料集](b2b.md) 以取得詳細資訊。

您可以考慮新增至連線的資料集：

| 資料集 | 綱要 | 結構類型 | 基底類別 | 說明 |
|---|---|---|---|---|
| B2B活動資料集 | B2B活動結構描述 | 事件 | XDM ExperienceEvent | ExperienceEvent是所發生情況的事實記錄，包括時間點和所涉及個人的身分。 ExperienceEvents可以是明確的（可直接觀察的人類動作）或內隱的（在沒有直接人類動作的情況下引發），並且記錄時不會進行彙總或解譯。 它們對於時間網域分析至關重要，因為它們允許觀察和分析在給定時間範圍內發生的變化，並比較多個時間範圍以追蹤趨勢。 |
| B2B個人資料集 | B2B個人綱要 | 設定檔 | XDM 個別設定檔 | XDM個人資料會形成已識別和部分識別個人的屬性和興趣的單一表示。 識別較少的設定檔可能僅包含匿名行為訊號，例如瀏覽器Cookie，而高度識別的設定檔可能包含詳細的個人資訊，例如姓名、出生日期、位置和電子郵件地址。 隨著個人檔案成長，它會成為個人資訊、身分資訊、聯絡詳細資料和個人通訊偏好設定的健全存放庫。 |
| B2B促銷活動成員資料集 | B2B促銷活動成員結構描述 | 查詢 | XDM商業活動會員 | XDM商業促銷活動成員是一個標準的體驗資料模型(XDM)類別，可描述與商業促銷活動相關聯的聯絡人或銷售機會。 |
| B2B帳戶資料集 | B2B帳戶結構描述 | 查詢 | XDM商業帳戶 | XDM企業帳戶是一個標準的體驗資料模型(XDM)類別，可擷取企業帳戶的最低要求屬性。 |
| B2B帳戶個人關係資料集 | B2B帳戶個人關係結構描述 | 查詢 | XDM商業帳戶個人關係 | XDM商業帳戶個人關係是一個標準的體驗資料模型(XDM)類別，可擷取與商業帳戶相關聯之個人的最低要求屬性。 |
| B2B機會資料集 | B2B機會結構描述 | 查詢 | XDM商業機會 | XDM商業機會是一個標準的體驗資料模型(XDM)類別，可擷取商業機會的最低要求屬性。 |
| B2B機會個人關係資料集 | B2B機會個人關係結構描述 | 查詢 | XDM商業機會個人關係 | XDM商業機會個人關係是一個標準的體驗資料模型(XDM)類別，可擷取與商業機會相關聯之個人的最低要求屬性。 |
| B2B促銷活動資料集 | B2B行銷活動結構描述 | 查詢 | XDM商業活動 | XDM商業促銷活動是一個標準的體驗資料模型(XDM)類別，可擷取商業促銷活動的最低要求屬性。 |
| B2B行銷清單資料集 | B2B行銷清單結構描述 | 查詢 | XDM行銷清單 | XDM業務行銷清單是一個標準的體驗資料模型(XDM)類別，可擷取行銷清單的最低要求屬性。 行銷清單可讓您優先處理最可能購買您產品的潛在客戶。 |
| B2B行銷清單成員資料集 | B2B行銷清單成員結構 | 查詢 | XDM行銷清單成員 | XDM業務行銷清單成員是一個標準的體驗資料模型(XDM)類別，可描述與行銷清單相關聯的成員、個人或聯絡人。 |

查詢結構描述、設定檔結構描述和事件結構描述之間的關係在Experience Platform內的B2B設定中定義。 請參閱結構描述 [Real-time Customer Data Platform B2B版本](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html?lang=en) 和 [在Real-time Customer Data Platform B2B Edition中定義兩個結構描述之間的多對一關係](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html?lang=en) 以取得更多詳細資料。

![B2B結構描述之間的關係](assets/classes.png)

對於您新增至連線的每個查詢資料集，您必須使用「編輯資料集」對話方塊中的「索引鍵」和「比對索引鍵」 ，明確定義與事件資料集的關係。 例如：

![索引鍵 — 相符的索引鍵](assets/key-matchingkey.png)


下表提供範例概述 [!UICONTROL 人員ID]， [!UICONTROL 索引鍵]、和 [!UICONTROL 比對索引鍵] 每個資料集的值。


| 資料集 | 人員 ID | 金鑰 | 相符的索引鍵（在事件資料集中） |
|---|---|---|---|
| B2B活動資料集 | `personKey.sourceKey` | | |
| B2B個人資料集 | `b2b.personKey.sourceKey` | | |
| B2B帳戶資料集 | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B機會資料集 | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B促銷活動資料集 | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| B2B行銷清單資料集 | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


在表格中 *_organizationID*`.interaction.*`，指的是您新增至B2B活動結構描述的自訂欄位群組，以定義與B2B帳戶和B2B機會結構描述的關係。 此 `listOperations.listKey.sourceKey` 參考新增至B2B活動結構描述的「新增至清單」欄位群組，以追蹤何時將人員新增至特定清單。

另請參閱 [新增和設定資料集](../../connections/create-connection.md) 如需如何設定資料集設定的詳細資訊。


## 資料檢視

若要在建置工作區專案時存取相關的B2B維度和量度，您必須相應地定義資料檢視。

本節提供在定義維度與量度時，應包含哪些維度和量度的建議與建議。 [元件](../../data-views/create-dataview.md#components) 針對資料檢視中的B2B資料集。

對於每個元件，都會提供名稱、結構描述型別、結構描述路徑以及有關設定的詳細資訊（若適用）。

+++ B2B活動資料集

### 量度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 新增至行銷活動 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `leadOperation.addToCampaign` |
| 新增至商機 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `opportunityEvent.addToOpportunity` |
| 應用程式已關閉 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `application.close` |
| 應用程式啟動 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `application.launch` |
| 行銷活動資料流 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** ` leadOperation.changeCampaignStream` |
| 結帳 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `commerce.checkouts` |
| 轉換潛在客戶 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `leadOperation.convertLead` |
| 電子郵件已點按 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `directMarketing.emailClicked` |
| 電子郵件已傳遞 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `directMarketing.emailDelivered` |
| 電子郵件已開啟 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `directMarketing.emailOpened` |
| 已傳送電子郵件 | 字串 | eventType | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `directMarketing.emailSent` |
| 電子郵件已取消訂閱 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `directMarketing.emailUnsubscribed` |
| 表單已填寫 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `web.formFilledOut` |
| 表單已開始 | 字串 | `web.fillOutForm.webFormName` | |
| 銷售機會 | 字串 | eventType | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `leadOperation.newLead` |
| 機會已更新 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `opportunityEvent.opportunityUpdated` |
| 價格 | 雙倍 | *_organizationID*`.interactions.products.price` |  |
| 優先等級 | 整數 | `leadOperation.changeScore.priority` |  |
| 生產清單新增 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `commerce.productListAdds.value` |
| 產品清單開啟 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `commerce.productListOpens.value` |
| 生產檢視 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `commerce.productViews.value` |
| 購買 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `commerce.purchases.value` |
| 從機會移除 | 字串 | `eventType` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `opportunityEvent.removeFromOpportunity` |
| 儲存供日後使用 | 字串 | eventType | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `commerce.productViews.value` |

{style="table-layout:auto"}


### 維度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 帳戶金鑰（來源金鑰） | 字串 | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| 已轉換的狀態 | 字串 | `leadOperation.convertLead.convertedStatus` | |
| 事件類型 | 字串 | `eventType` | |
| 表單名稱 | 字串 | `leadOperation.newLead.formName` | |
| 識別碼 | 字串 | `_id` | |
| 已傳送通知 | 布林值 | `leadOperation.convertLead.isSentNotificationEmail` | |
| 關鍵字 | 字串 | `search.keywords` | |
| 清單ID | 字串 | `listOperations.listID` | |
| 清單名稱 | 字串 | `leadOperation.newLead.listName` | |
| 頁面名稱 | 字串 | `web.webPageDetails.name` | |
| 個人金鑰（來源金鑰） | 字串 | `personKey.sourceKey` | |
| 製作者 | 字串 | productedBy | |
| 產品名稱 | 字串 | *_organizationID*`.Interactions.products.name` | |
| 角色 | 字串 | `opportunityEvent.role` | |
| 時間戳記 | 日期和時間 | `timestamp` | 日期時間格式： **[!UICONTROL 日]** |
| URL | 字串 | `web.webPageDetails.URL` | |
| 網頁表單名稱 | 字串 | `web.fillOutForm.webFormName` | |
| 產品URL | 字串 | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B個人資料集


### 量度

沒有量度元件定義為此資料集的一部分。


### 維度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 上次活動日期 | 日期和時間 | `extSourceSystemAudit.lastActivityDate` | 日期時間格式： **[!UICONTROL 日]** |
| 人員 ID | 字串 | `personID` | |

{style="table-layout:auto"}

+++


+++  B2B機會資料集

### 量度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 預期收入 | 雙倍 | `expectedRevenue.amount` | 行為： **[!UICONTROL 計數值]** |
| 機會金額 | 雙倍 | `opportunityAmount.amount` | 行為： **[!UICONTROL 計數值]** |
| 機會階段 — 已關閉的書籍 | 字串 | `opportunityStage` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `Closed - Booked` |
| 機會階段 — 潛在客戶 | 字串 | `opportunityStage` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `Prospect` |
| 機會階段 — 資格 | 字串 | `opportunityStage` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `Opportunity Qualification` |
| 機會階段 — 解決方案定義 | 字串 | `opportunityStage` | **[!UICONTROL 設定包含/排除值]**<br/>**[!UICONTROL 區分大小寫]**<br/>符合：**[!UICONTROL &#x200B;如果滿足所有條件]**<br/>條件： **[!UICONTROL 等於]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### 維度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 已關閉的旗標 | 布林值 | `isClosed` | |
| 公司ID | 字串 | `opportunityID` | |
| 預測類別 | 字串 | `forecastCategoryName` | |
| 上次活動日期 | 日期和時間 | `lastActivityDate` | 日期時間格式： **[!UICONTROL 日]** |
| 潛在客戶來源 | 字串 | `leadSource` | |
| 機會名稱 | 字串 | `opportunityName` | |
| 機會狀態 | 字串 | `opportunityStage` | |
| 已勝利的旗標 | 布林值 | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B行銷活動資料集

### 量度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 行銷活動成本 | 雙倍 | `actualCost.amount` | |

{style="table-layout:auto"}


### 維度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 行銷活動 ID | 字串 | `campaignID` | |
| 行銷活動名稱 | 字串 | `campaignName` | |
| 促銷活動開始日期 | 日期和時間 | `campaignStartDate` | 日期時間格式： **[!UICONTROL 日]** |
| 管道名稱 | 字串 | `channelName` | |
| 父級行銷活動ID | 字串 | `parentCampaignID` | |

{style="table-layout:auto"}

+++



+++ B2B帳戶資料集

### 量度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 年收入 | 雙倍 | `accountOrganization.annualRevenue.amount` | |
| 員工人數 | 整數 | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### 維度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 帳戶識別碼 | 字串 | `accountID` | |
| 帳戶類型 | 字串 | `accountType` | |
| 城市 | 字串 | `accountBillingAddress.city` | |
| 國家/地區 | 字串 | `accountBillingAddress.country` | |
| 產業 | 字串 | `accountOrganization.industry` | |
| 地區 | 字串 | `accountBillingAddress.region` | |
| 來源 ID | 字串 | `accountKey.sourceID` | |
| 來源例項ID | 字串 | `accountKey.sourceInstanceID` | |
| 來源金鑰 | 字串 | `accountKey.sourceKey` | |
| 來源類型 | 字串 | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


+++ B2B促銷活動成員資料集

### 量度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 已跳出 | 長整數 | *_organizationID*`.campaignBounced` | 行為： **[!UICONTROL 計數值]** |
| 已點按 | 長整數 | *_organizationID*`.campaignClicked` | 行為： **[!UICONTROL 計數值]** |
| 已開啟 | 長整數 | *_organizationID*`.CampaignOpened` | 行為： **[!UICONTROL 計數值]** |
| 已傳送 | 長整數 | *_organizationID*`.campaignSent` | 行為： **[!UICONTROL 計數值]** |
| 已訂閱 | 長整數 | *_organizationID*`.campaignSubscribed` | 行為： **[!UICONTROL 計數值]** |
| 網路研討會註冊 | 長整數 | *_organizationID*`.Registrations` | 行為： **[!UICONTROL 計數值]** |

{style="table-layout:auto"}

### 維度

| 元件名稱 | 結構描述資料類型 | 結構描述路徑 | 設定 |
|---|---|---|---|
| 行銷活動 ID | 字串 | `campaignID` | |
| 促銷活動會員ID | 字串 | `campaignMemberID` | |
| 促銷活動會員狀態 | 字串 | `memberStatus` | |
| 促銷活動會員狀態原因 | 字串 | `memberStatusReason` | |
| 建立日期 | 日期和時間 | `extSourceSystemAudit.createdDate` | 日期時間格式： **[!UICONTROL 日]** |
| 第一個回應日期 | 字串 | `firstRespondedDate` | 日期時間格式： **[!UICONTROL 日]** |
| 已取得成功 | 布林值 | `hasReachedSuccess` | |
| 已回應 | 布林值 | `hasResponded` | |
| 上次狀態 | 字串 | `lastStatus` | |
| 上次更新日期 | 日期和時間 | `extSourceSystemAudit.lastUpdatedDate` | 日期時間格式： **[!UICONTROL 日]** |
| 會籍日期 | 日期和時間 | `membershipDate` | 日期時間格式： **[!UICONTROL 日]** |
| Nurture步調 | 字串 | `nurtureCadence` | |
| Nurture追蹤名稱 | 字串 | `nurtureTrackName` | |
| 人員 ID | 字串 | `personID` | |
| 已達到成功日期 | 日期和時間 | `reachedSuccessDate` | 日期時間格式： **[!UICONTROL 日]** |
| 網路研討會註冊ID | 字串 | `webinarRegistrationID` | |
| 網路研討會註冊URL | 字串 | `webinarConfirmationUrl` | |
| isExhausted | 布林值 | isExhausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## Workspace

只要元件已正確定義，您現在就能在Workspace專案中建置特定的B2B視覺效果。

以下是依賴上述連線和資料檢視的工作區專案範例。 如需詳細資訊，請參閱每個視覺效果的說明。

+++ 詳細資料

![視覺效果](assets/visualizations.png)

+++

