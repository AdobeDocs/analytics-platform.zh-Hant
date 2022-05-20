---
title: 將 Marketo Engage 資料擷取至 AEP 和 CJA 報告
description: 了解如何將 Marketo Engage 資料帶入 CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: ad8e3c18dbb73a064662a4543cb0e553cd52cec3
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# 將 Marketo Engage 資料擷取至 AEP 和 CJA 報告

您可以利用 Adob&#x200B;&#x200B;e Experience Platform (AEP) 中新推出的 Marketo Engage 資料集，為 B2B 行銷人員提供有價值的分析和報告解決方案。然後在 Customer Journey Analytics  (CJA) 中報告這些資料集。

## 步驟 1：將 Marketo 來源資料欄位對應至它們的 XDM 目標。

將[人員](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=tw#persons)和[活動](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=tw#activities)物件對應至它們各自的 XDM 結構描述目標欄位。

## 步驟 2：將 Marketo 資料擷取至 AEP

使用 [Marketo Engage 連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=tw)將資料從 Marketo 帶到 Experience Platform，並使用平台連線的應用程式保持這些資料在最新狀態。

## 步驟 3：在 CJA 中設定此資料集的連線

若要針對 Experience Platform 資料集製作報表，必須先為 Experience Platform 和 CJA 中的資料集建立連線。在[建立連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=tw)項下可找到更多資訊。

## 步驟 4：建立一個或多個資料檢視

[資料檢視](/help/data-views/data-views.md)是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。它會指定 Analysis Workspace 中可用的所有維度和量度 (在此案例中則是 Marketo 特定的量度和維度)。它會這些維度和量度從哪些欄取得資料。資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

## 步驟 5：Analysis Workspace 中的報表

您可能會探索的一個使用案例是：我們在 2020 年 4 月至 6 月期間有多少潛在客戶的網頁瀏覽次數？

1. 請開啟 [Analytics Workspace](/help/analysis-workspace/home.md) 並建立新專案。擁有 B2B/B2P CDP 的客戶可以在 CJA 中進行 B2C 樣式的分析。尚未提供 B2B 物件。

1. 依下列方式建立網頁頁面檢視的[篩選器](/help/components/filters/create-filters.md) - 事件類型 = web.webpagedetails.pageViews：

   ![](assets/marketo-filter.png)

1. 進入 Freeform 表格中，提取您建立的篩選器 - 網頁頁面檢視，然後提取「月份」日期範圍。這會為您提供每個月潛在客戶的網頁瀏覽次數：

   ![](assets/marketo-freeform.png)

1. 或提取以下維度：人員金鑰或工作電子郵件地址。這會為您提供每個潛在客戶的網頁瀏覽次數：

   ![](assets/marketo-freeform2.png)
