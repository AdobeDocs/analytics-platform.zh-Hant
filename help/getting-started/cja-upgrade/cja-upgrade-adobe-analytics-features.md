---
title: 了解升級至 Customer Journey Analytics 時的 Adobe Analytics 功能支援
description: 了解關於升級至 Customer Journey Analytics 時的 Adobe Analytics 功能支援
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 100%

---

# 了解升級至 Customer Journey Analytics 時的 Adobe Analytics 功能支援 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="元件和專案"
>abstract="Adobe Analytics 的元件包括：專案 (及其相關的自由格式表格和視覺效果)、區段和計算量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map 覆蓋和連結追蹤"
>abstract="一種瀏覽器擴充功能，可讓您在網站上查看以覆蓋形式顯示的連結追蹤資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="尚未支援 Activity Map 覆蓋功能"
>abstract="Customer Journey Analytics 尚未支援 Activity Map 覆蓋功能。此功能預計將於未來推出。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="分類資料"
>abstract="將資料分組或分類為個別的維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="行銷管道"
>abstract="建立規則，將客戶造訪您網站的方式進行分類。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="資料摘要"
>abstract="從 Adobe Analytics 匯出原始資料以用於外部工具和流程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="以試算表格式從 Adobe Analytics 匯出已處理的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="串流媒體資料"
>abstract="Adobe Analytics 及 Customer Journey Analytics 的附加元件，專門用於媒體的資料收集，例如音訊、視訊或串流內容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="移轉專案和元件"
>abstract="將 Adobe Analytics 專案及其相關元件帶入 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下列表僅顯示升級至 Customer Journey Analytics 過程中需要考慮的 Adobe Analytics 功能。關於顯示哪些 Adobe Analytics 功能在 Customer Journey Analytics 中完全支援、部分支援或不支援的完整清單，請參閱「[Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)」。

當您升級到 Customer Journey Analytics 時，請考慮要繼續使用下列哪些 Adobe Analytics 功能：

| Adobe Analytics 功能 | Customer Journey Analytics 中的對應功能 |
|---------|----------|
| [Adobe Analytics 中的元件和專案](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [將專案及其相關元件移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map 覆蓋和連結追蹤](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/activity-map/overview) | 尚無法使用 |
| [分類資料](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/classifications/c-classifications) | 查閱資料集是為 Customer Journey Analytics 資料分類的方法。<p>[針對包含分類資料的每個維度建立查詢資料集。](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [行銷管道](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 衍生欄位是在資料檢視中建立。 <p>[建立行銷管道衍生的欄位。](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [資料摘要](https://experienceleague.adobe.com/zh-hant/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform 和 Customer Journey Analytics 提供許多功能，可以獨立或組合解決各種匯出需求。這些功能包括 [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=zh-Hant)、[Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hant)、[Customer Journey Analytics 完整表格匯出](/help/analysis-workspace/export/export-cloud.md)和 [BI 工具整合](/help/data-views/bi-extension.md)。<p>如需關於匯出選項的詳細資訊，請參閱[資料匯出使用案例](/help/use-cases/data-export/overview.md)。</p> |
| [Data Warehouse](https://experienceleague.adobe.com/zh-hant/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics 完整表格匯出](/help/analysis-workspace/export/export-cloud.md)是 Adobe Analytics 中 Data Warehouse 報告的演化，其中包含許多使用者經常要求且目前 Data Warehouse 目前尚未提供的新功能。 |
| [串流媒體資料](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-overview) | 串流媒體資料可使用 Analytics 來源連接器當作工作區中的「媒體同時檢視者」面板和「媒體播放時間」面板的一部分提供。 |
