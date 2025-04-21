---
title: 升級到 Customer Journey Analytics 時保留歷史資料
description: 了解如何在升級到 Customer Journey Analytics 時保留歷史資料
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 73%

---

# 步驟 4：升級時保留歷史數據

+++ 展開此部分，查看此頁面資訊在更大規模升級程序中的位置。確保所有先前的升級步驟都已完成。

在繼續此部分之前，請先確保您已完成所有先前的升級工作。

本頁資訊涵蓋升級程序的步驟 4，重點如下表所示：

| 升級工作 | 詳細資料 |
|---------|----------|
| **步驟 1：[開始進行升級](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升級到 Customer Journey Analytics 的好處和基本升級流程。 |
| **步驟 2：[選擇升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多種方法可以升級到 Customer Journey Analytics。根據您組織目前的 Adob&#x200B;&#x200B;e Analytics 環境和長期目標，選擇最適合您組織的方法。 |
| **步驟 3： [將資料發送至 Adob&#x200B;&#x200B;e Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 將資料發送送至 Adob&#x200B;&#x200B;e Experience Platform 的流程會因您在步驟 2 選擇的升級路徑而不同。 |
| <span class="preview">**步驟 4：保留歷史資料**</span> | <span class="preview">大多數組織需要保留其歷史 Adob&#x200B;&#x200B;e Analytics 資料達一段時間。有多種選項可以達到此目的。</span> |
| **步驟 5： [執行額外的實施工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段中，您需要執行各類工作後，您的 Customer Journey Analytics 環境才可供使用。<p>這些額外工作適用於 Adob&#x200B;&#x200B;e Analytics 的升級以及新的 Customer Journey Analytics 實施。</p><p>這些工作包括：</p><ul><li>將其他資料引入 Experience Platform</li><li>建立 Platform 資料集和 Customer Journey Analytics 之間的連線</li><li>建立資料檢視</li><li>轉移報告 API 用法</li><li>考量資料摘要和 Data Warehouse</li><li>移轉專案和元件</li><li>規劃使用者上線</li></ul> <p>如需更多資訊，請參閱「[Customer Journey Analytics 快速入門手冊](/help/getting-started/cja-getting-started.md)」。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>本頁資訊已取代為下列更完整的升級資訊： <ul><li>**建議的升級步驟**<p>如需詳細資訊，請參閱[從Adobe Analytics升級為Customer Journey Analytics時的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics升級指南**<p>有新的升級指南可供使用，動態產生針對貴組織和獨特環境量身打造的升級步驟。</p><p>若要從Customer Journey Analytics存取指南，請選取&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後在左側面板中選取&#x200B;**[!UICONTROL 升級至Customer Journey Analytics]**。 請依照熒幕上的指示操作。</p></li></ul>

從 Adob&#x200B;&#x200B;e Analytics 移至 Customer Journey Analytics 時，選擇以下選項之一來保留歷史資料：

>[!IMPORTANT]
>
>選擇如何保留歷史資料時，請聯絡您的 Adob&#x200B;&#x200B;e 客戶代表以確定價格。

## 使用Analytics來源聯結器

您可以使用[Analytics來源聯結器](/help/data-ingestion/analytics.md)來保留歷史資料。 無論您選擇哪種升級路徑(即使您使用Web SDK升級)，都可使用Analytics來源聯結器保留Adobe Analytics環境的歷史資料。

您可以使用Analytics來源聯結器將歷史資料引進其專屬位置（與您目前的資料分開），以保留歷史資料。

只要您需要存取歷史資料，Analytics來源聯結器就能繼續運作。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 維持您現有的 Adobe Analytics 實施。

您可以在特定時間範圍內 (例如 1 年) 維持您現有的 Adob&#x200B;&#x200B;e Analytics 實施以及新的 Customer Journey Analytics 實施。選擇此選項時，請考慮以下事項：

* Experience Platform 無法使用資料。

* 在 Customer Journey Analytics 中擁有足夠的資料後，您應該計劃停止使用 Adob&#x200B;&#x200B;e Analytics 實施。

## 接下來，執行額外的實施工作

在升級流程的這個階段中，您需要執行各類實施工作後，您的 Customer Journey Analytics 環境才可供使用。

這些額外工作適用於 Adob&#x200B;&#x200B;e Analytics 的升級以及新的 Customer Journey Analytics 實施。

這些工作包括：

* 將其他資料引入 Experience Platform

* 建立 Platform 資料集和 Customer Journey Analytics 之間的連線

* 建立資料檢視

* 轉移報告 API 用法

* 考慮資料摘要和 DataWarehouse 使用案例

* 移轉專案和元件

* 規劃使用者上線

如需了解更多資訊，請從 [Customer Journey Analytics 開始使用](/help/getting-started/cja-getting-started.md)中的步驟 2 開始。
