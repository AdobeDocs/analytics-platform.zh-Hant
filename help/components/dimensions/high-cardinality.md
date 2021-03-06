---
title: Customer Journey Analytics 中基數非常高的維度
description: 描述在 Customer Journey Analytics 中處理高基數維度的最佳做法
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
source-git-commit: 0e9d612e1c0f6d64cd6f1e045c1049a1f8202b72
workflow-type: ht
source-wordcount: '455'
ht-degree: 100%

---

# 基數很高的維度

Customer Journey Analytics (CJA) 不會限制在單一維度中可以報告的唯一值或維度項目數量。 但在某些情況下，具有極大量唯一項目的維度 (也稱為高基數維度) 可能會影響可以報告的內容。

## 限制

根據特定 CJA 連線中的事件數量，可能會出現與高基數維度有關的以下兩項限制：

### 1. 可能無法準確報告列計數

可能無法準確報告高基數維度的列計數。 如果發生這個狀況，自由表格將會提供指示，如下所示：

![](assets/high-cardinality.png)

### 2. 計算量度可針對某些函數和排序順序使用預估值

搭配高基數維度使用時，某些計算量度函數可能會傳回預估值，包括欄最大值、欄最小值、列計數、平均值、中位數、百分位數、四分位數、標準差、變異數、回歸函數以及 T 和 Z 函數。

此外，使用計算量度排序表格欄位可能會根據預估值，而且可能不會始終都反映準確的排序順序。 系統將會顯示警告訊息，提醒您已使用預估值。

請注意，雖然計算量度有時可能會傳回預估值，但是欄總計總是正確的，而且絕對不會根據預估值。 同樣地，當使用標準量度時，絕對不會使用預估值，而且總是會反映準確的排序順序。

### 在考量所有維度值時

雖然某些計算量度和維度的列計數存在著限制，但是請注意，以下功能永遠都會考量任何維度中的所有唯一值，無論維度是否為高基數：

* 量度歸因和維度配置
* 已套用到自由表格的條列項目搜尋
* 使用維度或維度項目的篩選
* 計算量度中近似計數的不同函數
* 已在資料檢視中套用到任何量度或維度的包含/排除邏輯
* 已新增到連線的查詢資料集

## 使用高基數維度的最佳做法

若要免除在使用高基數維度時可能發生的警告或預估值狀況，我們建議您使用以下其中一個方法來減少報告中所考量的列數：

* 為受影響的欄或面板新增篩選。
* 在自由表格中套用搜尋。
* 對感興趣的列套用劃分，或使用高基數維度當做劃分維度。
* 在維度的資料檢視設定中新增包含/排除條件，以減少存在於維度中的唯一值數量。

使用這些技巧通常就可以免除在使用高基數維度時所遇到的任何不想要的預估值或警告。
