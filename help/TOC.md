---
git-repo: https://github.com/AdobeDocs/analytics-platform.zh-Hant
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 指南
user-guide-description: 本指南針對 Adobe 用於跨管道分析的新一代解決方案，即 Customer Journey Analytics (以 Adobe Experience Platform 為基礎) 提供支援。
breadcrumb-title: Customer Journey Analytics 指南
source-git-commit: f6ad28f8ed766bd25986da48bfd7bd7e86df0861
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 98%

---


# Customer Journey Analytics 指南 {#using}

+ [Customer Journey Analytics 指南](getting-started/cja-landing.md)
+ 版本注意事項 {#releases}
   + [最新版本](release-notes/latest.md)
   + [2022 版本](release-notes/2022.md)
   + [2021 版本](release-notes/2021.md)
   + [2020 版本](release-notes/2020.md)
   + [CJA 版本](release-notes/releases.md)
   + [CJA 文件更新](release-notes/doc-changes.md)
+ Customer Journey Analytics 總覽 {#cja-overview}
   + [Customer Journey Analytics 總覽](getting-started/cja-overview.md)
   + [快速入門](getting-started/cja-getting-started.md)
   + [Customer Journey Analytics 登陸頁面](getting-started/landing.md)
   + [常見問答](getting-started/cja-faq.md)
   + [Adobe Analytics 至 Customer Journey Analytics 的發展進程](getting-started/aa-to-cja.md)
   + [全新 Customer Journey Analytics 使用者使用指南](getting-started/aa-to-cja-user.md)
   + 比較 Adobe Analytics 和 Customer Journey Analytics {#compare-aa-cja}
      + [Customer Journey Analytics 功能支援](getting-started/aa-vs-cja/cja-aa.md)
      + [比較 Adobe Analytics 和 CJA 的資料處理](getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [虛擬報告環境和沙箱環境](getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [處理規則、VISTA 和分類與「資料準備」的比較](getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID、ECID、ACUSTOMID和分析源連接器](getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [刪除關聯](getting-started/cja-deletion.md)
   + [CJA 字彙表](getting-started/cja-glossary.md)
+ 連線 {#cja-connections}
   + [連線總覽](connections/overview.md)
   + [建立連線](connections/create-connection.md)
   + [管理連線](connections/manage-connections.md)
   + [合併事件資料集](connections/combined-dataset.md)
   + [標準查詢](connections/standard-lookups.md)
   + 跨管道分析 {#cca}
      + [跨管道分析總覽](connections/cca/overview.md)
      + [重播的運作方式](connections/cca/replay.md)
      + [跨管道分析常見問答](connections/cca/faq.md)
+ 資料檢視 {#cja-dataviews}
   + [資料檢視總覽](data-views/data-views.md)
   + [建立或編輯資料檢視](data-views/create-dataview.md)
   + 元件設定 {#component-settings}
      + [元件設定總覽](data-views/component-settings/overview.md)
      + [歸因](data-views/component-settings/attribution.md)
      + [行為](data-views/component-settings/behavior.md)
      + [格式](data-views/component-settings/format.md)
      + [包含排除值](data-views/component-settings/include-exclude-values.md)
      + [量度重複資料刪除](data-views/component-settings/metric-deduplication.md)
      + [沒有值選項](data-views/component-settings/no-value-options.md)
      + [持續性](data-views/component-settings/persistence.md)
      + [子字串](data-views/component-settings/substring.md)
      + [值分組](data-views/component-settings/value-bucketing.md)
   + [標準元件參考](data-views/component-reference.md)
   + [資料檢視使用案例](data-views/data-views-usecases.md)
+ 工作區專案 {#cja-workspace}
   + [Analysis Workspace 總覽](analysis-workspace/home.md)
   + [執行基本分析](analysis-workspace/perform-basic-analysis.md)
   + [執行進階分析](analysis-workspace/perform-adv-analysis.md)
   + 專案 {#build-workspace-project}
      + [專案總覽](analysis-workspace/build-workspace-project/freeform-overview.md)
      + [儲存專案](analysis-workspace/build-workspace-project/save-projects.md)
      + [快速鍵](analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [調色盤](analysis-workspace/build-workspace-project/color-palettes.md)
      + [檢視密度](analysis-workspace/build-workspace-project/view-density.md)
   + 視覺效果 {#visualizations}
      + [視覺效果總覽](analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [管理資料來源](analysis-workspace/visualizations/t-sync-visualization.md)
      + 自由表格 {#freeform-table}
         + [自由表格](analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + 欄和列的設定 {#column-row-settings}
            + [欄設定](analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [列設定](analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [動態與靜態項目](analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [表格分頁、篩選及分類](analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [工作區總計](analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + 同類群組表格 {#cohort-table}
         + [什麼是同類群組分析？](analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [設定同類群組分析報表](analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [同類群組分析使用案例](analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 流失 {#fallout}
         + [流失總覽](analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [設定流失視覺效果](analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [維度間流失](analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [在流失分析中套用篩選](analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 流量 {#flow}
         + [流量總覽](analysis-workspace/visualizations/c-flow/flow.md)
         + [設定流量視覺效果](analysis-workspace/visualizations/c-flow/create-flow.md)
         + [維度間流量](analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [長條圖](analysis-workspace/visualizations/histogram.md)
      + [文氏](analysis-workspace/visualizations/venn.md)
      + [區域圖和堆疊區域圖](analysis-workspace/visualizations/area.md)
      + [長條圖和堆疊長條圖](analysis-workspace/visualizations/bar.md)
      + [項目符號圖表](analysis-workspace/visualizations/bullet-graph.md)
      + [環形圖](analysis-workspace/visualizations/donut.md)
      + [橫條圖和堆疊橫條圖](analysis-workspace/visualizations/horizontal-bar.md)
      + [線圖](analysis-workspace/visualizations/line.md)
      + [散佈圖](analysis-workspace/visualizations/scatterplot.md)
      + [摘要數字和摘要變更](analysis-workspace/visualizations/summary-number-change.md)
      + [Text](analysis-workspace/visualizations/text.md)
      + [樹狀圖](analysis-workspace/visualizations/treemap.md)
   + 面板 {#panels}
      + [面板總覽](analysis-workspace/c-panels/panels.md)
      + [歸因面板](analysis-workspace/c-panels/attribution.md)
      + [空白面板](analysis-workspace/c-panels/blank-panel.md)
      + [自由面板](analysis-workspace/c-panels/freeform-panel.md)
      + [快速深入分析面板](analysis-workspace/c-panels/quickinsight.md)
      + [「媒體同時檢閱者」面板](analysis-workspace/c-panels/media-concurrent-viewers.md)
      + 媒體播放時間 {#media-playback-timespent}
         + [概觀](analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [輸入和輸出設定](analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [常見問答](analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + 策劃、共用及排程專案 {#curate-share}
      + [共用功能表](analysis-workspace/curate-share/send-schedule-files.md)
      + [組織專案](analysis-workspace/curate-share/curate.md)
      + [共用專案](analysis-workspace/curate-share/share-projects.md)
      + [建立分享連結](analysis-workspace/curate-share/shareable-links.md)
      + [僅供檢視的專案](analysis-workspace/curate-share/view-only-projects.md)
      + [下載 PDF 或 CSV 檔案](analysis-workspace/curate-share/download-send.md)
      + [排程專案](analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ {#attribution}
      + [歸因總覽](analysis-workspace/attribution/overview.md)
      + [歸因模型與回顧期間](analysis-workspace/attribution/models.md)
      + [演算法歸因](analysis-workspace/attribution/algorithmic.md)
      + [歸因最佳實務](analysis-workspace/attribution/best-practices.md)
      + [常見問答](analysis-workspace/attribution/faq.md)
   + 虛擬分析人員 {#virtual-analyst}
      + [虛擬分析人員總覽](analysis-workspace/virtual-analyst/overview.md)
      + 異常偵測 {#anomaly-detection}
         + [異常偵測總覽](analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [在 Analysis Workspace 中檢視異常](analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [用於異常偵測的統計技術](analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [使用者偏好設定](analysis-workspace/user-preferences.md)
   + 「工作區」常見問答 {#workspace-faq}
      + [常見問答](analysis-workspace/workspace-faq/faq.md)
      + [最佳化 Analysis Workspace 效能](analysis-workspace/workspace-faq/optimizing-performance.md)
      + [錯誤訊息](analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace 限制](analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理需求](analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace 的協助工具](analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Analysis Workspace 中的長尾](analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Report Builder 概觀](report-builder/report-buider-overview.md)
   + [Report Builder 設定](report-builder/report-builder-setup.md)
   + [建立「資料區塊」](report-builder/create-a-data-block.md)
   + [Report Builder 中心](report-builder/report-builder-hub.md)
   + [選取日期範圍](report-builder/select-date-range.md)
   + [使用篩選器](report-builder/work-with-filters.md)
   + [篩選器維度](report-builder/filter-dimensions.md)
   + [管理資料區塊](report-builder/manage-reportbuilder.md)
   + [Report Builder 設定](report-builder/report-builder-settings.md)
+ 元件 {#cja-components}
   + [元件總覽](components/overview.md)
   + 註解 {#annotations}
      + [註解概述](components/annotations/overview.md)
      + [建立註解](components/annotations/create-annotations.md)
      + [管理註解](components/annotations/manage-annotations.md)
      + [檢視註解](components/annotations/view-annotations.md)
      + [行動註解](components/annotations/mobile-annotations.md)
   + 維度 {#dimensions}
      + [預覽維度](components/dimensions/view-dimensions.md)
      + [劃分維度](components/dimensions/t-breakdown-fa.md)
      + [時間分隔維度](components/dimensions/time-parting-dimensions.md)
      + [基數很高的維度](components/dimensions/high-cardinality.md)
   + [量度](components/apply-create-metrics.md)
   + 篩選 {#cja-filters}
      + [篩選總覽](components/filters/filters-overview.md)
      + [建立篩選](components/filters/create-filters.md)
      + [管理篩選](components/filters/manage-filters.md)
      + [快速篩選](components/filters/quick-filters.md)
      + [臨時篩選](components/filters/ad-hoc-filters.md)
      + [運算子](components/filters/operators.md)
   + 計算量度 {#cja-calcmetrics}
      + [計算量度總覽](components/calc-metrics/calc-metr-overview.md)
      + 計算量度工作流程{#cm-workflow}
         + [計算量度工作流程](components/calc-metrics/cm-workflow/cm-workflow.md)
         + [尋找量度](components/calc-metrics/cm-workflow/cm-finding.md)
         + [建立量度](components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [量度類型和歸因](components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [建立簡單的「每次造訪頁面瀏覽數」量度](components/calc-metrics/cm-workflow/cm-pvv.md)
         + [篩選量度](components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [堆疊和取代區段](components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [篩選和加權的量度](components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [使用函數](components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [參與率量度](components/calc-metrics/cm-workflow/participation-metric.md)
         + [標記計算量度](components/calc-metrics/cm-workflow/cm-tagging.md)
         + [核准計算量度](components/calc-metrics/cm-workflow/cm-approving.md)
         + [共用計算量度](components/calc-metrics/cm-workflow/cm-sharing.md)
         + [計算量度管理員](components/calc-metrics/cm-workflow/cm-manager.md)
      + [基本函數](components/calc-metrics/cm-functions.md)
      + [進階函數](components/calc-metrics/cm-adv-functions.md)
   + 日期範圍 {#cja-date-ranges}
      + [日期範圍總覽](components/date-ranges/overview.md)
      + [建立日期範圍](components/date-ranges/create.md)
      + [管理日期範圍](components/date-ranges/manage.md)
      + [行事曆總覽](components/date-ranges/calendar.md)
      + [建立自訂日期範圍](components/date-ranges/custom-date-ranges.md)
      + [日期比較](components/date-ranges/time-comparison.md)
+ Analytics 儀表板 {#cja-dashboards}
   + [Analytics 儀表板 - 總覽](mobile-app/home.md)
   + [組織者任務](mobile-app/curator.md)
   + [建立計分卡](mobile-app/create-scorecard.md)
   + [設定使用控制面板的高階主管](mobile-app/set-up-execs.md)
   + [高階主管使用者快速入門指南](mobile-app/executive.md)
+ 使用案例 {#cja-usecases}
   + [Customer Journey Analytics 使用案例](use-cases/cja-usecases.md)
   + [結合報告套裝與不同的結構描述](use-cases/combine-report-suites.md)
   + [使用物件陣列](use-cases/object-arrays.md)
   + [使用繫結維度和量度](use-cases/binding-dimensions-metrics.md)
   + [(B2B) 將帳戶層級資料新增為查詢資料集](use-cases/b2b.md)
   + [將 Marketo Engage 資料擷取至 AEP 和 CJA 報告](use-cases/marketo.md)
   + [將 AEP 對象擷取至 CJA](use-cases/ingest-aep-segments.md)
   + [跨管道分析資料](use-cases/cross-channel.md)
   + [匯入客服中心和網頁的資料](use-cases/call-center.md)
   + [資料擷取使用案例](use-cases/data-ingestion.md)
   + [使用行銷管道維度](use-cases/marketing-channels.md)
   + [將 Google Analytics 資料擷取至 Adobe Experience Platform](use-cases/ga-to-cja.md)
   + [報告 CJA 中的 Google Analytics 資料](use-cases/ga-to-cja-reporting.md)
+ Labs {#labs}
   + [Labs 使用手冊](labs/labs.md)
+ 疑難排解 {#troubleshooting}
   + [將您的 Adobe Analytics 資料與 CJA 資料進行比較](troubleshooting/compare.md)
+ 隱私權 {#cja-privacy}
   + [隱私權總覽](privacy/privacy-overview.md)
+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
