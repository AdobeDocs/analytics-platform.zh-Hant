---
title: B2B 專案範例
description: 瞭解如何設定、設定和報告B2B資料
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: c3d97fe2353011f4747d0c1742e49189cc91b85c
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 10%

---

# B2B 專案範例

本文說明如何在Customer Journey Analytics中設定、設定及報告設定檔（人員）層級的B2B資料。

## 連線

定義您的連線以包含Experience Platform中所有相關的B2B資料集。 確保您包含並轉換典型B2B以人員為基礎的報告案例所需的所有相關查詢資料集。 如需詳細資訊，請參閱[轉換B2B查詢資料集](/help/connections/transform-datasets-b2b-lookups.md)。

您可以考慮新增至連線的資料集：

| 資料集 | 結構描述 | 結構描述類型 | 基底類別 | 說明 |
|---|---|---|---|---|
| B2B活動資料集 | B2B活動結構描述 | 事件 | XDM ExperienceEvent | ExperienceEvent是所發生情況的事實記錄，包括時間點和所涉及個人的身分。 ExperienceEvents可以是明確的（可直接觀察的人類動作）或內隱的（在沒有直接人類動作的情況下引發），並且記錄時不會進行彙總或解譯。 它們對於時間網域分析至關重要，因為它們允許觀察和分析在給定時間範圍內發生的變化，並比較多個時間範圍以追蹤趨勢。 |
| B2B個人資料集 | B2B個人綱要 | 設定檔 | XDM個別設定檔 | XDM個人資料會形成已識別和部分識別個人的屬性和興趣的單一表示。 識別較少的設定檔可能僅包含匿名行為訊號，例如瀏覽器Cookie，而高度識別的設定檔可能包含詳細的個人資訊，例如姓名、出生日期、位置和電子郵件地址。 隨著個人檔案成長，它會成為個人資訊、身分資訊、聯絡詳細資料和個人通訊偏好設定的健全存放庫。 |
| B2B帳戶個人關係資料集 | B2B帳戶個人關係結構描述 | 查詢 | XDM 商業帳戶個人關係 | XDM商業帳戶個人關係是一個標準的體驗資料模型(XDM)類別，可擷取與商業帳戶相關聯之個人的最低要求屬性。 |
| B2B機會個人關係資料集 | B2B機會個人關係結構描述 | 查詢 | XDM 商業機會個人關係 | XDM商業機會個人關係是一個標準的體驗資料模型(XDM)類別，可擷取與商業機會相關聯之個人的最低要求屬性。 |
| B2B行銷清單成員資料集 | B2B行銷清單成員結構 | 查詢 | XDM行銷清單成員 | XDM業務行銷清單成員是一個標準的體驗資料模型(XDM)類別，可描述與行銷清單相關聯的成員、個人或聯絡人。 |
| B2B促銷活動成員資料集 | B2B促銷活動成員結構描述 | 查詢 | XDM 商業活動會員 | XDM商業促銷活動成員是一個標準的體驗資料模型(XDM)類別，可描述與商業促銷活動相關聯的聯絡人或銷售機會。 |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


查詢結構描述、設定檔結構描述和事件結構描述之間的關係在Experience Platform內的B2B設定中定義。 如需詳細資訊，請參閱[Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html)中的結構描述，以及[在Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html)中定義兩個結構描述之間的多對一關係。

![B2B結構描述之間的關係](assets/classes.png)

對於您新增至連線的每個查詢資料集，您必須在&#x200B;**[!UICONTROL 編輯資料集]**&#x200B;對話方塊中使用&#x200B;**[!UICONTROL 索引鍵]**&#x200B;和&#x200B;**[!UICONTROL 相符的索引鍵]**，明確定義與事件資料集的關聯。 例如：

![索引鍵 — 相符的索引鍵](assets/key-matchingkey.png)

有四個結構描述明確用於將個人結構描述連結到其他相關結構描述：帳戶、機會、行銷活動和行銷清單。 這些結構描述是以下列結構描述類別為基礎：

* XDM 商業帳戶個人關係
* XDM 商業機會個人關係
* XDM 業務行銷清單會員
* XDM 商業活動會員

對於每個查詢資料集，對於以此類結構描述類別為基礎的結構描述，您也會啟用&#x200B;**[!UICONTROL 轉換資料集]**，以確保轉換資料以進行人員型查詢。 請參閱[轉換資料集以進行 B2B 查詢](/help/connections/transform-datasets-b2b-lookups.md)，了解更多資訊。

下表提供每個資料集的[!UICONTROL 人員ID]、[!UICONTROL 索引鍵]和[!UICONTROL 相符的索引鍵]值的範例概觀。


| 資料集 | 人員 ID | 金鑰 | 相符的索引鍵（在事件資料集中） |
|---|---|---|---|
| B2B活動資料集 | `personKey.sourceKey` | | |
| B2B個人資料集 | `b2b.personKey.sourceKey` | | |
| B2B帳戶個人資料集 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B機會資料集 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B促銷活動成員資料集 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B行銷清單資料集 | | `personKey.sourceKey` | `personKey.sourceKey` |

{style="table-layout:auto"}

如需如何設定資料集設定的詳細資訊，請參閱[新增及設定資料集](../../connections/create-connection.md)。


## 資料視圖

若要在建置Workspace專案時存取相關的B2B維度和量度，您必須相應地定義資料檢視。

您可以將下列元件新增為資料檢視的維度，以確保您可以根據B2B資料製作以人員為基礎的層級報表。 為了清楚起見，元件名稱會經過修改。

| 元件名稱 | 資料集 | 結構描述資料類型 | 結構描述路徑 |
|---|---|---|---|
| 「人」 | B2B活動 | 字串 | `personID` |
| 帳戶 | B2B帳戶人員 | 字串 | `accountKey.sourceID` |
| 促銷活動 | B2B行銷活動會員 | 字串 | `campaignKey.sourceKey` |
| 行銷清單名稱 | B2B行銷清單 | 字串 | `marketingListID` |
| 商機 | B2B機會人員 | 字串 | `opportunityKey.sourceID` |


<!--
This section provides recommendations and suggestions on what dimensions and metrics to include when defining the [components](../../data-views/create-dataview.md#components) for B2B datasets in your data view.

For each component, the name, schema type, schema path, and (when applicable) details about the configuration are provided.


+++ B2B Activity dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Add To Campaign | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Add To Opportunity | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Application Closed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.close` |
| Application Launch | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.launch` |
| Campaign Stream | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Checkout | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.checkouts` |
| Convert Lead | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| Email Clicked | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| Email Delivered | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| Email Opened | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| Email Sent | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| Email Unsubscribed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Form Filled Out | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `web.formFilledOut` |
| Form Started | String | `web.fillOutForm.webFormName` | |
| Leads | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunity Updated | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Price | Double | *_organizationID*`.interactions.products.price` |  |
| Priority | Integer | `leadOperation.changeScore.priority` |  |
| Prod List Add | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Prod List Open | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Prod View | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Purchases | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Remove From Opportunity | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Save for Laters | String | eventType |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Account Key (Source Key) | String | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Converted Status | String | `leadOperation.convertLead.convertedStatus` | |
| Event Type | String | `eventType` | |
| Form Name | String | `leadOperation.newLead.formName` | |
| Identifier | String | `_id` | |
| Is Sent Notification | Boolean | `leadOperation.convertLead.isSentNotificationEmail` | |
| Keywords | String | `search.keywords` | |
| List ID | String | `listOperations.listID` | |
| List Name | String | `leadOperation.newLead.listName` | |
| Page Name | String | `web.webPageDetails.name` | |
| Person Key (Source Key) | String | `personKey.sourceKey` | |
| Produced By | String | producedBy | |
| Product Name | String | *_organizationID*`.Interactions.products.name` | |
| Role | String | `opportunityEvent.role` | | 
| Timestamp | Date-time | `timestamp` | Date-Time format: **[!UICONTROL Day]** |
| URL | String | `web.webPageDetails.URL` | |
| Web Form Name | String | `web.fillOutForm.webFormName` | |
| Product URL | String | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person dataset


### Metrics

No metric components are defined as part of this dataset.


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Last Activity Date | Date-time | `extSourceSystemAudit.lastActivityDate` | Date-Time format: **[!UICONTROL Day]** |
| Person ID | String | `personID` | |

{style="table-layout:auto"}

+++

+++ B2B Account Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Annual Revenue | Double | `accountOrganization.annualRevenue.amount` | |
| Number of employees | Integer | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Acount | String | `accountKey.sourceID` | 

{style="table-layout:auto"}

| Account Identifier | String | `accountID` | |
| Account Type | String | `accountType` | |
| City | String | `accountBillingAddress.city` | |
| Country | String | `accountBillingAddress.country` | |
| Industry | String | `accountOrganization.industry` | |
| Region | String | `accountBillingAddress.region` | |
| Source ID | String | `accountKey.sourceID` | |
| Source Instance ID | String | `accountKey.sourceInstanceID` | |
| Source Key | String | `accountKey.sourceKey` | |
| Source Type | String | `accountKey.sourceType` | |


+++

+++  B2B Opportunity Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Expected Revenue | Double | `expectedRevenue.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Closed - Booked` |
| Opportunity Stage - Prospect | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Prospect` |
| Opportunity Stage - Qualification | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Opportunity Stage - Solution Definition | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Closed Flag | Boolean | `isClosed` | |
| Company ID | String | `opportunityID` | |
| Forecast Category | String | `forecastCategoryName` | |
| Last Activity Date | Date-time | `lastActivityDate` | Date-time format: **[!UICONTROL Day]** |
| Lead Source | String | `leadSource` | |
| Opportunity Name | String | `opportunityName` | | 
| Opportunity Status | String | `opportunityStage` | |
| Won Flag | Boolean | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign Member dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Bounced | Long | *_organizationID*`.campaignBounced` | Behavior: **[!UICONTROL Count values]** |
| Clicked | Long | *_organizationID*`.campaignClicked` | Behavior: **[!UICONTROL Count values]** |
| Opened | Long | *_organizationID*`.CampaignOpened` | Behavior: **[!UICONTROL Count values]** |
| Sent | Long | *_organizationID*`.campaignSent` | Behavior: **[!UICONTROL Count values]** |
| Subscribed | Long | *_organizationID*`.campaignSubscribed` | Behavior: **[!UICONTROL Count values]** |
| Webinar Registrations | Long | *_organizationID*`.Registrations` | Behavior: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Campaign ID | String | `campaignID` | |
| Campaign Member ID | String | `campaignMemberID` | |
| Campaign Member Status | String | `memberStatus` | |
| Campaign Member Status Reason | String | `memberStatusReason` | |
| Created Date | Date-time | `extSourceSystemAudit.createdDate` | Date-time format: **[!UICONTROL Day]** |
| First Responded Date | String | `firstRespondedDate` | Date-time format: **[!UICONTROL Day]** |
| Has Reached Success | Boolean | `hasReachedSuccess` | |
| Has Responded | Boolean | `hasResponded` | |
| Last Status | String | `lastStatus` | |
| Last Updated Date | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Date-time format: **[!UICONTROL Day]** |
| Membership Date | Date-time | `membershipDate` | Date-time format: **[!UICONTROL Day]** |
| Nurture Cadence | String | `nurtureCadence` | |
| Nurture Track Name | String | `nurtureTrackName` | |
| Person ID | String | `personID` | |
| Reached Success Date | Date-time | `reachedSuccessDate` | Date-time format: **[!UICONTROL Day]** |
| Webinar Registration ID | String | `webinarRegistrationID` | |
| Webinar Registration URL | String | `webinarConfirmationUrl` | |
| isExhausted | Boolean | isExhausted | |

{style="table-layout:auto"}

+++

+++ B2B Marketing List Member dataset

### Metrics

### Dimensions

+++

-->

## Workspace

現在，只要在資料檢視中正確定義元件，您就可以在Workspace專案中建置特定的B2B報告和視覺效果。

以下是依賴上述連線和資料檢視的範例專案。

![範例專案](assets/sample-project.png)

<!-- See the descriptions for each visualization for more details.

+++ Example project

![Visualizations](assets/visualizations.png)

+++
-->
