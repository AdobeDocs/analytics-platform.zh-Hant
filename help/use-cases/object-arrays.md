---
title: 使用物件陣列
description: 瞭解如何Customer Journey Analytics資料階層的報表。
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# 使用物件陣列

某些平台結構允許使用物件陣列。Adobe Customer Journey Analytics支援事件、查詢和設定檔資料中物件陣列的擷取和報表功能。 內含多種產品的購物車是最常見的例子。每樣產品都有名稱、SKU、類別、價格、數量，以及您要追蹤的其他任何維度。這些面向的規定各不相同，但全都必須符合相同點擊規範。

舊版 Adobe Analytics 中，此功能是使用 `products`變數來完成。該變數是以分號 (`;`) 分隔的串連字串，以區隔產品的各個面向，而逗號 (`,`) 則劃分產品。這是唯一有限支援「物件陣列」的變數。清單變數之類的多值變數可支援同等陣列，但無法支援「物件陣列」。Customer Journey Analytics擴充了此概念，在單一資料列中支援任意深度的階層，任何舊版Adobe Analytics皆未支援此功能。

## 相同事件範例

以下事件是JSON物件，代表客戶購買洗衣機和烘衣機。

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

建立資料檢視時，可 (根據結構) 使用下列維度和量度：

* **維度：**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : warranty : coverage
   * prodcut : warranty : length
   * product : warranty : name
   * product : warranty : type
* **量度：**
   * product : orders
   * product : units
   * product : revenue
   * product : warranty
   * product : warranty : revenue

### 相同事件範例（報表行為）

下表僅採計上述事件，顯示包含某些維度和量度組合的Workspace報表。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

Customer Journey Analytics會根據表格選擇性地檢視物件的維度和量度。

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

如果您只想針對保固收入產生報表，專案外觀大致如下：

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

Customer Journey Analytics會檢視事件的這些部分，以產生報表：

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

由於烘衣機不附保固，因此未列入表格中。

有鑑於您可以結合任何維度與量度，下表提供未指定維度項目的資料狀態：

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

產品訂單沒有相關聯的保固名稱，因此維度項目為「未指定」。同樣的情況也適用於產品保固訂單：

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

請注意沒有關聯名稱的訂單。這些都是「未指定」維度項目的訂單。

### 結合不同量度

Customer Journey Analytics本身不會結合名稱相似但物件層級不同的量度。

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

不過，您可以建立計算量度，將所需的量度加以結合：

計算量度「總收入」：`[product : revenue] + [product : warranty : revenue]`

套用此計算量度會顯示所需的結果：

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## 限制

限制確實適用於Customer Journey Analytics所使用且模型化為Experience Platform中結構描述一部分的資料陣列。 檢視[即時客戶個人檔案資料和區段](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/profile/guardrails)預設護欄中的[資料模型限制](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/profile/guardrails#data-model-limits)和[資料大小限制](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/profile/guardrails#data-size-limits)。

