---
description: 了解如何在 Analysis Workspace 中定義自訂日期範圍。
keywords: Analysis Workspace
title: 自訂日期範圍的範例
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 28a657a0a93325a745dcf51c706cc488f599a6e0
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%

---

# 自訂日期範圍的範例

本文章顯示更多自訂日期範圍的範例。

## 兩個月前

+++ 詳細內容

您想要使用一個自訂日期範圍來定義前兩個月。您使用其中一個預設集。

![過去的前兩個月](assets/date-range-example-simple.png)

+++


## 滾動計算至上週結束

+++ 詳細內容

您想要使用一個日期範圍，定義從一週前的今天，直到那一週結束之間的時段。例如，若現在是 2024 年 9 月 11 日星期三。您想要的日期範圍是從 2024 年 9 月 4 日星期三，直到 2024 年 9 月 7 日星期六。

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