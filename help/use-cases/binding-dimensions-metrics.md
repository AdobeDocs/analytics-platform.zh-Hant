---
title: 在CJA中使用綁定維和度量
description: 屬性維到對象陣列以用於複雜持久性分析。
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 38c10e395b816d812d30f0698dc821ee0ea5c9b1
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 1%

---

# 在CJA中使用綁定維和度量

Customer Journey Analytics提供了多種方法來保留維值，使其超出設定的命中值。 Adobe提供的持久性方法之一稱為Binding。 在以前的Adobe Analytics版本中，這個概念被稱為商品銷售。

雖然可以將綁定維與頂級事件資料一起使用，但在使用時最好使用此概念 [對象陣列](object-arrays.md)。 您可以將維屬性化到對象陣列的一部分，而不將其應用於給定事件中的所有屬性。 例如，您可以將搜索項屬性為購物車對象陣列中的一個產品，而不將該搜索項綁定到整個事件。

## 示例1:使用綁定維將附加產品屬性屬性屬性附加到採購

可以將對象陣列中的維項綁定到另一個維。 當綁定維項出現時，CJA將回調綁定維並將其包括在事件中。 請考慮以下客戶行程：

1. 訪問者在洗衣機上查看產品頁面。

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. 然後，訪問者在烘乾機上查看產品頁面。

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. 最終，他們買了。 購買事件中未包括每個產品的顏色。

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

如果要按顏色查看沒有綁定維的收入，則維 `product.color` 持續並錯誤地將原因歸於乾燥器的顏色：

| product.color | 收入 |
| --- | --- |
| 橙色 | 二零九九 |

您可以進入「資料視圖管理器」，並將產品顏色綁定到產品名稱：

![綁定維](assets/binding-dimension.png)

設定此持久性模型時，每當設定產品顏色時，Adobe都會注意產品名稱。 如果在此訪問者的後續事件中識別出相同的產品名稱，則產品顏色也會隨之改變。 將產品顏色綁定到產品名稱時的相同資料與以下內容類似：

| product.color | 收入 |
| --- | --- |
| 白色 | 1600 |
| 橙色 | 499 |

## 示例2:使用綁定度量將搜索術語與產品採購關聯

在Adobe Analytics，最常見的促銷方法之一是將搜索詞綁定到產品上，這樣每個搜索詞都能獲得對其合適產品的認可。 請考慮以下客戶行程：

1. 有訪客來到您的網站，搜索「拳擊手套」。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. 他們找到一雙他們喜歡的手套，然後把它添加到他們的手推車上。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. 然後，參觀者搜索「網球拍」。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. 他們找到自己喜歡的球拍，然後把它加到手推車上。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. 訪客第三次搜索「鞋」。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 他們找到一雙他們喜歡的鞋，然後把它加到他們的手推車上。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 參觀者通過結帳過程購買這三件物品。

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

如果使用帶搜索項的傳統分配模型，則所有三種產品都只將收入歸為單個搜索項。 例如，如果您將第一個分配與搜索術語維一起使用：

| 搜索項 | 收入 |
| --- | --- |
| 拳擊手套 | US$204.97 |

如果您將上次分配與搜索術語維一起使用，則所有三種產品仍將收入分配給單個搜索術語：

| 搜索項 | 收入 |
| --- | --- |
| shoes | US$204.97 |

雖然此示例僅包括一名訪問者，但許多搜索不同內容的訪問者可能會將搜索詞錯誤地分配給不同的產品，因此很難確定最佳搜索結果到底是什麼。

使用綁定維，Adobe會記下它綁定到的維項。 當在後續事件中看到相同的綁定值時，它會將維項帶來，以便您可以將所需度量屬性化到該維項。 在本示例中，我們可以將search_term的綁定維設定為product name。 在資料視圖管理器中設定此維時，還需要設定綁定度量，因為綁定維在對象陣列中。 綁定度量用作綁定維的觸發器，因此它僅在存在綁定度量的事件上綁定自己。 在此示例實現中，搜索結果頁始終包括搜索項維和搜索度量。 只要存在「搜索」(Searches)度量，我們就可以將搜索項綁定到產品名稱。

![綁定度量](assets/binding-metric.png)

將搜索項維設定為此持久性模型執行以下邏輯：

* 當search_term在事件中時，檢查是否存在產品名稱。
* 如果產品名稱不在，則不執行任何操作。
* 如果產品名稱在，請檢查是否存在「搜索」度量。
* 如果「搜索」度量不存在，則不執行任何操作。
* 如果存在「搜索」度量，請將搜索項綁定到所有產品名稱。 它就像它在與該事件的產品名稱相同的級別上一樣。 在本示例中，它被視為product.search_term。
* 如果在後續事件中看到相同的產品名稱，則綁定的搜索詞也存在。

在Analysis Workspace，所得報告與下列報告相似：

| 搜索項 | 收入 |
| --- | --- |
| 拳擊手套 | US$89.99 |
| 網球拍 | US$34.99 |
| 鞋 | US$79.99 |
