---
title: 摘要資料
description: 有關如何在資料檢視中使用和設定摘要資料的詳細資料和資訊。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 9517d698acf41a25fa972ced32faa75de540a080
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 4%

---


# 摘要資料

{{release-limited-testing}}

摘要資料是不繫結至個別人員ID的時間序列資料。 摘要資料代表不同彙總層級的彙總資料，例如促銷活動。 您可以在Customer Journey Analytics中使用此資料來支援各種使用案例。 例如，包含日期和單一量度值的資料，或包含多個維度和量度的資料。

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


請參閱[擷取及報告摘要資料](/help/use-cases/data-views/summary-data.md)使用案例，以取得有關如何使用、報告及分析Customer Journey Analytics中摘要資料的詳細文章。


## 先決條件

若要在報表和分析中正確使用摘要資料，需滿足幾項必要條件。 以下小節詳細說明這些先決條件。

### 詳細程度和時區

當設定包含Customer Journey Analytics摘要資料的資料集時，您會注意到粒度會自動從資料衍生。 已停用&#x200B;**[!UICONTROL Timestamp]**&#x200B;和&#x200B;**[!UICONTROL Timezone]**&#x200B;下拉式清單的選擇，因為兩者都是衍生自結構描述定義。

#### 詳細程度

使用單一摘要資料結構描述，您無法在一個資料集（或不同資料集）中混合搭配每小時和每日詳細程度的摘要資料。 例如，如果您的廣告行銷活動資料有每日和每小時精細的摘要資料，您需要兩個結構：一個用於每日，另一個用於每小時摘要資料。 然後上傳相關的精細資料至與適當結構描述相關聯的資料集（例如，將每小時資料上傳至與每小時摘要資料結構描述相關聯的資料集）。

#### 時區

您摘要資料的時區是在Experience Platform的摘要結構層級定義。 時區僅適用於每小時精細資料。

- 對於每日粒度，除非時間戳記中包含時區位移，否則Experience Platform會假設UTC時間。 新增包含每日摘要資料的摘要資料集時，Customer Journey Analytics會忽略結構描述上設定的時區定義，並從資料集中的資料中遵守與時間戳記相關聯的日期。
- 對於每小時粒度，Customer Journey Analytics在解譯時間戳記時，會遵循在Experience Platform的摘要資料結構上設定的時區。 下表提供此詮釋的一些範例。

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 請參閱[驗證及存取Experience PlatformAPI](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication)，以取得如何指定這些變數的值的詳細資訊。 |
| `$SCHEMA_ID` | 您可以在Experience PlatformUI中找到結構描述的ID。 從結構描述清單中選取您的摘要結構描述，然後在右側面板中尋找&#x200B;**[!UICONTROL API使用狀況]** > **[!UICONTROL 結構描述ID]**。 使用該id作為值。 |
| `$GRANULARITY` | 指定`hour`或`day`作為值。 |
| `$TIMEZONE` | 從tz資料庫時區](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)的[List of tz識別碼資料行中，指定適當的時區識別碼值。 例如: `America/Los_Angeles`。 |

## 元件設定

確認摘要資料群組的元件設定相同。 如需詳細資訊，請參閱[摘要資料群組元件設定](component-settings/summary-data-group.md#same-component-settings)。

>[!MORELIKETHIS]
>
>請參閱[擷取及使用摘要資料](/help/use-cases/data-views/summary-data.md)文章，以取得有關如何使用和報告摘要資料的詳細使用案例範例。