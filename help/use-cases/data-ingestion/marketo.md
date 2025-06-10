---
title: 報告Marketo Engage資料
description: 瞭解如何在Customer Journey Analytics中報告Marketo Engage資料
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 51%

---

# 報告Marketo Engage資料

您可以善用Adobe Experience Platform (Adobe Experience Platform)中新推出的Marketo Engage資料集，為B2B行銷人員提供有價值的分析和報告解決方案。 然後在Adobe Customer Journey Analytics中報告這些資料集。

## 步驟 1：將 Marketo 來源資料欄位對應至它們的 XDM 目標。

將[人員](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#persons)和[活動](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#activities)物件對應至它們各自的 XDM 結構描述目標欄位。

## 步驟2：將Marketo資料擷取至Adobe Experience Platform

使用 [Marketo Engage 連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html)將資料從 Marketo 帶到 Experience Platform，並使用平台連線的應用程式保持這些資料在最新狀態。

## 步驟3：在Customer Journey Analytics中設定此資料集的連線

若要針對Experience Platform資料集製作報表，必須先為Experience Platform和Customer Journey Analytics中的資料集建立連線。 請參閱以取得詳細資訊[建立或編輯連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant)。

## 步驟 4：建立一個或多個資料檢視

[資料檢視](/help/data-views/data-views.md)是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。它會指定 Analysis Workspace 中可用的所有維度和量度 (在此案例中則是 Marketo 特定的量度和維度)。它會這些維度和量度從哪些欄取得資料。資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

## 步驟 5：Analysis Workspace 中的報表

您可能會探索的一個使用案例是：我們在 2020 年 4 月至 6 月期間有多少潛在客戶的網頁瀏覽次數？

1. 請開啟 [Analytics Workspace](/help/analysis-workspace/home.md) 並建立新專案。擁有B2B/B2P CDP的客戶可以在Customer Journey Analytics中進行B2C樣式的分析。 尚未提供 B2B 物件。

1. 為網頁檢視建立[區段](/help/components/segments/seg-create.md)，如下所示：事件型別= web.webpagedetails.pageViews：

   顯示事件和事件型別的![定義視窗](../assets/marketo-filter.png)

1. 將您建立的區段提取至「自由表格 — 網頁檢視次數」中，然後提取「月份」日期範圍。 這會為您提供每個月潛在客戶的網頁瀏覽次數：

   ![自由表格，依月份顯示事件。](../assets/marketo-freeform.png)

1. 或提取以下維度：人員金鑰或工作電子郵件地址。這會為您提供每個潛在客戶的網頁瀏覽次數：

   ![顯示事件和workEmail.Address及網頁檢視的自由格式表格。](../assets/marketo-freeform2.png)
