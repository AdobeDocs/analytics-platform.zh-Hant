---
title: 摘要資料
description: 有關如何在資料檢視中使用和設定摘要資料的詳細資料和資訊。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: e2e04432682f94b18bf9ed25d15f906c05bfd59d
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 7%

---

# 摘要資料

摘要資料是不繫結至個別人員ID的時間序列資料。 摘要資料代表不同彙總等級的彙總資料，例如行銷活動。您可以在 Customer Journey Analytics 中使用此資料來支援各種使用案例。例如，包含日期和單一量度值的資料，或包含多個維度和量度的資料。

然後，此摘要資料可用於呈現高階績效指標或執行分析。 摘要資料的範例可為廣告曝光數、電子郵件開啟次數、廣告支出、已售出商品成本、S&amp;P指數等。 您也可以使用摘要資料，每小時或每天上傳目標或目標。

>[!NOTE]
>
>摘要資料是摘要資料集中的時間序列資料。 該摘要資料集是以使用XDM摘要量度類別作為其基底類別的結構描述為基礎。
>僅支援以每小時或每日為基礎的時間序列資料。

>[!TIP]
>
>您可以設定連線、資料檢視，並接著報告&#x200B;**僅限**&#x200B;摘要資料。 您的設定不需要有其他事件、設定檔或查詢資料。


## 範例

使用摘要資料的範例是將摘要的廣告行銷活動資料與網站上的點按資料流資料結合，以便進行報告。

### 摘要資料

您的摘要資料包含下列廣告行銷活動資料。

| 行銷活動代碼 | 曝光數 | 成本 |
|---|---:|---:|
| abc123 | 1,250 | $1,500 |
| def456 | 775 | $650 |
| ghi789 | 500 | $500 |


### 事件資料

您的站上點按資料流資料包含下列事件。

| 追蹤代碼 | 點進次數 | 收入 |
|---|---:|---:|
| abc123 | 1,250 | $7,200 |
| def456 | 775 | $1,250 |
| ghi789 | 500 | 750美元 |

### 合併的資料

如[合併事件資料集](/help/connections/combined-dataset.md)中所述，定義連線時，Customer Journey Analytics會建立整體的合併事件資料集。 當您為源自摘要資料集的維度設定資料檢視時，選項可用於分組和隱藏維度，以準備在Workspace中報告。 特別針對摘要資料，摘要資料會根據[摘要資料群組元件](component-settings/summary-data-group.md)組態與事件資料結合。

| 追蹤代碼 | 行銷活動代碼 | 曝光數 | 成本 | 點進次數 | 收入 |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | $1,500 | 1,250 | $7,200 |
| def456 | def123 | 775 | $650 | 775 | $1,250 |
| ghi789 | ghi789 | 500 | $500 | 500 | 750美元 |



### 報表

結合摘要事件資料和站上點按資料流資料，您就能在Workspace中報告廣告投資報酬率(ROAS)。

| 追蹤代碼 | 曝光數 | 成本 | 點進次數 | 收入 | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | $1,500 | 1,250 | $7,200 | 4.80 |
| def456 | 775 | $650 | 775 | $1,250 | 1.92 |
| ghi789 | 500 | $500 | 500 | 750美元 | 1.50 |


### 查詢資料

如果您想使用在其他查詢資料集中定義的維度來報告（例如促銷活動名稱），則必須依照下列其他步驟進行：

1. 建立新的衍生欄位，使用[查詢](/help/data-views/derived-fields/derived-fields.md#lookup)函式從查詢資料集中查詢促銷活動名稱。 在[Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)函式的定義中，您會使用行銷活動代碼與追蹤代碼之間的比對來查詢行銷活動名稱。
1. 將新建立的衍生欄位作為維度元件新增到資料檢視。
1. 設定行銷活動名稱維度元件（從查詢資料集）以使用新建立的衍生欄位進行摘要資料分組。

請參閱[擷取及報告摘要資料](/help/use-cases/data-views/summary-data.md)使用案例，以取得有關如何在Customer Journey Analytics中使用、報告及分析摘要資料的詳細文章。


## 先決條件

若要在報表和分析中正確使用摘要資料，需滿足幾項必要條件。 以下小節詳細說明這些先決條件。

### 詳細程度和時區

在Customer Journey Analytics中設定包含摘要資料的資料集時，您會注意到粒度會自動從資料衍生。 已停用&#x200B;**[!UICONTROL Timestamp]**&#x200B;和&#x200B;**[!UICONTROL Timezone]**&#x200B;下拉式清單的選擇，因為兩者都是衍生自結構描述定義。

#### 詳細程度

使用單一摘要資料結構描述，您無法在一個資料集（或不同資料集）中混合搭配每小時和每日詳細程度的摘要資料。 例如，如果您的廣告行銷活動資料有每日和每小時精細的摘要資料，您需要兩個結構：一個用於每日，另一個用於每小時摘要資料。 然後上傳相關的精細資料至與適當結構描述相關聯的資料集（例如，將每小時資料上傳至與每小時摘要資料結構描述相關聯的資料集）。

#### 時區

您摘要資料的時區是在Experience Platform的摘要結構層級定義。 時區僅適用於每小時精細資料。

- 對於每日粒度，Experience Platform會假設UTC，除非時間戳記中包含時區位移。 新增包含每日摘要資料的摘要資料集時，Customer Journey Analytics會忽略結構描述上設定的時區定義，並從資料集中的資料中尊重與時間戳記相關聯的日期。
- 針對每小時詳細程度，Customer Journey Analytics在解譯時間戳記時，會遵守Experience Platform中摘要資料結構上設定的時區。 下表提供此詮釋的一些範例。

  | 時間戳記<br/>來源資料 | 時區<br/>結構描述 | 時間戳記<br/>Experience<br/>平台 | 時區<br/>資料<br/>檢視 | 時間戳記<br/>客戶<br/>歷程<br>分析 |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *預設GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *預設GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *預設GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *預設GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *預設GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  如果時區有30分鐘時差（例如IST、印度標準時間），則在報告摘要資料時會捨棄30分鐘時差。 例如：12:30會回報為12:00。


為確保您的每小時精細摘要資料採用正確的時區，您必須確保用於摘要資料的結構描述已設定正確的時區。

若要設定摘要資料結構的詳細程度和時區，由於沒有同等的使用者介面可用，因此您必須使用以下API呼叫。

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 如需如何指定這些變數之值的詳細資訊，請參閱[驗證及存取Experience Platform API](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication)。 |
| `$SCHEMA_ID` | 您可以在Experience Platform UI中找到結構描述的ID。 從結構描述清單中選取您的摘要結構描述，然後在右側面板中尋找&#x200B;**[!UICONTROL API使用狀況]** > **[!UICONTROL 結構描述ID]**。 使用該id作為值。 |
| `$GRANULARITY` | 指定`hour`或`day`作為值。 |
| `$TIMEZONE` | 從tz資料庫時區](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)的[List of tz識別碼資料行中，指定適當的時區識別碼值。 例如：`America/Los_Angeles`。 |

## 元件設定

確認摘要資料群組的元件設定相同。 如需詳細資訊，請參閱[摘要資料群組元件設定](component-settings/summary-data-group.md#same-component-settings)。

>[!MORELIKETHIS]
>
>- 請參閱[使用摘要資料](/help/use-cases/data-views/summary-data.md)文章，以取得有關如何使用和報告摘要資料的詳細使用案例範例。
>- 部落格： [摘要資料如何增強Adobe Customer Journey Analytics資料集](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

