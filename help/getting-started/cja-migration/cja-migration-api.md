---
title: 移轉至Customer Journey Analytics時移植報表API使用量
description: 瞭解如何將API使用方式從Adobe Analytics移轉到Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 0%

---

# 步驟7：移轉至Customer Journey Analytics時移植報表API使用量

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟7，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。 |
| **步驟4： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| <span class="preview">**步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)**</span> | <span class="preview">Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。</span> |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |
| **步驟10： [執行移轉後工作](/help/getting-started/cja-getting-started.md)** | 完成移轉後，您需要執行各種工作，包括將其他資料匯入Experience Platform、建立Platform資料集與Customer Journey Analytics之間的連線、建立資料檢視，以及瞭解如何在Analysis Workspace中報告跨管道資料。 |

{style="table-layout:auto"}

+++

將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。

Customer Journey Analytics報表API採用相同格式，但使用不同的端點。

## 接下來，取代資料摘要並Data Warehouse

決定如何使用Customer Journey Analytics中可用的匯出選項，以便 [取代資料摘要和Data Warehouse功能](/help/getting-started/cja-migration/cja-migration-export-options.md) 您在Adobe Analytics中使用。
