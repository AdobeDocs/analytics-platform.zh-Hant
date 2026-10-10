---
title: 資料摘要中的陣列和地圖中的子容器元件
description: 瞭解Customer Journey Analytics資料摘要如何從陣列和對應欄位匯出子容器元件，以及如何在Data Warehouse中查詢它們。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 93107a7cf46e5d71bcb5c588eb7395fd1b88d150
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%
---
# 資料摘要中的子容器元件

{{release-limited-testing}}

子容器元件是維度和量度，根據XDM結構描述中陣列或對應內的欄位。 它們可讓您在比事件層級更精細的層級分析資料，例如購買中的個別產品。 如需在區段中使用這項資料的相關資訊，請參閱[子事件](/help/components/segments/sub-event.md)。

使用下列資訊來瞭解來自陣列和對應欄位的子容器元件如何在您的Customer Journey Analytics資料摘要中顯示。

## 瞭解子容器元件

### XDM結構描述中的子容器元件

在XDM結構描述中，陣列的每個元素（字串陣列或物件陣列）都是子容器。 對應欄位中的每個專案也是子容器，如資料摘要](#map-fields-in-data-feeds)中的[對應欄位中所述。 根據子容器內欄位的維度和量度是子容器元件。

若要在Adobe Experience Platform中檢視XDM結構描述內的子容器，請選取&#x200B;[!UICONTROL **結構描述**]，然後展開包含子容器的事件。

在下列範例中，`Product list items`是包含各種子容器元件的物件陣列。

包含物件陣列和子容器元件的![XDM結構描述](assets/df-sub-event-schema.png)

### Analysis Workspace和資料摘要之間的子容器差異

Analysis Workspace和Customer Journey Analytics中的資料摘要之間，子容器元件的呈現方式不同。

| 位置 | 子容器元件的呈現方式 |
| --- | --- |
| **Analysis Workspace （在Customer Journey Analytics中）** | 可選取為個別元件，與任何可見的階層分開。 |
| **資料摘要（在Customer Journey Analytics中）** | 以群組表示，其階層完整。 |

### Adobe Analytics和Customer Journey Analytics之間的子容器差異

子容器資料（例如單一購買事件中的多個產品詳細資訊）在Customer Journey Analytics資料摘要中的顯示方式與Adobe Analytics資料摘要中的顯示方式不同。 下表比較每項產品代表子容器資料的方式。

| 產品 | 子容器資料在資料摘要中的顯示方式 | 範例：產品清單 |
| --- | --- | --- |
| **Adobe Analytics** | 在單一欄中平面化為分隔字串。 | 產品清單包含在單一字串中分組的多個產品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子容器元件會保留XDM結構描述中定義的階層。 在同一欄中分組時，它們會向父事件和同層級子容器顯示其關聯階層。 | 產品清單會維護其在XDM結構描述中定義為陣列的階層：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### 子容器範例：購買事件中的產品

客戶單一訂購購買兩種產品：一個無繩鑽床和兩個鑽床電池組。 您的實作會傳送單一購買事件，其中包含`productListItems`物件陣列中的兩個產品：

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

此事件包含兩個子容器，`productListItems`陣列中的每個物件各一個。 下表顯示哪些欄位屬於事件，哪些欄位屬於其子容器。

| 層級 | 欄位 | 欄位說明內容 |
| --- | --- | --- |
| **事件** | `eventType`, `timestamp`, `commerce.purchases.value` | 整個購買。 每個欄位都有一個事件值。 **訂單**&#x200B;量度會針對此事件計算`1`，無論它包含多少產品。 |
| **子容器** | 每個`productListItems`物件中的`SKU`、`name`、`quantity`、`priceTotal` | 購買中的個別產品。 每個欄位針對每個產品具有一個值。 例如，`quantity`對於無繩鑽機是`1`，對於鑽機電池組是`2`。 |

{style="table-layout:auto"}

>[!NOTE]
>
>子容器僅包含隨事件傳送的資料。 Customer Journey Analytics不會從先前的事件重新建構購物車內容，例如購物車新增或結帳。 若要讓產品顯示為購買事件的子容器，您的實作必須包含在該購買事件的`productListItems`中。

## 將子容器元件新增至資料摘要

將子容器元件新增至資料摘要時，對話方塊會提示您從相同的子容器新增其他元件。

![提示您新增相關子容器元件的對話方塊](assets/data-feeds-add-subevent.png)

來自相同子容器的欄位在畫布上顯示為可收合的巢狀群組，而不是平面專案。

![子容器群組](assets/data-feeds-subevent-added.png)

此群組反映基礎資料結構。

在資料摘要輸出中，所有這些元件都會以巢狀陣列的形式顯示在單一欄中。

如需有關如何將元件（包括子容器元件）新增到資料摘要的資訊，請參閱[建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)。

## 在資料摘要輸出中查詢子容器資料

由於子容器資料[在Customer Journey Analytics資料摘要](#sub-container-differences-between-adobe-analytics-and-customer-journey-analytics)中的顯示方式不同，因此您用於子容器資料的查詢與您用於Adobe Analytics資料摘要的查詢不同。

下列範例說明如何尋找包含特定產品的事件。 這些範例使用Google BigQuery語法。 其他資料倉儲（例如Snowflake和Databricks）支援相同方法，但語法略有差異。

+++ 在Customer Journey Analytics資料摘要中查詢產品資料

在Customer Journey Analytics資料摘要中，相同的兩個產品會顯示為`product_list_items`欄中的物件陣列。 不需要分隔符號剖析：

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

查詢的編寫方式取決於您是希望每個事件有一列，還是希望每個相符產品有一列。

**每個事件傳回一列**

若要篩選事件而不變更列數，請在`EXISTS`子查詢內使用`UNNEST`：

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

此查詢會針對每個相符事件傳回一列，完整`product_list_items`陣列保持不變，無論陣列中有多少產品相符。

**每個相符產品傳回一列**

若要傳回每個相符產品的一列，請將`UNNEST`移至外部`FROM`子句：

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

具有多個相符產品的事件會顯示為多列，而事件的欄（例如`row_id`）會重複顯示於每一列。 只有在您需要產品層級的詳細資料時，才使用此方法。 若要計算結果中的事件，請使用`COUNT(DISTINCT row_id)`而不計算資料列。

此方法適用於XDM結構描述中的任何陣列欄位，而不僅僅是產品。

+++

+++ 在Adobe Analytics資料摘要中查詢產品資料

在Adobe Analytics資料摘要中，包含兩個產品一起購買的事件在`product_list`欄中顯示為單一分隔字串：

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

若要尋找包含Cordless Drill的事件，請使用規則運算式剖析此字串：

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++

## 在資料摘要中使用對應欄位

對應XDM結構描述存放區索引鍵值配對中的欄位。 資料摘要會將每個對應匯出為物件陣列，其方式與其他[子容器資料](#query-sub-container-data-in-data-feed-output)相同。 每個物件都包含對應索引鍵及其值做為個別欄位。

輸出中的欄位名稱來自您為資料摘要設定的元件ID，而不是固定名稱，例如`key`或`value`。 本節中的範例使用範例元件ID。

<!-- Confirm with Nate before publishing: how the outer array column is named in the output (for example, `survey_responses`). -->

### 簡單地圖

簡單對應是您可以在自己的結構描述中建立的對應型別。 每個鍵值都是一個字串，而每個值都是一個字串或整數。

例如，調查地圖會將每個問題儲存為索引鍵，並將回應儲存為值：

```json
{
  "_yourtenant": {
    "surveyResponses": {
      "How did you hear about us?": "Search engine",
      "How likely are you to recommend us?": 9
    }
  }
}
```

在資料摘要輸出中，`survey_question`和`survey_answer`是索引鍵和值的元件ID：

```json
{
  "survey_responses": [
    { "survey_question": "How did you hear about us?", "survey_answer": "Search engine" },
    { "survey_question": "How likely are you to recommend us?", "survey_answer": 9 }
  ]
}
```

### 身分對應

[`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap)欄位中的每個身分都會匯出為一個物件。 物件包含身分名稱空間（金鑰），以及識別碼、驗證狀態和主要旗標。 該名稱空間會針對該名稱空間中的每個身分重複執行。

系統只會匯出資料檢視中作為維度存在的身分對應屬性，以及您新增至資料摘要的屬性。

```json
{
  "identity_map": [
    { "identity_namespace": "ECID", "identity_id": "83290187457380573620940587193016478103", "authenticated_state": "ambiguous", "is_primary": true },
    { "identity_namespace": "CRMID", "identity_id": "C-1048576", "authenticated_state": "authenticated", "is_primary": false }
  ]
}
```

### 巢狀對應

某些Adobe定義的欄位（例如`segmentMembership`）為地圖地圖。 資料摘要會將其平面化為單一陣列，並使用第一層索引鍵和第二層索引鍵作為每個物件中的個別欄位。 在套用到的每個物件中會重複第一層索引鍵，因此不會遺失任何資料或關係。

例如，`segment_namespace`和`segment_id`是第一層索引鍵和第二層索引鍵的元件ID：

```json
{
  "segment_membership": [
    { "segment_namespace": "ups", "segment_id": "04a81716-43d6-4e7a-a49c-f1d8b3129ba9", "status": "realized" },
    { "segment_namespace": "ups", "segment_id": "53cba6b2-a23b-454a-8069-fc41308f1c0f", "status": "exited" }
  ]
}
```








