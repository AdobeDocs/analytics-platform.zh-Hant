---
title: 瞭解資料摘要中的子事件和物件陣列
description: 瞭解Customer Journey Analytics資料摘要如何從結構陣列匯出子事件，以保留階層，而非如Workspace一樣將其平面化。
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
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# 資料摘要中的子事件

{{release-limited-testing}}

Customer Journey Analytics中的[子事件](/help/components/segments/sub-event.md)可讓您在比事件層級更精細的層級分析事件資料。

使用下列資訊來瞭解如何在Customer Journey Analytics資料摘要中使用子事件。

## 瞭解子事件

### XDM結構描述中的子事件

在XDM結構描述中，陣列的每個元素（字串陣列或物件陣列）都是子事件。

若要在Adobe Experience Platform的XDM結構描述中檢視具有子事件的事件，請選取&#x200B;[!UICONTROL **結構描述**]，然後展開包含子事件的事件。

在下列範例中，`Product list items`是包含各種子事件的物件陣列。

包含物件陣列和子事件的![XDM結構描述](assets/df-sub-event-schema.png)

### 子事件範例：購買事件中的產品

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

此事件包含兩個子事件，`productListItems`陣列中的每個物件各一個。 下表顯示哪些欄位屬於事件以及哪些欄位屬於其子事件。

| 層級 | 欄位 | 欄位說明內容 |
| --- | --- | --- |
| **事件** | `eventType`, `timestamp`, `commerce.purchases.value` | 整個購買。 每個欄位都有一個事件值。 **訂單**&#x200B;量度會針對此事件計算`1`，無論它包含多少產品。 |
| **子事件** | 每個`productListItems`物件中的`SKU`、`name`、`quantity`、`priceTotal` | 購買中的個別產品。 每個欄位針對每個產品具有一個值。 例如，`quantity`對於無繩鑽機是`1`，對於鑽機電池組是`2`。 |

{style="table-layout:auto"}

>[!NOTE]
>
>子事件僅包含隨事件傳送的資料。 Customer Journey Analytics不會從先前的事件重新建構購物車內容，例如購物車新增或結帳。 若要讓產品顯示為購買事件的子事件，您的實作必須包含在該購買事件的`productListItems`中。

## 將子事件資料新增至資料摘要

當您在建立資料摘要時嘗試新增作為子事件的欄時，會顯示對話方塊，提示您新增任何對等子事件。 在資料摘要輸出中，所有這些事件都會顯示在單一欄中。

## 檢視資料摘要輸出中的子事件資料

### Analysis Workspace與資料摘要之間的子事件差異

在Customer Journey Analytics中，Analysis Workspace和資料摘要之間的子事件呈現方式不同。

| 位置 | 子事件的呈現方式 |
| --- | --- |
| **Analysis Workspace （在Customer Journey Analytics中）** | 可選取為個別元件，與任何可見的階層分開。 |
| **資料摘要（在Customer Journey Analytics中）** | 以群組表示，其階層完整。 |

### Adobe Analytics和Customer Journey Analytics之間的子事件差異

子事件資料（例如單一購買事件中的多個產品詳細資訊）在Customer Journey Analytics資料摘要中的顯示方式與Adobe Analytics資料摘要中的顯示方式不同。 下表比較每項產品代表子事件資料的方式。

| 產品 | 子事件資料在資料摘要中的顯示方式 | 範例：產品清單 |
| --- | --- | --- |
| **Adobe Analytics** | 在單一欄中平面化為分隔字串。 | 產品清單包含在單一字串中分組的多個產品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件會保留XDM結構描述中定義的階層。 在同一欄中分組時，它們會向父事件和同層級子事件顯示其關聯階層。 | 產品清單會維護其在XDM結構描述中定義為陣列的階層：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### 與Adobe Analytics的差異

### Adobe Analytics和Customer Journey Analytics資料摘要之間的輸出有何不同

子事件資料（例如單一購買事件中的多個產品詳細資訊）在Customer Journey Analytics資料摘要中的顯示方式與Adobe Analytics資料摘要中的顯示方式不同。 下表比較每項產品代表子事件資料的方式。

| 產品 | 子事件資料在資料摘要中的顯示方式 | 範例：產品清單 |
| --- | --- | --- |
| **Adobe Analytics** | 在單一欄中平面化為分隔字串。 | 產品清單包含在單一字串中分組的多個產品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件會保留XDM結構描述中定義的階層。 在同一欄中分組時，它們會向父事件和同層級子事件顯示其關聯階層。 | 產品清單會維護其在XDM結構描述中定義為陣列的階層：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Analysis Workspace和資料摘要輸出之間的子事件有何不同

在Customer Journey Analytics中，Analysis Workspace和資料摘要之間的子事件呈現方式不同。

| 位置 | 子事件的呈現方式 |
| --- | --- |
| **Analysis Workspace** | 可選取為個別元件，與任何可見的階層分開。 |
| **資料摘要** | 以群組表示，其階層完整。 |


## 檢視資料摘要輸出中的子事件資料

子事件資料（例如單一購買事件中的多個產品詳細資訊）在Customer Journey Analytics資料摘要中的顯示方式與Adobe Analytics資料摘要中的顯示方式不同。 下表比較每項產品代表子事件資料的方式。

| 產品 | 子事件資料在資料摘要中的顯示方式 | 範例：產品清單 |
| --- | --- | --- |
| **Adobe Analytics** | 在單一欄中平面化為分隔字串。 | 產品清單包含在單一字串中分組的多個產品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件會保留XDM結構描述中定義的階層。 在同一欄中分組時，它們會向父事件和同層級子事件顯示其關聯階層。 | 產品清單會維護其在XDM結構描述中定義為陣列的階層：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## 查詢資料摘要輸出中的子事件資料

由於子事件資料[在Customer Journey Analytics資料摘要](#view-sub-event-data-in-data-feed-output)中的顯示方式不同，因此您用於它的查詢與您用於Adobe Analytics資料摘要的查詢不同。

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






