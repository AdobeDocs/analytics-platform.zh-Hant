---
title: 升級至Customer Journey Analytics時保留歷史資料
description: 瞭解在升級至Customer Journey Analytics時如何保留歷史資料
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 97d48d88af969705f2664781e7a972f20c1b4239
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# 步驟4：升級時保留歷史資料

+++展開本節，瞭解此頁面上的資訊在大型升級程式中的適用位置。 請確定所有先前的升級步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的升級工作。

本頁資訊涵蓋升級程式的步驟4，如下表所示：

| 升級任務 | 詳細資料 |
|---------|----------|
| **步驟1：[開始升級](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 瞭解升級至Customer Journey Analytics的好處和基本升級程式。 |
| **步驟2：[選擇升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 升級至Customer Journey Analytics有多種方法可供使用。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3：[傳送資料至Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的升級路徑而有所不同。 |
| <span class="preview">**步驟4：保留歷史資料**</span> | <span class="preview">大多陣列織都需要保留其歷史Adobe Analytics資料一段時間。 有各種選項可完成此作業。</span> |
| **步驟5：[執行其他實作工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種工作。<p>這些額外工作適用於Adobe Analytics的升級以及新的Customer Journey Analytics實作。</p><p>這些工作包括：</p><ul><li>將其他資料帶入Experience Platform</li><li>在Platform資料集和Customer Journey Analytics之間建立連線</li><li>建立資料檢視</li><li>移植報表API使用量</li><li>資料摘要和Data Warehouse的會計處理</li><li>移轉專案和元件</li><li>Planning使用者上線</li></ul> <p>如需詳細資訊，請參閱[Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

選擇下列其中一個選項，以便在從Adobe Analytics移至Customer Journey Analytics時保留歷史資料：

>[!IMPORTANT]
>
>選擇如何保留歷史資料時，請聯絡您的Adobe客戶代表以決定價格。

## 使用Analytics來源聯結器

您可以使用[Analytics來源聯結器](/help/data-ingestion/analytics.md)來保留歷史資料。 無論您選擇哪種升級路徑(即使您使用Web SDK升級)，都可使用Analytics來源聯結器保留Adobe Analytics環境的歷史資料。

您可以使用Analytics來源聯結器將歷史資料引進其專屬位置（與您目前的資料分開），以保留歷史資料。

只要您需要存取歷史資料，Analytics來源聯結器就能繼續運作。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 維護您現有的Adobe Analytics實作

您可以針對特定時間範圍（例如1年）維護現有Adobe Analytics實作與新的Customer Journey Analytics實作。 選擇此選項時，請考量下列事項：

* 資料在Experience Platform中無法使用。

* 您應規劃在Customer Journey Analytics中有足夠資料後停用Adobe Analytics實作。

## 接下來，執行其他實作工作

在升級流程的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種實作工作。

這些額外工作適用於Adobe Analytics的升級以及新的Customer Journey Analytics實作。

這些工作包括：

* 將其他資料帶入Experience Platform

* 在Platform資料集和Customer Journey Analytics之間建立連線

* 建立資料檢視

* 移植報表API使用量

* 資料摘要和Data Warehouse使用案例的會計處理

* 移轉專案和元件

* Planning使用者上線

如需詳細資訊，請從[Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md)中的步驟2開始。
