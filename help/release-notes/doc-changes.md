---
title: Customer Journey Analytics 文件更新
description: 列出 2019 年 12 月以來 Customer Journey Analytics 文件集的內容更新。
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 99%

---

# Customer Journey Analytics - 文件更新

從開始建立 Customer Journey Analytics 文件以來，已對其完成以下更新。

## 2023

| 功能 | 說明 |
| --- | --- |
| **2023 年 7 月** |
| 內容感知工作階段 | 新增此資料檢視設定的主題。 [了解更多](/help/data-views/context-aware-sessions.md) |
| Adobe Product Analytics | Adobe Product Analytics 是一種與 Customer Journey Analytics 跨管道資料和深入見解進行互動的新方式。這些新功能使產品團隊能夠透過[引導式分析](/help/guided-analysis/overview.md)工作流程取得有關其產品體驗的自助資料和深入見解。 |
| 衍生欄位 | [衍生欄位](/help/data-views/derived-fields/derived-fields.md)可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。 |
| 已擴大對設定檔和查詢資料的查詢支援 | 提供功能，可將資料集新增為設定檔或查詢資料集內的欄位查詢。之前僅支援事件資料集。[了解更多](/help/connections/create-connection.md) |
| Report Builder 改良功能 | <ul><li>[從儲存格篩選多個資料區塊](/help/report-builder/select-data-view.md)</li><li>[顯示和隱藏行與欄標題](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=zh-Hant#build-the-data-block)</li></ul> |
| 體驗 Edge 地理位置查詢 | [Adobe Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant) 將加入地理位置查詢服務，為所有 Experience Edge 使用者提供統一的地理位置資料。 |
| **2023 年 6 月** | |
| 跨管道分析與彙整 | 因為預期即將進行的變更會啟用彙整並進一步釐清如何使用彙整來提升跨管道分析，我們編輯了與跨管道分析功能相關的文件，以便參照[跨管道分析](../use-cases/cross-channel/cross-channel.md)做為 Customer Journey Analytics 功能和使用案例，並參照[彙整](../stitching/overview.md)做為完成此目標的重要功能。 |
| PowerBI 和 Tableau 可存取 Customer Journey Analytics 資料檢視 | Customer Journey Analytics SQL 連接器可讓 SQL 存取您在 Customer Journey Analytics 中已定義的資料檢視。[了解更多](/help/data-views/sql-connector.md) |
| Adobe Journey Optimizer 資料檢視 | Customer Journey Analytics 管理員可以存取 Customer Journey Analytics 中一些額外的資料檢視，標題為「AJO 資料檢視 (沙箱名稱)」。[了解更多](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html)。 |
| 貨幣轉換 | 已更新[貨幣轉換](../data-views/component-settings/format.md#currency)支援的文件。 |
| 計算量度更新 | 已針對計算量度文件進行以下更新，使其與目前的 Customer Journey Analytics 功能維持一致： <ul><li>已更新 Customer Journey Analytics 中可用的[預設計算量度](/help/components/calc-metrics/default-calcmetrics.md)清單</li><li>已更新各種計算量度文章中的螢幕擷取畫面和程序 </li></ul> |
| **2023 年 5 月** | |
| 深度連結 (行動應用程式) 文件 | 可讓使用者傳送計分卡連結，這些連結會直接導向應用程式中的計分卡專案。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) |
| Report Builder 中關於「從儲存格中選取資料檢視」的文件 | 此功能可讓使用者從儲存格中選取資料區塊的資料檢視。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) |
| Analytics 儀表板應用程式 (行動應用程式) 更新首頁的文件 | 新更新的首頁可讓您在一個綜合計分卡清單中檢視所有計分卡。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) |
| 最佳化更新 | 已更新關於[最佳化 Customer Journey Analytics 效能](/help/admin/optimizing-performance.md)的文章 |
| Analysis Workspace 概觀 | 更新[Analysis Workspace 概觀](/help/analysis-workspace/home.md)以包含更多一般概觀資訊和相關內容的連結。 |
| 建立專案 | 建立新文章，其中詳細說明如何在 Analysis Workspace [建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)。 |
| 排序左側邊欄中的元件 | 已新增排序左側邊欄中元件清單的資訊。請參閱[元件概觀](/help/components/overview.md)中的「搜尋、篩選和排序元件清單」一節。 |
| 從自由格式表格中刪除包含動態維度的列 | 已新增如何使用 x 圖示快速刪除包含動態維度的特定列的資訊。請參閱[篩選和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的「從表格中快速排除特定列」一節。 |
| 在面板中新增視覺效果的按鈕 | 已在 Analysis Workspace 中每個面板底部新增有關新按鈕的資訊，讓您可快速新增視覺效果。請參閱[視覺效果概觀](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)中的「將視覺效果新增到面板」一節。 |
| 智慧標題文件 | 使用台詞視覺效果[自然語言摘要](/help/analysis-workspace/visualizations/intelligent-captions.md)來增強使用者的故事講述效果。 |
| 衍生欄位 | 已新增[衍生欄位](../data-views/derived-fields/derived-fields.md)功能的文章。 |
| **2023 年 4 月** |  |
| 關於使用篩選器做為維度的影片 | 更新關於使用篩選器做為維度的影片 <p>該影片連結自「[建立篩選器](/help/components/filters/create-filters.md)」頁面。</p> <p>以下是影片的直接連結：[在 Analysis Workspace 中使用篩選器做為維度](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html)。</p> |
| 篩選器文件 | 新增說明如何使用[篩選器產生器](/help/components/filters/filter-builder.md)的文章。 <p>簡化了[建立篩選器](/help/components/filters/create-filters.md)和[篩選器概觀](/help/components/filters/filters-overview.md)文件。</p> |
| 實驗面板文件更新 | 新增有關[解釋非隨機維度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html?lang=zh-Hant#non-randomized)的章節。 |
| 專案篩選器 (臨時和快速篩選器) | 已簡化關於專案篩選器的文件，並移除重複的資訊。建立臨時篩選器的步驟現在已經和[建立快速篩選器](/help/components/filters/quick-filters.md)的步驟相結合。 |
| **2023 年 3 月** | |
| 整合決策管理資料 | 已新增內容來說明如何[在 Customer Journey Analytics 中整合 Adobe Journey Optimizer 決策管理資料](/help/integrations/ajo-od.md)。 |
| 在行動計分卡中建立資料故事 | [資料故事](/help/mobile-app/create-scorecard.md#create-data-stories)是圍繞中心主題或量度建置的支援資料點、業務內容和相關量度的集合。 |
| 更新功能支援 | 已透過 Customer Journey Analytics 中提供、但在 AA 中無法使用或不支援的功能表來更新 [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。 |
| 預設計算量度 | 已新增說明 [Adobe 提供的預設計算量度](/help/components/calc-metrics/default-calcmetrics.md)的內容。 |
| 資料字典 | <p>為資料字典新增了新文件，包括[概觀](/help/components/data-dictionary/data-dictionary-overview.md)、[檢視](/help/components/data-dictionary/view-data-dictionary.md)、[編輯 ](/help/components/data-dictionary/edit-entries-data-dictionary.md)，以及[監視](/help/components/data-dictionary/monitor-data-dictionary-health.md)資料字典。</p><p>已更新[新增元件說明](/help/components/add-component-descriptions.md)中的資訊，以說明資料字典功能。</p> |
| 專案連結共用 (不需登入) | <p>已更新現有文件，說明如何與無權存取 Analysis Workspace 的人員共用專案的唯讀連結。</p> <p>已更新使用者文件，包括[共用專案](/help/analysis-workspace/curate-share/share-projects.md)和[建立可共用連結](/help/analysis-workspace/curate-share/shareable-links.md)。</p> <p>已將管理員選項新增至[偏好設定](/help/analysis-workspace/user-preferences.md)。</p> |
| **2023 年 2 月** | |
| 比較 Customer Journey Analytics 和 BI 解決方案 | Customer Journey Analytics 與典型 BI 解決方案[比較](../getting-started/cja-vs-bi.md)的新文件。 |
| 更新至 Audiences 文件 | 有關[延遲的注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=zh-Hant#latency)的新章節。 |
| Audiences 文件的更新 | 建立對象之後，Adobe 會[為每個新的 Customer Journey Analytics 對象建立一個 Experience Platform 串流分段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=zh-Hant#after-audience-created)。 |
| Workspace 行事曆和日期範圍 | 更新內容以說明相對日期範圍、公式計算更新和行事曆 UI 變更。查看[關於相對面板日期範圍](/help/components/date-ranges/calendar.md#relative-panel-dates)。 |
| Mobile 計分卡 | 新文件部分會說明如何顯示和隱藏比較日期範圍。請參閱 Customer Journey Analytics 中的「[顯示比較日期範圍](/help/mobile-app/create-scorecard.md#show-comparison-dates)」。 |
| **2023 年 1 月** | |
| 篩選和排序表格 | 已更新[篩選和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的內容 (包括新增過程和說明可用選項)。重新命名本文的「分頁、篩選和排序表格」。 |
| 資料擷取快速入門指南 | 新增有關如何在 Customer Journey Analytics 中[擷取和使用資料](/help/data-ingestion/data-ingestion.md)的文件內容。 |
| 工作區資料夾 | [資料夾管理](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)的專用頁面。 |
| 工作區使用者偏好設定 | [偏好設定](/help/analysis-workspace/user-preferences.md)現在提供許多其他使用者偏好設定。 |
| 自動儲存工作區專案 | 已更新內容，在[儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)中加入自動儲存功能。 |
| 登陸頁面 | 新的登陸頁面更新[登陸頁面](/help/getting-started/landing.md)。 |
| 排程活頁簿 | 說明如何在 Report Builder 中[排程活頁簿](/help/report-builder/schedule-reportbuilder.md)的專用頁面。 |
| 針對設定檔及查閱資料集提供物件陣列支援 | 已更新[使用物件陣列](/help/use-cases/object-arrays.md)和[擷取 Adobe Experience Platform 對象](/help/use-cases/data-ingestion/ingest-aep-segments.md)，以反映針對設定檔及查閱資料集的物件陣列支援。 |

## 2022

| 日期 | 更新說明 |
| --- | --- |
| **2022 年 12 月** |  |
| 2022 年 12 月 16 日 | 新增有關[測量及管理 Customer Journey Analytics 資料使用情況](/help/admin/estimate-usage.md)的主題。 |
| **2022 年 10 月** | |
| 2022 年 10 月 | 有關[排程專案的密碼保護](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#password)的新主題。此功能支援 [HIPAA 整備程度](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html)。 |
| 2022 年 10 月 | 有關[客戶自控金鑰](/help/privacy/cmk.md)的新主題。此功能支援 [HIPAA 整備程度](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html)。 |
| 2022 年 10 月 | 新增有關 [Customer Journey Analytics 稽核記錄](/help/privacy/audit-log.md)的主題。 |
| 2022 年 10 月 | 新主題：[關鍵量度摘要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=zh-Hant)視覺化。 |
| 2022 年 10 月 | 新章節：[資料檢視中的日期和日期-時間功能](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hant#date) |
| 2022 年 10 月 | 行動應用程式：新主題：[自訂詳細檢視](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=zh-Hant#view-detail-slides)。 |
| 2022 年 10 月 | [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)主題的更新。 |
| **2022 年 9 月** | |
| 2022 年 9 月 | 新增有關[將 Google Analytics 資料移轉到 Customer Journey Analytics](/help/use-cases/ga/overview.md) 的使用案例。 |
| 2022 年 9 月 | Workspace [組合圖表](/help/analysis-workspace/visualizations/combo-charts.md)的新主題。 |
| 2022 年 9 月 | Workspace [實驗面板](/help/analysis-workspace/c-panels/experimentation.md)的新主題。 |
| **2022 年 8 月** | |
| 2022 年 8 月 | 有關 [Analytics 來源連接器的跨區域支援](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)的 Adobe Experience Platform 文章 |
| 2022 年 8 月 | 大幅更新有關 [Customer Journey Analytics 存取控制](/help/admin/cja-access-control.md)的文章。 |
| 2022 年 8 月 | 新增有關 [Customer Journey Analytics 支援資料控管標籤和原則](/help/data-views/data-governance.md)的文章。 |
| 2022 年 8 月 | 新增[比較透過 Analytics 來源連接器傳遞的 Analytics 資料的術語](/help/getting-started/aa-vs-cja/terminology.md)的文章 |
| 2022 年 8 月 | 新增[將對象發佈到即時客戶個人檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=zh-Hant)的文件。 |
| **2022 年 7 月** | |
| 2022 年 7 月 | [「媒體播放時間」面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=zh-Hant)文件。 |
| 2022 年 7 月 | [「媒體同時檢閱者」面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=zh-Hant)文件。 |
| 2022 年 7 月 | [第一個工作階段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hant#new-repeat)報告文件。 |
| **2022 年 6 月** | |
| 2022 年 6 月 | 關於 [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hant)的新文章 |
| 2022 年 6 月 | 新增 [Adobe Analytics 處理規則、VISTA 和分類與 Analytics 來源連接器的「資料準備」的比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)的文章 |
| 2022 年 6 月 | 新增[虛擬報告環境和沙箱環境](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)的文章。 |
| 2022 年 6 月 | 新增有關[比較在 Adobe Analytics 和 Customer Journey Analytics 報告功能的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)文章。 |
| 2022 年 6 月 | 新增[結合報告套裝與不同的結構描述](/help/use-cases/aa-data/combine-report-suites.md)文章。 |
| 2022 年 6 月 | 新增[以行動計分卡共用註解](/help/components/annotations/mobile-annotations.md)的文章。 |
| 2022 年 6 月 | 新增有關 [Customer Journey Analytics 中 Analytics Labs](/help/labs/labs.md) 的文章。 |
| 2022 年 6 月 | 新增[支援數值欄位做為查閱鍵和查閱值](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#numeric)的區段。 |
| 2022 年 6 月 | 更新[流量視覺效果工作流程](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。 |
| **2022 年 5 月** | |
| 2022 年 5 月 | 大幅更新有關在 Customer Journey Analytics 中[建立連線](/help/connections/create-connection.md)的文章。 |
| 2022 年 5 月 | 新增有關如何[在 Customer Journey Analytics Report Builder 中管理資料區塊](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=zh-Hant)的文章。 |
| 2022 年 5 月 | 新增有關[將 Adobe Experience Platform 對象帶進 Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md) 的文章。 |
| **2022 年 4 月** | |
| 2022 年 4 月 | [維度子字串](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=zh-Hant)文件。 |
| 2022 年 4 月 | 新增 [Adobe Analytics 使用者適用的 Customer Journey Analytics 使用指南](/help/getting-started/aa-to-cja-user.md)。 |
| **2022 年 3 月** | |
| 2022 年 3 月 | 新增 [Customer Journey Analytics 註解 API 文件](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)。 |
| 2022 年 3 月 | 有關[工作區中註解](/help/components/annotations/overview.md)的新文件。 |
| 2022 年 3 月 | 有關[估算連線規模](/help/getting-started/cja-faq.md)的重大更新內容。 |
| **2022 年 2 月** | |
| 2022 年 2 月 | 新增適用於從 Adobe Analytics 移至 Customer Journey Analytics 的管理員指南：[Adobe Analytics 至 Customer Journey Analytics 的發展進程](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=zh-Hant) |
| **2022 年 1 月** | |
| 2022 年 1 月 | 新增[在 Customer Journey Analytics 中使用繫結維度和量度](/help/use-cases/data-views/binding-dimensions-metrics.md)的使用案例 |
| 2022 年 1 月 | 新增關於[繫結維度和量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)，以及新的[[!UICONTROL 最先已知]和[!UICONTROL 最後已知]配置設定](/help/data-views/component-settings/persistence.md#allocation-settings)的新功能文件 |
| 2022 年 1 月 | 新增有關[比較 Adobe Analytics 資料與 Customer Journey Analytics 中的 Analytics 資料](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html)的文章 |

{style="table-layout:auto"}

## 2021

| 日期 | 更新說明 |
| --- | --- |
| **2021 年 11 月** | |
| 2021 年 11 月 | 已更新「連線詳細資料」頁面上「[[!UICONTROL 略過的記錄]](/help/connections/manage-connections.md)」文件。 |
| **2021 年 10 月** | |
| 2021 年 10 月 | 適用於 Customer Journey Analytics 之 [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/report-buider-overview.html?lang=zh-Hant#) 的文件。 |
| 2021 年 10 月 | Customer Journey Analytics [稽核紀錄](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) API 文件 |
| 2021 年 10 月 | [Analytics 儀表板視覺效果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=zh-Hant#apply-visualizations)的紀錄 |
| 2021 年 10 月 | [!UICONTROL 連線][資料保留](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant#set-rolling-window-for-connection-data-retention)滾動時段的文件。 |
| **2021 年 9 月** | |
| 2021 年 9 月 | [量度重複資料刪除](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=zh-Hant)文件 |
| 2021 年 9 月 | [報表中的「日光節約時間」支援](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hant#calendar) |
| 2021 年 9 月 | [客戶行事曆](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hant#calendar)文件 |
| 2021 年 9 月 | [布林值欄位](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html?lang=zh-Hant)文件 |
| 2021 年 9 月 | 將資料檢視中的元件設定拆解成個別檔案:<ul><li>[[!UICONTROL 元件]設定概觀](/help/data-views/component-settings/overview.md)</li><li>[[!UICONTROL 歸因]元件設定](/help/data-views/component-settings/attribution.md)</li><li>[[!UICONTROL 行為]元件設定](/help/data-views/component-settings/behavior.md)</li><li>[[!UICONTROL 格式]元件設定](/help/data-views/component-settings/format.md)</li><li>[[!UICONTROL 包含/排除]元件設定](/help/data-views/component-settings/include-exclude-values.md)</li><li>[[!UICONTROL 量度重複資料刪除]元件設定](/help/data-views/component-settings/metric-deduplication.md)</li><li>[[!UICONTROL 無值]元件設定](/help/data-views/component-settings/no-value-options.md)</li><li>[[!UICONTROL 持續性]元件設定](/help/data-views/component-settings/persistence.md)</li><li>[[!UICONTROL 值分組]元件設定](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| 2021 年 9 月 | 新增有關在 Customer Journey Analytics 中[合併報告套裝的影響](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#6.-considerations-when-merging-report-suites-in-cja)的章節。 |
| **2021 年 8 月** | |
| 2021 年 8 月 | 新增有關增強 Customer Journey Analytics 之[連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant)體驗的章節。 |
| 2021 年 8 月 | 有關[「資料檢視」維度中區分大小寫](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hant#configure-behavior-settings)的新章節。 |
| **2021 年 6 月** | |
| 2021 年 6 月 | 有關「工作區」中[之前專案版本](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html?lang=zh-Hant#previous-version)的新文件。 |
| **2021 年 4 月** | |
| 2021 年 4 月 | 有關[持續性](/help/data-views/component-settings/persistence.md)的新主題。 |
| 2021 年 4 月 | 有關「工作區」中支援排定專案的新文件。 |
| 2021 年 4 月 | 有關[強化「資料檢視」體驗](/help/data-views/data-views.md)的新主題。 |
| 2021 年 4 月 | 有關[擷取 Google Analytics 資料](/help/use-cases/ga/overview.md)和[分析該資料](/help/use-cases/ga/report.md)的新主題。 |
| 2021 年 4 月 | 有關「工作區」中[排程報告](/help/analysis-workspace/curate-share/t-schedule-report.md)的新增主題。 |
| 2021 年 4 月 | 新增有關 [Customer Journey Analytics 中高基數維度](/help/components/dimensions/high-cardinality.md)的主題。 |
| **2021 年 3 月** | |
| 2021 年 3 月 | 有關支援 [Analytics 儀表板](/help/mobile-app/home.md) (行動應用程式) 的新增主題。 |
| 2021 年 3 月 | 有關「工作區」中[使用者偏好](/help/analysis-workspace/user-preferences.md)的新主題。 |
| **2021 年 2 月** | |
| 2021 年 2 月 | 有關使用 [Adobe Experience Platform 中的「行銷管道」維度](/help/use-cases/aa-data/marketing-channels.md)的新主題。 |
| 2021 年 2 月 | 發佈新的 [Customer Journey Analytics API](https://www.adobe.io/cja-apis/docs/) 文件。 |
| **2021 年 1 月** | |
| 2021 年 1 月 | 有關[將標準查詢新增至您的資料集](/help/connections/standard-lookups.md)的新主題。 |

{style="table-layout:auto"}

## 2020

| 日期 | 更新說明 |
| --- | --- |
| 2020 年 11 月 13 日 | 有關[跨管道分析](/help/cca/overview.md)的新主題，這可讓您為資料集的使用者 ID 重設金鑰，並啟用多個資料集的無縫結合。 |
| 2020 年 11 月 13 日 | 新增有關[匯入客服中心和 Web 資料](/help/use-cases/cross-channel/call-center.md)的新使用案例。 |
| 2020 年 11 月 10 日 | 新增有關刪除資料元件對[常見問題集](/help/getting-started/cja-faq.md)之影響的區段。 |
| 2020 年 11 月 2 日 | [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)頁面的更新。 |
| 2020 年 11 月 | 新增有關[移除回填限制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#backfill-historical-data)以完成連線的內容。 |
| 2020 年 10 月 7 日 | 新增有關[合併事件資料集](/help/connections/combined-dataset.md)的主題。 |
| 2020 年 9 月 15 日 | 新增有關[資料擷取](/help/data-ingestion/data-ingestion.md)的主題。 |
| 2020 年 9 月 2 日 | 更新有關[使用者權限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)的區段。 |
| 2020 年 8 月 7 日 | 有關[B2B 使用案例 - 查詢資料集](/help/use-cases/b2b/b2b.md)的新主題已新增。 |
| 2020 年 7 月 | 新增有關[使用者 ID 恆等映射選項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant)的資訊。 |
| 2020 年 7 月 | 有關[物件陣列](/help/use-cases/object-arrays.md)或「資料階層」的新主題已新增。 |
| 2020 年 4 月 14 日 | 對[建立連線](/help/connections/create-connection.md)主題中最新 UI 的更新。 |
| 2020 年 2 月 27 日 | 更新 [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md) |
| 2019 年 12 月 | Customer Journey Analytics 文件的第一份草稿 |

{style="table-layout:auto"}
