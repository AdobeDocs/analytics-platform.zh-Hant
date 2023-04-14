---
git-repo: https://github.com/AdobeDocs/analytics-platform.zh-Hant
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 指南
user-guide-description: 了解 Customer Journey Analytics (CJA)，和如何將 Analysis Workspace 與 Experience Platform 的資料搭配使用。
breadcrumb-title: Customer Journey Analytics 指南
source-git-commit: a69f9eef39c0eceee1964a3b8741b7538b218ece
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 99%

---


# Customer Journey Analytics 指南 {#using}

+ [Customer Journey Analytics 指南](../getting-started/cja-landing.md)

+ 發行說明 {#releases}
   + [最新版本](../release-notes/latest.md)
   + [2023 版本](../release-notes/2023.md)
   + [2022 版本](../release-notes/2022.md)
   + [2021 版本](../release-notes/2021.md)
   + [2020 版本](../release-notes/2020.md)
   + [CJA 版本](../release-notes/releases.md)
   + [CJA 文件更新](../release-notes/doc-changes.md)

+ 快速入門 {#cja-overview}
   + [Customer Journey Analytics 總覽](../getting-started/cja-overview.md)
   + [快速入門指南](../getting-started/cja-getting-started.md)
   + [登陸頁面](../getting-started/landing.md)
   + [常見問題](../getting-started/cja-faq.md)
   + [比較 CJA 和 BI 解決方案](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics 和 Adobe Analytics {#compare-aa-cja}
   + [從 Adobe Analytics 發展而來 ](../getting-started/aa-to-cja.md)
   + [Adobe Analytics 使用者的使用手冊](../getting-started/aa-to-cja-user.md)
   + 與 Adobe Analytics 比較{#cja-aa-comparison}
      + [在 Customer Journey Analytics 中利用 Adobe Analytics 資料](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Customer Journey Analytics 功能支援](../getting-started/aa-vs-cja/cja-aa.md)
      + [比較透過 Analytics 來源連接器傳遞的 Analytics 資料的術語](../getting-started/aa-vs-cja/terminology.md)
      + [比較 Adobe Analytics 和 CJA 的資料處理](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [虛擬報告環境和沙箱環境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [處理規則、VISTA 和分類與資料準備的比較](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ 資料擷取 {#cja-data-ingestion}
   + [資料擷取概觀](../data-ingestion/data-ingestion.md)
   + 擷取和使用快速入門指南{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [Adobe Experience Platform Web SDK 與 Edge Network](../data-ingestion/aepwebsdk.md)
      + [批次資料](../data-ingestion/batch.md)
      + [串流資料](../data-ingestion/streaming.md)
      + [來源連接器](../data-ingestion/sources.md)

+ 連線 {#cja-connections}
   + [連線總覽](../connections/overview.md)
   + [建立連線](../connections/create-connection.md)
   + [管理連線](../connections/manage-connections.md)
   + [合併事件資料集](../connections/combined-dataset.md)
   + [標準查詢](../connections/standard-lookups.md)
   + [跨管道分析](../connections/cca.md)

+ 資料檢視 {#cja-dataviews}
   + [資料檢視總覽](../data-views/data-views.md)
   + [建立或編輯資料檢視](../data-views/create-dataview.md)
   + 元件設定 {#component-settings}
      + [元件設定總覽](../data-views/component-settings/overview.md)
      + [歸因](../data-views/component-settings/attribution.md)
      + [行為](../data-views/component-settings/behavior.md)
      + [格式](../data-views/component-settings/format.md)
      + [包含排除值](../data-views/component-settings/include-exclude-values.md)
      + [量度重複資料刪除](../data-views/component-settings/metric-deduplication.md)
      + [沒有值選項](../data-views/component-settings/no-value-options.md)
      + [持續性](../data-views/component-settings/persistence.md)
      + [子字串](../data-views/component-settings/substring.md)
      + [值分組](../data-views/component-settings/value-bucketing.md)
   + [標準元件參考](../data-views/component-reference.md)
   + [標籤和原則](../data-views/data-governance.md)


+ 工作區專案 {#cja-workspace}
   + [Analysis Workspace 總覽](../analysis-workspace/home.md)
   + [執行基本分析](../analysis-workspace/perform-basic-analysis.md)
   + [執行進階分析](../analysis-workspace/perform-adv-analysis.md)

   + 專案 {#build-workspace-project}
      + [專案總覽](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [儲存專案](../analysis-workspace/build-workspace-project/save-projects.md)
      + Workspace 資料夾{#workspace-folders}
         + [關於 Workspace 資料夾](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [建立資料夾和子資料夾](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [刪除資料夾](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [新增專案](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [移除專案](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [儲存新專案](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [快速鍵](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [調色盤](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [檢視密度](../analysis-workspace/build-workspace-project/view-density.md)
   + 視覺效果 {#visualizations}
      + [視覺效果總覽](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [管理資料來源](../analysis-workspace/visualizations/t-sync-visualization.md)

      + 自由表格 {#freeform-table}
         + [自由表格](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + 欄和列的設定 {#column-row-settings}
            + [欄設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [列設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [動態與靜態項目](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [表格分頁、篩選及分類](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)

         + [工作區總計](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + 同類群組表格 {#cohort-table}
         + [什麼是同類群組分析？](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [設定同類群組分析報表](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [同類群組分析使用案例](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 流失 {#fallout}
         + [流失總覽](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [設定流失視覺效果](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [維度間流失](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [在流失分析中套用篩選](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 流量 {#flow}
         + [流量總覽](../analysis-workspace/visualizations/c-flow/flow.md)
         + [設定流量視覺效果](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [維度間流量](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [區域圖和堆疊區域圖](../analysis-workspace/visualizations/area.md)

      + [長條圖和堆疊長條圖](../analysis-workspace/visualizations/bar.md)
      + [項目符號圖表](../analysis-workspace/visualizations/bullet-graph.md)
      + [組合圖表](../analysis-workspace/visualizations/combo-charts.md)
      + [環形圖](../analysis-workspace/visualizations/donut.md)
      + [長條圖](../analysis-workspace/visualizations/histogram.md)
      + [橫條圖和堆疊橫條圖](../analysis-workspace/visualizations/horizontal-bar.md)
      + [關鍵量度摘要](../analysis-workspace/visualizations/key-metric.md)
      + [折線圖](../analysis-workspace/visualizations/line.md)
      + [散佈圖](../analysis-workspace/visualizations/scatterplot.md)
      + [摘要數字和摘要變更](../analysis-workspace/visualizations/summary-number-change.md)
      + [文字](../analysis-workspace/visualizations/text.md)
      + [樹狀圖](../analysis-workspace/visualizations/treemap.md)
      + [文氏圖表](../analysis-workspace/visualizations/venn.md)
   + 面板 {#panels}
      + [面板總覽](../analysis-workspace/c-panels/panels.md)
      + [歸因面板](../analysis-workspace/c-panels/attribution.md)
      + [空白面板](../analysis-workspace/c-panels/blank-panel.md)
      + [實驗面板](../analysis-workspace/c-panels/experimentation.md)
      + [自由面板](../analysis-workspace/c-panels/freeform-panel.md)
      + [快速深入分析面板](../analysis-workspace/c-panels/quickinsight.md)
      + [媒體同時檢閱者面板](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + 媒體播放時間 {#media-playback-timespent}
         + [概觀](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [輸入和輸出設定](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [常見問題](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + 策劃、共用及排程專案 {#curate-share}
      + [共用功能表](../analysis-workspace/curate-share/send-schedule-files.md)
      + [組織專案](../analysis-workspace/curate-share/curate.md)
      + [共用專案](../analysis-workspace/curate-share/share-projects.md)
      + [建立分享連結](../analysis-workspace/curate-share/shareable-links.md)
      + [僅供檢視的專案](../analysis-workspace/curate-share/view-only-projects.md)
      + [下載 PDF 或 CSV 檔案](../analysis-workspace/curate-share/download-send.md)
      + [排程專案](../analysis-workspace/curate-share/t-schedule-report.md)
   + 虛擬分析人員 {#virtual-analyst}
      + [虛擬分析人員總覽](../analysis-workspace/virtual-analyst/overview.md)
      + 異常偵測 {#anomaly-detection}
         + [異常偵測總覽](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [在 Analysis Workspace 中檢視異常](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [用於異常偵測的統計技術](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [使用者偏好設定](../analysis-workspace/user-preferences.md)

   + 工作區常見問題 {#workspace-faq}
      + [常見問題](../analysis-workspace/workspace-faq/faq.md)
      + [最佳化 Analysis Workspace 效能](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [錯誤訊息](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace 限制](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理需求](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace 的協助工具](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Analysis Workspace 中的長尾](../analysis-workspace/workspace-faq/long-tail.md)











+ 元件 {#cja-components}
   + [元件總覽](../components/overview.md)
   + [新增元件說明](../components/add-component-descriptions.md)
   + 註解 {#annotations}
      + [註解概述](../components/annotations/overview.md)
      + [建立註解](../components/annotations/create-annotations.md)
      + [管理註解](../components/annotations/manage-annotations.md)
      + [檢視註解](../components/annotations/view-annotations.md)
      + [行動註解](../components/annotations/mobile-annotations.md)
   + 對象 {#audiences}
      + [對象概覽](../components/audiences/audiences-overview.md)
      + [建立及發佈對象](../components/audiences/publish.md)
      + [管理對象](../components/audiences/manage.md)
   + 維度 {#dimensions}
      + [預覽維度](../components/dimensions/view-dimensions.md)
      + [劃分維度](../components/dimensions/t-breakdown-fa.md)
      + [時間分隔維度](../components/dimensions/time-parting-dimensions.md)
      + [基數很高的維度](../components/dimensions/high-cardinality.md)
   + [量度](../components/apply-create-metrics.md)
   + 篩選 {#cja-filters}
      + [篩選總覽](../components/filters/filters-overview.md)
      + [建立篩選](../components/filters/create-filters.md)
      + [管理篩選](../components/filters/manage-filters.md)
      + [快速篩選](../components/filters/quick-filters.md)
      + [運算子](../components/filters/operators.md)
   + 計算量度 {#cja-calcmetrics}
      + [計算量度總覽](../components/calc-metrics/calc-metr-overview.md)
      + 計算量度工作流程{#cm-workflow}
         + [計算量度工作流程](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [尋找量度](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [建立量度](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [量度類型和歸因](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [建立簡單的「每次造訪頁面瀏覽數」量度](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [篩選量度](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [堆疊和取代區段](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [篩選和加權的量度](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [使用函數](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [參與率量度](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [標記計算量度](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [核准計算量度](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [共用計算量度](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [計算量度管理員](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [預設計算量度](../components/calc-metrics/default-calcmetrics.md)
      + [基本函數](../components/calc-metrics/cm-functions.md)
      + [進階函數](../components/calc-metrics/cm-adv-functions.md)
   + 日期範圍 {#cja-date-ranges}
      + [日期範圍總覽](../components/date-ranges/overview.md)
      + [建立日期範圍](../components/date-ranges/create.md)
      + [管理日期範圍](../components/date-ranges/manage.md)
      + [行事曆總覽](../components/date-ranges/calendar.md)
      + [建立自訂日期範圍](../components/date-ranges/custom-date-ranges.md)
      + [日期比較](../components/date-ranges/time-comparison.md)
   + 資料字典 {#data-dictionary}
      + [資料字典概觀](../components/data-dictionary/data-dictionary-overview.md)
      + [檢視資料字典中的元件資訊](../components/data-dictionary/view-data-dictionary.md)
      + [編輯資料字典中的元件條目](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [監視資料字典健康狀況](../components/data-dictionary/monitor-data-dictionary-health.md)
+ Analytics 儀表板 {#cja-dashboards}
   + [Analytics 儀表板 - 總覽](../mobile-app/home.md)
   + [組織者任務](../mobile-app/curator.md)
   + [建立行動計分卡](../mobile-app/create-scorecard.md)
   + [設定使用儀表板的主管](../mobile-app/set-up-execs.md)
   + [高階主管使用者快速入門指南](../mobile-app/executive.md)

+ Report Builder {#cja-reportbuilder}
   + [Report Builder 概觀](../report-builder/report-buider-overview.md)
   + [Report Builder 設定](../report-builder/report-builder-setup.md)
   + [建立資料區塊](../report-builder/create-a-data-block.md)
   + [Report Builder 中心](../report-builder/report-builder-hub.md)
   + [選取日期範圍](../report-builder/select-date-range.md)
   + [使用篩選器](../report-builder/work-with-filters.md)
   + [篩選器維度](../report-builder/filter-dimensions.md)
   + [管理資料區塊](../report-builder/manage-reportbuilder.md)
   + [排程活頁簿](../report-builder/schedule-reportbuilder.md)
   + [受限制的標籤](../report-builder/restricted-labels.md)
   + [Report Builder 設定](../report-builder/report-builder-settings.md)

+ 跨管道分析 {#cca}
   + [跨管道分析總覽](../cca/overview.md)
   + [重播的運作方式](../cca/replay.md)
   + [跨管道分析常見問題](../cca/faq.md)

+ Adobe 整合 {#integrations}
   + [整合 Adobe 解決方案與 CJA 總覽](/help/integrations/overview.md)
   + [將 Adobe Analytics 與 Customer Journey Analytics 整合](/help/integrations/aa.md)
   + [將 Journey Optimizer 資料與 CJA 整合](/help/integrations/ajo.md)
   + [將決策管理資料與CJA整合](/help/integrations/ajo-od.md)
   + [將 Customer AI 資料與 CJA 整合](/help/integrations/customer-ai.md)

+ 資料控管 {#cja-privacy}
   + [資料控管](../privacy/privacy-overview.md)
   + [稽核記錄](../privacy/audit-log.md)
   + [客戶自控金鑰](../privacy/cmk.md)

+ 使用案例 {#cja-usecases}
   + [Customer Journey Analytics 使用案例](../use-cases/cja-usecases.md)
   + Google Analytics 資料 {#ga}
      + [將資料從 Google Analytics 移轉到 CJA 概述](../use-cases/ga/overview.md)
      + [將 Google Analytics 歷史資料擷取至 Platform](../use-cases/ga/backfill.md)
      + [將串流的 Google Analytics 資料設定至 Platform](../use-cases/ga/streaming.md)
      + [報告 CJA 中的 Google Analytics 資料](../use-cases/ga/report.md)
   + 資料擷取 {#data-ingestion}
      + [將 Marketo Engage 資料擷取至 AEP 並在 CJA 中報告](../use-cases/data-ingestion/marketo.md)
      + [將 AEP 對象擷取至 CJA](../use-cases/data-ingestion/ingest-aep-segments.md)
   + 資料檢視 {#data-views}
      + [資料檢視使用案例](../use-cases/data-views/data-views-usecases.md)
      + [使用繫結維度和量度](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [新增帳戶層級資料當作查詢資料集](../use-cases/b2b/b2b.md)
   + 跨管道的資料 {#cross-channel}
      + [跨管道分析資料](../use-cases/cross-channel/cross-channel.md)
      + [匯入客服中心和網頁的資料](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics 資料 {#aa-data}
      + [使用行銷管道維度](../use-cases/aa-data/marketing-channels.md)
      + [結合報告套裝與不同的結構描述](../use-cases/aa-data/combine-report-suites.md)
   + 複雜的資料 {#complex-data}
      + [使用物件陣列](../use-cases/object-arrays.md)

+ 管理 {#cja-admin}
   + [存取控制](../admin/cja-access-control.md)
   + [檢視和管理使用情況](../admin/estimate-usage.md)
   + [刪除關聯](../admin/cja-deletion.md)

+ Labs {#labs}
   + [Labs 使用手冊](../labs/labs.md)

+ 疑難排解 {#troubleshooting}
   + [將您的 Adobe Analytics 資料與 CJA 資料進行比較](../troubleshooting/compare.md)
   + [Real-time CDP 與 CJA 之間的量度一致性及對象會籍數](../troubleshooting/consistency-rcdp-cja.md)

+ [CJA 字彙表](../getting-started/cja-glossary.md)

+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
