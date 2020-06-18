---
title: 使用物件陣列
description: 瞭解CJA如何報告資料階層。
translation-type: tm+mt
source-git-commit: 52fecf03cc503fa59101f6280c671e153e2129e9
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# 使用物件陣列

某些平台架構可以有對象陣列。 最常見的例子之一是包含多種產品的購物車。 每個產品都有名稱、SKU、類別、價格、數量，以及您要追蹤的任何其他維度。 所有這些面都有不同的需求，但必須都符合相同的點擊。

在舊版Adobe Analytics中，此功能是使用變數 `products` 完成。 它是以分號(`;`)分隔的串連字串，以區隔產品的刻面，而逗號(`,`)則劃分產品。 它是唯一對「物件陣列」支援有限的變數。 清單變數等多值變數可支援等同的陣列，但無法支援「物件陣列」。 CJA擴充了此概念，在單一資料列中支援任意深度的階層，這是任何舊版Adobe Analytics都無法使用的功能。

## 相同點擊範例

以下點擊是JSON物件，代表客戶購買洗衣機和烘乾機。

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

建立資料檢視時，可使用下列維度和量度（根據結構）:

* **維度:**
   * ID
   * 產品： SKU
   * 產品： 名稱
   * 產品： order_id
   * 產品： 保修： 覆蓋率
   * prodcut: 保修： 長度
   * 產品： 保修： 名稱
   * 產品： 保修： type
* **量度:**
   * 產品： 訂單
   * 產品： 單位
   * 產品： 收入
   * 產品： 保修
   * 產品： 保修： 收入

### 相同的點擊範例（報告行為）

僅使用上述點擊，下表顯示具有某些維度和量度組合的「工作區」報表。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA會根據表格選擇性地查看物件的維度和量度。

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

如果您只想報告保修收入，則您的項目外觀將類似於：

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA會查看點擊的這些部分，以產生報表：

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

由於乾燥器不包括保修，因此不包括在桌子中。

由於您可以將任何維度與任何度量結合，下表顯示資料與未指定維度值的方式：

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

產品訂單不存在與其關聯的擔保名稱，因此維度值屬於「未指定」。 同樣的情況也適用於產品保修訂單：

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

請注意沒有與訂單相關名稱的訂單。 這些是屬於「未指定」維值的訂單。

### 結合量度

如果CJA位於不同的物件層級，則CJA本身不會結合具有類似命名的量度。

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

不過，您可以建立結合所需度量的計算度量：

計算量度「總收入」: `[product : revenue] + [product : warranty : revenue]`

套用此計算量度會顯示所需的結果：

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |

## 永續性範例

