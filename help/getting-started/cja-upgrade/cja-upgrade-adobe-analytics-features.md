---
title: 瞭解升級至Customer Journey Analytics時的Adobe Analytics功能支援
description: 瞭解升級至Customer Journey Analytics時的Adobe Analytics功能支援
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1460cbd05cce793b25d026c413744508ab951147
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 29%

---

# 瞭解升級至Customer Journey Analytics時的Adobe Analytics功能支援 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="元件和專案"
>abstract="Adobe Analytics的元件包括：專案（及其相關自由表格和視覺效果）、區段和計算量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map覆蓋和連結追蹤"
>abstract="瀏覽器擴充功能可讓您在網站上以覆蓋圖的形式檢視連結追蹤資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="分類資料"
>abstract="以個別維度將資料分組或分類。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="行銷管道"
>abstract="建立分類客戶如何到達您網站的規則。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="資料摘要"
>abstract="從Adobe Analytics匯出原始資料，以用於外部工具和程式。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="以試算表格式從Adobe Analytics匯出處理的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="串流媒體資料"
>abstract="Adobe Analytics的附加元件，專門處理媒體的資料收集，例如音訊、視訊或串流內容。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中的問題時，使用此頁面上的資訊。

下列清單僅顯示[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中包含的功能。 如需顯示Customer Journey Analytics支援、部分支援或不支援哪些Adobe Analytics功能的完整清單，請參閱[Customer Journey Analytics功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。

升級至Customer Journey Analytics時，請考慮下列哪項Adobe Analytics功能要繼續使用：

| Adobe Analytics功能 | Customer Journey Analytics中的對應功能 |
|---------|----------|
| 來自Adobe Analytics的[元件和專案](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [將專案及其相關元件移轉至Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map覆蓋和連結追蹤](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | 尚未提供 |
| [分類資料](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | 查詢資料集是將資料分類Customer Journey Analytics的方法。<p>[為每個包含分類資料的維度建立查詢資料集。](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [行銷管道](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 衍生欄位會在資料檢視中建立。 <p>[建立行銷管道衍生欄位。](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [資料摘要](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | 可透過 [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html) 和 [Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html) 匯出資料集的第一代資料。這些選項提供收集或擷取至 Experience Platform Data Lake 中的所有資料事件/列層級匯出。後處理資料欄無法使用，因為後處理欄是在查詢時計算的。可透過報告匯出發佈欄。 |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics 完整表格匯出](/help/analysis-workspace/export/export-cloud.md)是 Adobe Analytics 中 Data Warehouse 報告的演化，其中包含許多使用者經常要求且目前 Data Warehouse 目前尚未提供的新功能。 |
| [串流媒體資料](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-overview) | 串流媒體資料可使用 Analytics 來源連接器當作工作區中的「媒體同時檢視者」面板和「媒體播放時間」面板的一部分提供。 |

