---
title: B2B 專案範例
description: 瞭解如何設定、設定和報告B2B資料
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 20756b289912dfcc4e0539db4d1ae36d1496a266
workflow-type: tm+mt
source-wordcount: '1205'
ht-degree: 7%

---

# B2B 專案範例

本文說明如何在Customer Journey Analytics中設定、設定及報告設定檔（人員）層級的B2B資料。

## 連線

定義您的連線以包含Experience Platform中所有相關的B2B資料集。 您可以考慮新增至連線的資料集：

| 資料集 | 結構描述 | 結構描述類型 | 基底類別 | 說明 |
|---|---|---|---|---|
| B2B活動資料集 | B2B活動結構描述 | 事件 | XDM ExperienceEvent | ExperienceEvent是所發生情況的事實記錄，包括時間點和所涉及個人的身分。 ExperienceEvents可以是明確的（可直接觀察的人類動作）或內隱的（在沒有直接人類動作的情況下引發），並且記錄時不會進行彙總或解譯。 體驗事件對時間網域分析至關重要，因為它們允許觀察和分析在給定時間範圍內發生的變化，並比較多個時間範圍以追蹤趨勢。 |
| B2B個人資料集 | B2B個人綱要 | 設定檔 | XDM個別設定檔 | XDM個人資料會形成已識別和部分識別個人的屬性和興趣的單一表示。 識別較少的設定檔可能僅包含匿名行為訊號，例如瀏覽器Cookie，而高度識別的設定檔可能包含詳細的個人資訊，例如姓名、出生日期、位置和電子郵件地址。 隨著個人檔案成長，它會成為個人資訊、身分資訊、聯絡詳細資料和個人通訊偏好設定的健全存放庫。 |
| B2B帳戶資料集 | B2B帳戶結構描述 | 查詢 | XDM商業帳戶 | XDM企業帳戶是一個標準的體驗資料模型(XDM)類別，可擷取企業帳戶的最低要求屬性。 此XDM類別只能包含在擁有B2B或B2P版本之客戶的個人資料中。 |
| B2B機會資料集 | B2B機會結構描述 | 查詢 | XDM商業機會 | XDM商業機會是一個標準的體驗資料模型(XDM)類別，可擷取商業機會的最低要求屬性。 此XDM類別只能包含在擁有B2B或B2P版本之客戶的個人資料中。 |
| B2B促銷活動資料集 | B2B行銷活動結構描述 | 查詢 | XDM商業活動 | XDM商業促銷活動是一個標準的體驗資料模型(XDM)類別，可擷取商業促銷活動的最低要求屬性。 此XDM類別只能包含在擁有B2B或B2P版本之客戶的個人資料中。 |
| B2B行銷清單資料集 | B2B行銷清單結構描述 | 查詢 | XDM業務行銷清單 | XDM業務行銷清單是一個標準的體驗資料模型(XDM)類別，可擷取行銷清單的最低要求屬性。 行銷清單可讓您優先處理最可能購買您產品的潛在客戶。 此XDM類別只能包含在擁有B2B或B2P版本之客戶的個人資料中。 |
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


B2B查詢結構描述、設定檔結構描述和事件結構描述之間的關係會在Experience Platform內的B2B設定中定義。 檢視[Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b)中的結構描述，以及[在Real-time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b)中定義兩個結構描述之間的多對一關係。


若要確保連線設定正確，可支援B2B資料的個人查詢功能，請使用下列圖例來概略瞭解情況，並依照下列步驟進行：

![已註解的B2B結構描述](assets/b2b-schemas-annotated.svg)

1. 從上表將資料集新增到您的連線。
1. 對於您新增至連線的每個查詢資料集，您必須在&#x200B;**[!UICONTROL 編輯資料集]**&#x200B;對話方塊中使用&#x200B;**[!UICONTROL 索引鍵]**&#x200B;和&#x200B;**[!UICONTROL 比對索引鍵]**，明確定義與事件資料集的關聯。
1. 針對您想要針對以人員為基礎的B2B查詢轉換的每個查詢資料集，請啟用&#x200B;**[!UICONTROL 轉換資料集]**，以確保針對以人員為基礎的查詢轉換資料。 如需詳細資訊，請參閱[轉換B2B查詢的資料集](/help/connections/transform-datasets-b2b-lookups.md)。

   ![索引鍵 — 相符的索引鍵](assets/key-matchingkey.png)

   下表提供每個資料集的[!UICONTROL 人員ID]、[!UICONTROL 索引鍵]和[!UICONTROL 相符的索引鍵]值的範例概觀。

   | 資料集 | 人員 ID | 金鑰 | 比對索引鍵<br/> （在事件資料集中） |
   |---|---|---|---| 
   | B2B活動資料集 | `personKey.sourceKey` | | |
   | B2B個人資料集 | `b2b.personKey.sourceKey` | | |
   | B2B帳戶資料集 | | `accountKey.sourceKey`❶<br/>Source金鑰 | `b2b.accountKey.sourceKey`❶<br/>（B2B人員資料集） |
   | B2B機會資料集 | | `opportunityKey.sourceKey`❷<br/>Source金鑰 | `opportunityKey.sourceKey`❷<br/>（B2B機會關係資料集） |
   | B2B促銷活動資料集 | | `campaignKey.sourceKey`❸<br/>Source金鑰 | `campaignKey.sourceKey`❸<br/>（B2B行銷活動成員資料集） |
   | B2B行銷清單資料集 | | `marketingListKey.sourceKey`❹<br/>Source金鑰 | `marketingListKey.sourceKey`❹<br/>（B2B行銷清單成員資料集） |
   | B2B帳戶個人關係資料集 | | `personKey.sourceKey`❺<br/>Source金鑰 | `personKey.sourceKey`❺<br/>Source金鑰（事件資料集） |
   | B2B機會個人關係資料集 | | `personKey.sourceKey`❻<br/>Source金鑰 | `personKey.sourceKey`❻<br/>Source金鑰（事件資料集） |
   | B2B促銷活動成員資料集 | | `personKey.sourceKey`❼<br/>Source金鑰 | `personKey.sourceKey`❼<br/>Source金鑰（事件資料集） |
   | B2B行銷清單成員資料集 | | `personKey.sourceKey`❽<br/>Source金鑰 | `personKey.sourceKey`❽<br/>Source金鑰（事件資料集） |

{style="table-layout:auto"}

如需如何設定資料集設定的詳細資訊，請參閱[新增及設定資料集](../../connections/create-connection.md)。


## 資料視圖

若要在建置Workspace專案時存取相關的B2B維度和量度，您必須相應地定義資料檢視。

例如，您可以將下列元件新增至資料檢視，以確保您可以根據B2B資料以人員為基礎的層級建立報表。 元件名稱有時會修改，以使其原始結構描述名稱更清楚。

+++量度

| 元件名稱 | 資料集 | 資料類型 | 結構描述路徑 |
|---|---|---|---|
| 年度帳戶收入 | B2B帳戶資料集 | 雙倍 | accountOrganization.annualRevenue.amount |
| 員工人數 | B2B帳戶資料集 | 整數 | accountOrganization.numberOfEmployees |
| 實際行銷活動成本 | B2B促銷活動資料集 | 雙倍 | actualCost.amount |
| 預算行銷活動成本 | B2B促銷活動資料集 | 雙倍 | budgetedCost.amount |
| 預期機會收入 | B2B機會資料集 | 雙倍 | expectedRevenue.amount |
| 預期行銷活動收入 | B2B促銷活動資料集 | 雙倍 | expectedRevenue.amount |
| 機會金額 | B2B機會資料集 | 雙倍 | opportunityAmount.amount |

+++

+++Dimension

| 元件名稱 | 資料集 | 資料類型 | 結構描述路徑 |
|---|---|---|---|
| 帳戶名稱 | B2B帳戶資料集 | 字串 | 帳戶名稱 |
| 行銷活動名稱 | B2B促銷活動資料集 | 字串 | campaignName |
| 管道名稱 | B2B促銷活動資料集 | 字串 | channelname |
| 國家/地區 | B2B帳戶資料集 | 字串 | accountBillingAddress.country |
| 預測類別名稱 | B2B機會資料集 | 字串 | forecastCategoryName |
| 產業 | B2B帳戶資料集 | 字串 | accountOrganization.industry |
| 姓氏 | B2B個人資料集 | 字串 | person.name.lastName |
| 行銷清單名稱 | B2B行銷清單資料集 | 字串 | marketingListName |
| 機會名稱 | B2B機會資料集 | 字串 | 機會名稱 |
| 機會階段 | B2B機會資料集 | 字串 | opportunestage |
| 機會型別 | B2B機會型別資料集 | 字串 | 機會型別 |
| 網路研討會工作階段名稱 | B2B促銷活動資料集 | 字串 | 網路研討會工作階段名稱 |

+++

## Workspace

現在，只要在資料檢視中正確定義元件，您就可以在Workspace專案中建置特定的B2B報告和視覺效果。

以下是依賴上述連線和資料檢視的範例專案熒幕擷圖。 視覺效果說明可說明哪些自由表格視覺效果需仰賴轉換後的B2B查詢資料。

![範例專案](assets/sample-workspace-project.png)

