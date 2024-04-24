---
title: 將專案和元件移轉至Customer Journey Analytics
description: 瞭解將專案和元件移轉至Customer Journey Analytics的元件移轉。
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 11%

---

# 步驟9：將專案和元件移轉至Customer Journey Analytics

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟9，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉路徑](/help/getting-started/cja-migration/cja-migration-path.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分移轉路徑都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟4： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的移轉路徑而有所不同。 |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| <span class="preview">**步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。</span> |
| **步驟10： [執行移轉後工作](/help/getting-started/cja-getting-started.md)** | 完成移轉後，您需要執行各種工作，包括將其他資料匯入Experience Platform、建立Platform資料集與Customer Journey Analytics之間的連線、建立資料檢視，以及瞭解如何在Analysis Workspace中報告跨管道資料。 |

{style="table-layout:auto"}

+++

Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。

移轉過程包括：

* 在 Customer Journey Analytics 中重新建立 Adobe Analytics 專案。

* 將 Adobe Analytics 報表套件中的維度和指標對應到 Customer Journey Analytics 資料視圖中的維度和指標。

在開始移轉之前，首先[準備將元件和專案從 Adobe Analytics 移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)。

完成所有必要的準備工作後，您可以[將元件和專案從 Adobe Analytics 移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)。

## 接下來，執行移轉後的工作

在您之後 [將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)，您必須執行各種工作才能完成Customer Journey Analytics環境的設定。 這些工作包括將其他資料匯入Experience Platform、建立Platform資料集與Customer Journey Analytics之間的連線、建立資料檢視，以及瞭解如何在Analysis Workspace中報告跨管道資料。

若要深入瞭解這些移轉工作，請參閱 [Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md).
