---
title: 瞭解資料摘要中的子事件和物件陣列
description: 瞭解Customer Journey Analytics資料摘要如何從結構陣列匯出子事件，以保留階層，而非如Workspace一樣將其平面化。
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# 資料摘要中的子事件

{{release-limited-testing}}

在XDM結構描述中，任何陣列（字串或物件）都是子事件。 Customer Journey Analytics中的子事件在資料摘要匯出中與其階層一起呈現。

在Adobe Analytics中，子事件會顯示為單一欄。

使用下列資訊來瞭解如何在Customer Journey Analytics資料摘要中使用子事件。

## XDM結構、Workspace和資料摘要中的子事件

您可以在XDM結構描述中將子事件定義為字串陣列或物件陣列。

這些子事件的呈現方式會有所不同，具體取決於您在Analysis Workspace中檢視還是在「資料摘要」中檢視。

| 位置 | 子事件的呈現方式 |
| --- | --- |
| **Analysis Workspace** | 物件陣列中的個別物件可選取為個別元件，與任何可見的階層分開。 |
| **資料摘要** | 物件陣列中的物件以群組表示，其階層完好無損。 |

## 將子事件資料新增至資料摘要

當您在建立資料摘要時嘗試新增作為子事件的欄時，會顯示一個對話方塊，可讓您新增所有對等子事件。 所有這些事件都會顯示在資料摘要輸出的單一欄中。

## 檢視資料摘要輸出中的子事件資料

子事件資料（例如單一事件中的多個產品）在Customer Journey Analytics資料摘要中的顯示方式與Adobe Analytics資料摘要中的顯示方式不同。 下表比較每項產品代表子事件資料的方式。

| 產品 | 子事件資料在資料摘要中的顯示方式 | 範例：產品清單 |
| --- | --- | --- |
| **Adobe Analytics** | 在單一欄中平面化為分隔字串。 | 產品清單包含在單一字串中分組的多個產品：<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件會保留您XDM結構描述中定義的階層。 它們會與父事件和同層級子事件一起分組在相同欄中。 | 產品清單會維護其在XDM結構描述中定義為陣列的階層：<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## 查詢資料摘要輸出中的子事件資料

由於子事件資料[在Customer Journey Analytics資料摘要](#customer-journey-analytics-vs-adobe-analytics)中的顯示方式不同，因此您用於它的查詢與您用於Adobe Analytics資料摘要的查詢不同。

下列範例說明如何尋找包含特定產品的事件。 這些範例使用Google BigQuery語法。 其他資料倉儲（例如Snowflake和Databricks）支援相同方法，但語法略有差異。

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






