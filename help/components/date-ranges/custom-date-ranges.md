---
description: 瞭解如何在Analysis Workspace中定義自訂日期範圍。
keywords: Analysis Workspace
title: 自訂日期範圍範例
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 28a657a0a93325a745dcf51c706cc488f599a6e0
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 3%

---

# 自訂日期範圍範例

本文顯示更多自訂日期範圍範例。

## 前兩個月

+++ 詳細資料

您要定義兩個月前定義的自訂日期範圍。 您使用其中一個預設集。

![過去2個月前](assets/date-range-example-simple.png)

+++


## 滾動至上週結束

+++ 詳細資料

您想要定義日期範圍，以定義一週前當天，直到上週同一天結束之間的期間。 例如，如果今天是2024年9月11日星期三。 您想要從2024年9月4日星期三到2024年9月7日星期六的日期範圍。

![日期範圍範例](assets/date-range-example.png)

+++

<!--
## Example: Use a 7-day rolling date range

You can create a date range that specifies a 7-day rolling window that ends one week ago:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* The Start settings would be *`current day minus 6 days`*.

* The End settings would be *`current day minus 7 days`*.

This date range can be a component that you drag onto any freeform table.
-->