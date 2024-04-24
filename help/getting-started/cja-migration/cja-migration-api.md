---
title: 移轉至Customer Journey Analytics時移植報表API使用量
description: 瞭解如何將API使用方式從Adobe Analytics移轉到Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 步驟7：移轉至Customer Journey Analytics時移植報表API使用量

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟7，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉路徑](/help/getting-started/cja-migration/cja-migration-path.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的移轉路徑而有所不同。 |
| **步驟4： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟5： [執行其他實作工作](/help/getting-started/cja-getting-started.md)** | 在移轉程式中的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種工作。<p>這些額外的工作適用於從Adobe Analytics的移轉以及新的Customer Journey Analytics實作。</p><p>這些工作包括：</p><ul><li>將其他資料帶入Experience Platform</li><li>在Platform資料集和Customer Journey Analytics之間建立連線</li><li>建立資料檢視</li><li>移植報表API使用量</li><li>資料摘要和Data Warehouse的帳戶處理</li><li>移轉專案和元件</li><li>Planning使用者上線</li></ul> <p>如需詳細資訊，請參閱 [Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。

Customer Journey Analytics報表API的格式相同，但使用不同的子網域。

請參閱Adobe Analytics和Customer Journey Analytics的端點指南。

大部分的API呼叫都可以輕鬆地從Adobe Analytics轉譯為Customer Journey Analytics。

將Customer Journey Analytics API新增至其API專案。

將IMS組織ID新增到其API呼叫的標題中。

cja.adobe.io與analytics.adobe.io

其他標頭

## 接下來，取代資料摘要並Data Warehouse

決定如何使用Customer Journey Analytics中可用的匯出選項，以便 [取代資料摘要和Data Warehouse功能](/help/getting-started/cja-migration/cja-migration-export-options.md) 您在Adobe Analytics中使用。
