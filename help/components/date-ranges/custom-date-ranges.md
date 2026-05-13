---
description: 了解如何在 Analysis Workspace 中定義自訂日期範圍。
keywords: Analysis Workspace
title: 自訂日期範圍的範例
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
TQID: https://experienceleague.adobe.com/UqM7kI1AJmseZkWgH4cl5gTRgBhhORkAaPZWrf8WpOc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 100%

---

# 自訂日期範圍的範例

本文章顯示更多自訂日期範圍的範例。

## 兩個月前

+++ 詳細資料

您想要使用一個自訂日期範圍來定義前兩個月。 您使用其中一個預設集。

![過去的前兩個月](assets/date-range-example-simple.png)

+++


## 滾動計算至上週結束

+++ 詳細資料

您想要使用一個日期範圍，定義從一週前的今天，直到那一週結束之間的時段。 例如，若現在是 2024 年 9 月 11 日星期三。 您想要的日期範圍是從 2024 年 9 月 4 日星期三，直到 2024 年 9 月 7 日星期六。

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