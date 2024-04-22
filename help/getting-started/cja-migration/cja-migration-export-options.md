---
title: 移轉至Customer Journey Analytics時取代資料摘要和Data Warehouse
description: 規劃從Adobe Analytics移轉至Customer Journey Analytics的程式
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# 步驟8：移轉至Customer Journey Analytics時取代資料摘要和Data Warehouse

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟8，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。 |
| **步驟4： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| <span class="preview">**步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。</span> |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |
| **步驟10： [執行移轉後工作](/help/getting-started/cja-getting-started.md)** | 完成移轉後，您需要執行各種工作，包括將其他資料匯入Experience Platform、建立Platform資料集與Customer Journey Analytics之間的連線、建立資料檢視，以及瞭解如何在Analysis Workspace中報告跨管道資料。 |

{style="table-layout:auto"}

+++

如果您目前使用Adobe Analytics中的資料摘要或Data Warehouse，請使用下表瞭解Customer Journey Analytics中可用的各種匯出選項：

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| 資料摘要 | 評估您的資料摘要使用案例，然後使用Customer Journey Analytics提供的任何替代匯出方法組合： <ul><li>若要匯出原始資料集， [將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets). &#x200B;</li><li>若要使用人員ID或時間戳記進行對象或事件層級匯出，請使用 [完整表格匯出](/help/analysis-workspace/export/export-cloud.md). &#x200B;</li><li>若要與Power BI和Tableau直接整合，請使用 [Customer Journey AnalyticsBI擴充功能](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension). &#x200B;</li><li>若要以SQL直接存取Adobe Experience Platform中的資料，請使用 [Adobe Experience Platform查詢服務](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | 變更要使用的Adobe AnalyticsData Warehouse匯出 [完整表格匯出](/help/analysis-workspace/export/export-cloud.md) 在Customer Journey Analytics中。<p>「Customer Journey Analytics完整表格匯出」是Adobe Analytics中Data Warehouse報表的發展成果，其中包含許多經常請求的新功能，目前在Data Warehouse中尚未提供。</p> |

{style="table-layout:auto"}

## 接下來，移轉專案和元件

使用Adobe Analytics中的元件移轉區域可以 [移轉專案及其相關元件](/help/getting-started/cja-migration/cja-migration-projects.md) 從Adobe Analytics到Customer Journey Analytics。
