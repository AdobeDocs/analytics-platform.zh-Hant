---
title: 摘要資料
description: 瞭解如何在資料檢視中使用和設定摘要資料的詳細資訊和資訊。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 96%

---

# 摘要資料

摘要資料是未連結至個別個人 ID 的時間序列資料。摘要資料代表不同彙總等級的彙總資料，例如行銷活動。您可以在 Customer Journey Analytics 中使用此資料來支援各種使用案例。例如，包含日期和單一指量度的資料，或包含多個維度和量度的資料。

然後可以使用這些摘要資料來呈現高層級效能指標或進行分析。摘要資料範例有廣告曝光度、電子郵件開啟數、廣告支出、已售商品成本、標準普爾指數等。您也可以使用摘要資料按每小時或每天方式來上傳目標。

>[!NOTE]
>
>摘要資料是來自摘要資料集的時間序列資料。此摘要資料集依據的結構描述是使用 XDM 摘要量度類別，並且是以此為基本類別。
>僅支援以每小時或每天為依據的時間序列資料。

>[!TIP]
>
>您可以設定連線、資料檢視，接著&#x200B;**僅限**&#x200B;摘要資料進行報告。您的設定中不需要有額外的事件、設定檔或查詢資料。


## 範例

使用摘要資料的範例為：結合匯總廣告活動資料與現場點按資料流資料供報告

### 摘要資料

您的摘要資料包含以下廣告活動資料。

| 促銷活動代碼 | 曝光數 | 成本 |
|---|---:|---:|
| abc123 | 1,250 | $1,500 |
| def456 | 775 | $650 |
| ghi789 | 500 | $500 |


### 事件資料

您的現場點按資料流資料包含以下事件。

| 追蹤程式碼 | 點進次數 | 收入 |
|---|---:|---:|
| abc123 | 1,250 | $7,200 |
| def456 | 775 | $1,250 |
| ghi789 | 500 | $750 |

### 合併的資料

如「[合併事件資料集](/help/connections/combined-dataset.md)」所述，在定義連線時，Customer Journey Analytics 會建立一個整體合併事件資料集。當您為源自摘要資料集的維度設定資料檢視時，可以使用選項進行維度分類和隱藏，作為在 Workspace 中報告的準備。特別以摘要資料來說，摘要資料會與事件資料合併 (根據[摘要資料群組元件](component-settings/summary-data-group.md)設定)

| 追蹤程式碼 | 促銷活動代碼 | 曝光數 | 成本 | 點進次數 | 收入 |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | $1,500 | 1,250 | $7,200 |
| def456 | def123 | 775 | $650 | 775 | $1,250 |
| ghi789 | ghi789 | 500 | $500 | 500 | $750 |



### 報告

合併匯總的事件資料和現場點按資料流資料，可讓您在 Workspace 中報告廣告投資報酬率 (ROAS)。

| 追蹤程式碼 | 曝光數 | 成本 | 點進次數 | 收入 | 廣告投資報酬率 |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | $1,500 | 1,250 | $7,200 | 4.80 |
| def456 | 775 | $650 | 775 | $1,250 | 1.92 |
| ghi789 | 500 | $500 | 500 | $750 | 1.50 |


### 查詢資料

如果您想要使用在額外查詢資料集中定義的維度 (例如，促銷活動名稱) 進行報告，則必須遵循以下的額外步驟：

1. 建立使用[查詢](/help/data-views/derived-fields/derived-fields.md#lookup)功能的新衍生欄位，查詢來自查詢資料集的促銷活動名稱。在[查詢](/help/data-views/derived-fields/derived-fields.md#lookup)函數定義中，您可以使用促銷活動代碼與追蹤代碼符合的資料來查詢促銷活動名稱。
1. 將新建立的派生欄位作為維度元件新增至資料檢視。
1. 設定促銷活動名稱維度元件 (來自查詢資料集)，以便使用新建立的派生欄位進行摘要資料分組。

請參閱[攝取並報告摘要資料](/help/use-cases/data-views/summary-data.md)使用案例，了解有關如何運用、報告和分析 Customer Journey Analytics 中摘要資料的詳細文章。


## 先決條件

若要在報告和分析中正確使用摘要資料，需要滿足一些先決條件。以下部分有這些先決條件的詳細說明。

### 顆粒度和時區

在 Customer Journey Analytics 中設定含有摘要資料的資料集時，您會注意到顆粒度是從資料中自動衍生。已停用&#x200B;**[!UICONTROL 時間戳記]**&#x200B;和&#x200B;**[!UICONTROL 時區]**&#x200B;下拉式功能表的選取專案，因為兩者都是衍生自結構描述定義。

#### 顆粒度

您不能使用一個摘要資料結構描述來混合搭配一個資料集 (或不同的資料集) 中摘要資料的每小時和每日顆粒度。例如，如果您的促銷活動資料有每日和每小時的詳細程度摘要資料，則需要兩種結構描述：一種用於每日摘要資料，另一種用於每小時摘要資料。然後將相關的詳細程度資料上傳到與適當結構描述相關聯的資料集中 (例如，將每小時資料上傳到與每小時摘要資料結構描述相關聯的資料集中)。

#### 時區

摘要資料的時區是在 Experience Platform 中以摘要結構描述層級來定義。時區僅適用於每小時詳細程度的資料。

- 若是每日顆粒度，Experience Platform 會設定為 UTC，除非時區內含有時間戳記位移。在新增含有每日摘要資料的摘要資料集時，Customer Journey Analytics 會忽略結構描述上設定的時區定義，並遵守與資料集資料的時間戳記相關聯的日期。
- 若是每小時顆粒度，Customer Journey Analytics 在解釋時間戳記時會遵守 Experience Platform 中摘要資料結構描述上設定的時區。下表提供了此解釋的一些範例。

  | 時間戳記 <br/>來源資料 | 時區<br/>結構描述 | 時間戳記<br/>Experience<br/>Platform | 時區<br/> 資料<br/>檢視 | 時間戳記<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *預設 GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *預設 GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *預設 GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *預設 GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *預設 GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  若是有 30 分鐘位移的時區 (例如 IST，印度標準時間)，報告摘要資料時會減少 30 分鐘位移。例如： 12:30回報為12:00。


為了確保每小時詳細程度摘要資料使用正確的時區，您必須確保用於摘要資料的結構描述設定好正確時區。

若要為您的摘要資料結構描述設定顆粒度和時區，您必須使用以下 API 呼叫，因為沒有適用的等效使用者介面。

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| 變數 | 值 |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 請參閱[驗證並存取 Experience Platform API](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-apis/api-authentication)，了解更多有關如何指定這些變數的值。 |
| `$SCHEMA_ID` | 您可以在 Experience Platform UI 中找到結構描述的 ID。從結構描述清單中選取您的摘要結構描述，然後在右側面板找到「**[!UICONTROL API 使用情況]** > **[!UICONTROL 結構描述 ID]**」。使用該 id 作為值。 |
| `$GRANULARITY` | 指定 `hour` 或 `day` 作為值。 |
| `$TIMEZONE` | 從 [tz 資料庫時區清單](https://zh.wikipedia.org/wiki/List_of_tz_database_time_zones)中的 TZ 識別碼欄指定正確的時區識別碼值。例如：`America/Los_Angeles`。 |

## 元件設定

確保摘要資料群組的元件設定相同。請參閱「[摘要資料群組元件設定](component-settings/summary-data-group.md#same-component-settings)」，了解更多詳細資訊。

>[!MORELIKETHIS]
>
>- 請參閱「[使用摘要資料](/help/use-cases/data-views/summary-data.md)」文章，了解如何使用和報告摘要資料的詳細使用案例範例。
>- 部落格：[摘要資料如何增強 Adobe Customer Journey Analytics 資料集](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

