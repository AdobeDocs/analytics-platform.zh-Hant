---
git-repo: https://github.com/AdobeDocs/analytics-platform.zh-Hant
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 指南
user-guide-description: 了解 Adobe Customer Journey Analytics 以及如何將 Analysis Workspace 與 Experience Platform 的資料搭配使用。
breadcrumb-title: Customer Journey Analytics 指南
source-git-commit: a16043f1bb15deba1332ed39438214597647b9b4
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 99%

---

# Adobe Customer Journey Analytics 指南 {#using}

+ [Adobe Customer Journey Analytics 指南](../getting-started/cja-landing.md)

+ 發行說明 {#releases}
   + [最新版本](../release-notes/latest.md)
   + [預發行說明](../release-notes/pre-release-notes.md)
   + [2025 年版本](../release-notes/2025.md)
   + [2024 年版本](../release-notes/2024.md)
   + [2023 版本](../release-notes/2023.md)
   + [2022 版本](../release-notes/2022.md)
   + [2021 版本](../release-notes/2021.md)
   + [2020 版本](../release-notes/2020.md)
   + [功能版本策略](../release-notes/releases.md)
   + [文件更新](../release-notes/doc-changes.md)

+ 開始使用 {#cja-overview}
   + Customer Journey Analytics {#cja-b2c-overview}
      + [概觀](../getting-started/cja-overview.md)
      + [快速入門指南](../getting-started/cja-getting-started.md)
      + [登陸頁面](../getting-started/landing.md)
      + [常見問題](../getting-started/cja-faq.md)
      + [和 BI 解決方案比較](../getting-started/cja-vs-bi.md)
      + [AI 助理](../ai-assistant.md)
      + [Data Insights 代理](../data-analysis-ai.md)
   + Customer Journey Analytics B2B Edition {#cja-b2b}
      + [概觀](/help/getting-started/cja-b2b-edition.md)
      + [B2B 概念與特點](/help/getting-started/cja-b2b-concepts-features.md)
      + [快速入門指南](/help/getting-started/cja-b2b-quick-start-guide.md)
      + [轉變指南](/help/getting-started/cja-b2b-transition.md)

+ 升級和比較 {#compare-aa-cja}
   + 升級至 Customer Journey Analytics {#upgrade-to-cja}
      + [開始使用](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [選擇您的升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [將資料傳送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [建議的升級流程](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + 架構者和建立結構描述 {#schema}
         + [建立您的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
         + [建立您的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
         + [使用您現有的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + 建立資料流 {#create-datastream}
         + [建立資料流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
         + [新增平台即服務](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + 建立資料集 {#create-datasets}
         + [建立資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
         + [建立用於分類的查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
         + [監視資料集擷取](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + 使用標記實施 Web SDK {#create-tags}
         + [為您的屬性建立標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
         + [將 Web SDK 擴充功能新增至您的標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
         + [實施適用於 Web SDK 擴充功能的 Loader 標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
         + [將 XDM 資料收集邏輯新增至您的標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [手動實施 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-manual.md)
      + [使用 API 實施 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-api.md)
      + [建立連線](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [建立資料視圖](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [建立行銷管道衍生的欄位](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [驗證資料流](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [設定串流媒體集合](/help/getting-started/cja-upgrade/cja-upgrade-streaming-media.md)
      + 透過 Analytics 來源連接器保留歷史資料 {#historical-data-source-connector}
         + [建立 Analytics 來源連接器的 XDM 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
         + [建立 Analytics 來源連接器和對應欄位](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
         + [將 Analytics 來源連接器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [評估何時要停用 Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)
      + [停用 Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + 替代的升級方法 {#alternative-upgrade-methods}
         + [使用 AppMeasurement 資料收集](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)
         + [傳送資料層](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)
         + [Analytics 來源連接器](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)
      + 其他升級情境 {#other-upgrade-scenarios}
         + [從 Analytics 來源連接器移至 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
         + [從非 Adobe Analytics 解決方案升級](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + 其他資訊 {#additional-information}
         + [了解 Analytics 實施](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
         + [升級過程中支援 Adobe Analytics 功能](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
         + [Customer Journey Analytics 功能](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md)
         + [Web SDK 實施選項](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md)
         + [設定 Adobe Analytics Web SDK for Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)
         + [使用 Adobe Journey Optimizer 進行個人化](/help/getting-started/cja-upgrade/cja-upgrade-personalization-journeyoptimizer.md)
   + 與 Adobe Analytics 比較 {#cja-aa-comparison}
      + [概觀](../getting-started/aa-vs-cja/overview.md)
      + [使用 Adobe Analytics 資料 ](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [功能支援](../getting-started/aa-vs-cja/cja-aa.md)
      + [比較術語](../getting-started/aa-vs-cja/terminology.md)
      + [比較資料處理](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [環境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [分析處理與資料準備](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [分析身分識別](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [從 Adobe Analytics 發展而來](../getting-started/aa-to-cja.md)
   + [Adobe Analytics 使用者的使用手冊](../getting-started/aa-to-cja-user.md)

+ 資料攝取 {#cja-data-ingestion}
   + [概觀](../data-ingestion/data-ingestion.md)
   + 攝取和使用快速入門指南{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network  {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [伺服器 API](../data-ingestion/serverapi.md)
      + [批次資料](../data-ingestion/batch.md)
      + [串流資料](../data-ingestion/streaming.md)
      + [來源連接器](../data-ingestion/sources.md)
      + [Ad hoc 資料](/help/data-ingestion/adhoc.md)

+ Data Mirror {#cja-data-mirror}
   + [概觀](/help/data-mirror/data-mirror.md)
   + 設定 {#configure}
      + [資料倉儲原生解決方案](/help/data-mirror/datawarehouse.md)
      + [Experience Platform](/help/data-mirror/aep.md)
      + [Customer Journey Analytics](/help/data-mirror/cja.md)
   + [Data Mirror 快速入門指南](/help/data-mirror/model-based.md)

+ 連線 {#cja-connections}
   + [連線概觀](../connections/overview.md)
   + [建立或編輯連線](../connections/create-connection.md)
   + [管理連線](../connections/manage-connections.md)
   + [合併事件資料集](../connections/combined-dataset.md)
   + [標準查詢](../connections/standard-lookups.md)
   + [B2B 查詢](../connections/transform-datasets-b2b-lookups.md)

+ 資料檢視 {#cja-dataviews}
   + [資料檢視概觀](../data-views/data-views.md)
   + [建立或編輯資料檢視](../data-views/create-dataview.md)
   + [工作階段設定](../data-views/session-settings.md)
   + 元件設定 {#component-settings}
      + [元件設定概觀](../data-views/component-settings/overview.md)
      + [歸因](../data-views/component-settings/attribution.md)
      + [行為](../data-views/component-settings/behavior.md)
      + [格式](../data-views/component-settings/format.md)
      + [包含排除值](../data-views/component-settings/include-exclude-values.md)
      + [量度重複資料刪除](../data-views/component-settings/metric-deduplication.md)
      + [沒有值選項](../data-views/component-settings/no-value-options.md)
      + [持續性](../data-views/component-settings/persistence.md)
      + [子字串](../data-views/component-settings/substring.md)
      + [摘要資料群組](../data-views/component-settings/summary-data-group.md)
      + [值分組](../data-views/component-settings/value-bucketing.md)
   + [標準元件參考](../data-views/component-reference.md)
   + [BI 擴充功能](../data-views/bi-extension.md)
   + [衍生欄位](../data-views/derived-fields/derived-fields.md)
   + [摘要資料](../data-views/summary-data.md)
   + [標籤和原則](../data-views/data-governance.md)
   + 共用的量度和維度{#shared-metrics-dimensions}
      + [概觀](/help/data-views/shared-metrics-dimensions/smd-overview.md)
      + [編輯器](/help/data-views/shared-metrics-dimensions/shared-component-editor.md)

+ 工具 {#tools}
   + 資產轉移 {#asset-transfer}
      + [轉移資產](../tools/asset-transfer/transfer-assets.md)
   + 產品使用情況 {#product-usage}
      + [概觀](../tools/product-usage/usage-overview.md)
      + [資料設定](../tools/product-usage/data-settings.md)
      + [選擇退出設定](../tools/product-usage/opt-out-settings.md)

+ Workspace 專案 {#cja-workspace}
   + [Analysis Workspace 概觀](../analysis-workspace/home.md)
   + [執行基本分析](../analysis-workspace/perform-basic-analysis.md)
   + [執行進階分析](../analysis-workspace/perform-adv-analysis.md)
   + 專案 {#build-workspace-project}
      + [概觀](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [快速開始專案](/help/analysis-workspace/build-workspace-project/starter-projects.md)
      + [建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [開啟專案](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [針對專案發表評論](/help/analysis-workspace/build-workspace-project/comment-projects.md)
      + [儲存專案](../analysis-workspace/build-workspace-project/save-projects.md)
      + [目錄](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
      + Workspace 的資料夾 {#workspace-folders}
         + [概觀](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [建立資料夾](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [管理資料夾](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [新增或移動專案](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [快捷鍵](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [調色盤](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [檢視密度](../analysis-workspace/build-workspace-project/view-density.md)
      + [偵錯工具](../analysis-workspace/build-workspace-project/debugger.md)
   + 範本 {#templates}
      + [使用範本](../analysis-workspace/templates/use-templates.md)
      + [建立和管理範本](../analysis-workspace/templates/create-templates.md)
   + 視覺效果 {#visualizations}
      + [概觀](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [管理資料來源](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [智慧型註解](../analysis-workspace/visualizations/intelligent-captions.md)
      + 自由格式表格 {#freeform-table}
         + [概觀](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [建立超連結](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + [檢視趨勢資料](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)
         + [篩選和排序](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [總計](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
         + 欄和列的設定 {#column-row-settings}
            + [欄設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [列設定](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [動態與靜態項目](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
      + 同類群組表格 {#cohort-table}
         + [概觀](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [設定](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [使用案例](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 流失 {#fallout}
         + [概觀](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [設定](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [維度間流失](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [套用區段](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 流量 {#flow}
         + [概觀](../analysis-workspace/visualizations/c-flow/flow.md)
         + [設定](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [維度間流程](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + 歷程畫布 {#journey-canvas}
         + [概觀](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [設定](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [疑難排解](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [區域圖 (堆疊)](../analysis-workspace/visualizations/area.md)
      + [條狀圖 (堆疊)](../analysis-workspace/visualizations/bar.md)
      + [項目符號](../analysis-workspace/visualizations/bullet-graph.md)
      + [組合](../analysis-workspace/visualizations/combo-charts.md)
      + [環形圖](../analysis-workspace/visualizations/donut.md)
      + [直方圖](../analysis-workspace/visualizations/histogram.md)
      + [橫條圖 (堆疊)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [關鍵量度摘要](../analysis-workspace/visualizations/key-metric.md)
      + [折線圖](../analysis-workspace/visualizations/line.md)
      + [地圖](/help/analysis-workspace/visualizations/map.md)
      + [散佈圖](../analysis-workspace/visualizations/scatterplot.md)
      + [區段標題](/help/analysis-workspace/visualizations/section-header.md)
      + [摘要數字和變更](../analysis-workspace/visualizations/summary-number-change.md)
      + [文字](../analysis-workspace/visualizations/text.md)
      + [樹狀圖](../analysis-workspace/visualizations/treemap.md)
      + [文氏圖表](../analysis-workspace/visualizations/venn.md)
   + 面板 {#panels}
      + [概觀](../analysis-workspace/c-panels/panels.md)
      + [空白面板](../analysis-workspace/c-panels/blank-panel.md)
      + [歸因](../analysis-workspace/c-panels/attribution.md)
      + [實驗](../analysis-workspace/c-panels/experimentation.md)
      + [自由格式](../analysis-workspace/c-panels/freeform-panel.md)
      + [媒體平均分鐘觀眾數](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [媒體同時檢視者](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [媒體播放時間](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [下一個或上一個項目](../analysis-workspace/c-panels/next-previous.md)
      + [快速深入分析](../analysis-workspace/c-panels/quickinsight.md)
   + 鑑選和共用 {#curate-share}
      + [概觀](../analysis-workspace/curate-share/send-schedule-files.md)
      + [組織專案](../analysis-workspace/curate-share/curate.md)
      + [共用專案](../analysis-workspace/curate-share/share-projects.md)
      + [建立分享連結](../analysis-workspace/curate-share/shareable-links.md)
      + [唯讀專案](../analysis-workspace/curate-share/view-only-projects.md)
      + [產生簡報](/help/analysis-workspace/curate-share/generate-presentations.md)
   + 匯出 {#export}
      + [概觀](../analysis-workspace/export/export-project-overview.md)
      + [下載](../analysis-workspace/export/download-send.md)
      + [傳送和排程](../analysis-workspace/export/t-schedule-report.md)
      + [匯出至雲端](../analysis-workspace/export/export-cloud.md)
   + 歸因 {#attribution}
      + [歸因概觀](../analysis-workspace/attribution/overview.md)
      + [模型、容器及回顧期間](../analysis-workspace/attribution/models.md)
      + [演算法歸因](../analysis-workspace/attribution/algorithmic.md)
      + [最佳做法](../analysis-workspace/attribution/best-practices.md)
      + [常見問題集](../analysis-workspace/attribution/faq.md)
   + 異常偵測 {#anomaly-detection}
      + [概觀](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [檢視異常](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [統計技術](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + 預測 {#forecasting}
      + [概觀](../analysis-workspace/c-forecast/forecasting.md)
      + [檢視預測](../analysis-workspace/c-forecast/view-forecasts.md)
      + [統計技術](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [使用者偏好設定](../analysis-workspace/user-preferences.md)
   + 工作區常見問題及更多資訊 {#workspace-faq}
      + [常見問題集](../analysis-workspace/workspace-faq/faq.md)
      + [效能最佳化](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [錯誤和疑難排解](../analysis-workspace/workspace-faq/error-messages.md)
      + [限制](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [需求](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [協助工具](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Content Analytics {#content-analytics}
   + [概觀](/help/content-analytics/content-analytics.md)
   + 報告 {#report}
      + [概觀](/help/content-analytics/report/report.md)
      + [元件](/help/content-analytics/report/components.md)
   + 設定 {#configuration}
      + [概觀](/help/content-analytics/config/configuration.md)
      + [引導式設定](/help/content-analytics/config/guided.md)
      + [手動設定](/help/content-analytics/config/manual.md)
      + [資料收集](/help/content-analytics/config/datacollection.md)

+ Analytics 儀表板 {#cja-dashboards}
   + [概觀](../mobile-app/home.md)
   + [評選人任務](../mobile-app/curator.md)
   + [建立行動計分卡](../mobile-app/create-scorecard.md)
   + [管理行動計分卡](../mobile-app/manage-scorecard.md)
   + [設定使用儀表板的主管](../mobile-app/set-up-execs.md)
   + [高階主管使用者快速入門指南](../mobile-app/executive.md)

+ 引導式分析 {#guided-analysis}
   + [概觀](../guided-analysis/overview.md)
   + [積極成長](../guided-analysis/types/active-growth.md)
   + [轉換趨勢](../guided-analysis/types/conversion-trends.md)
   + [參與](../guided-analysis/types/engagement.md)
   + [首次使用影響](../guided-analysis/types/first-use-impact.md)
   + [頻率](../guided-analysis/types/frequency.md)
   + [漏斗](../guided-analysis/types/funnel.md)
   + [淨增長](../guided-analysis/types/net-growth.md)
   + [發行影響](../guided-analysis/types/release-impact.md)
   + [保留](../guided-analysis/types/retention.md)
   + [時間軸](../guided-analysis/types/timeline.md)
   + [趨勢](../guided-analysis/types/trends.md)
   + [產業使用案例](../guided-analysis/industry-use-cases.md)
   + [常見問題](../guided-analysis/faq.md)

+ 元件 {#cja-components}
   + [概觀](../components/overview.md)
   + [使用元件](../components/use-components-in-workspace.md)
   + [新增元件說明](../components/add-component-descriptions.md)
   + 註解 {#annotations}
      + [概觀](../components/annotations/overview.md)
      + [建立註解](../components/annotations/create-annotations.md)
      + [管理註解](../components/annotations/manage-annotations.md)
      + [檢視註解](../components/annotations/view-annotations.md)
      + [行動計分卡註解](../components/annotations/mobile-annotations.md)
   + 客群 {#audiences}
      + [客群概觀](../components/audiences/audiences-overview.md)
      + [建立及發佈客群](../components/audiences/publish.md)
      + [管理客群](../components/audiences/manage.md)
   + 維度 {#dimensions}
      + [概觀](../components/dimensions/overview.md)
      + [預覽維度](../components/dimensions/view-dimensions.md)
      + [劃分維度](../components/dimensions/t-breakdown-fa.md)
      + [時間分隔維度](../components/dimensions/time-parting-dimensions.md)
      + [高基數維度](../components/dimensions/high-cardinality.md)
   + [量度](../components/apply-create-metrics.md)
   + 區段 {#segments}
      + [概觀](/help/components/segments/seg-overview.md)
      + [建立區段](/help/components/segments/seg-create.md)
      + [建置區段](/help/components/segments/seg-builder.md)
      + [快速區段](/help/components/segments/seg-quick.md)
      + [循序區段](/help/components/segments/seg-sequential-build.md)
      + [共用區段](/help/components/segments/seg-share.md)
      + [標記區段](/help/components/segments/seg-tag.md)
      + [劃分區段清單](/help/components/segments/seg-filter.md)
      + [將區段標示為我的最愛](/help/components/segments/seg-favorite.md)
      + [核准區段](/help/components/segments/seg-approve.md)
      + [複製區段](/help/components/segments/seg-copy.md)
      + [管理區段](/help/components/segments/seg-manage.md)
      + [運算子](/help/components/segments/seg-operators.md)
      + [使用區段](/help/components/segments/seg-use.md)
   + 計算量度 {#cja-calcmetrics}
      + [概觀](../components/calc-metrics/calc-metr-overview.md)
      + 工作流程 {#cm-workflow}
         + [建立計算量度](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [尋找量度](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [建置計算量度](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [簡單範例](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [更複雜的範例](../components/calc-metrics/cm-workflow/cm-orders-participation.md)
         + [量度類型和歸因](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [參與率量度](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [區段量度](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [堆疊和取代區段](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [篩選計算量度](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [將計算量度標示為我的最愛](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [複製計算量度](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [使用函數](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [標記計算量度](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [核准計算量度](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [共用計算量度](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [管理計算量度](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [範例](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [計算量度範本](../components/calc-metrics/default-calcmetrics.md)
      + [基本函數](../components/calc-metrics/cm-functions.md)
      + [進階函數](../components/calc-metrics/cm-adv-functions.md)
   + 日期範圍 {#cja-date-ranges}
      + [概觀](../components/date-ranges/overview.md)
      + [建立日期範圍](../components/date-ranges/create.md)
      + [管理日期範圍](../components/date-ranges/manage.md)
      + [日期比較](../components/date-ranges/time-comparison.md)
      + [範例](../components/date-ranges/custom-date-ranges.md)
   + 警報 {#alerts}
      + [概觀](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [建立警報](/help/components/c-intelligent-alerts/alert-builder.md)
      + [管理警報](/help/components/c-intelligent-alerts/alert-manager.md)
      + [功能比較 ](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [使用案例](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + 匯出 {#exports}
      + [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)
      + [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)
      + [管理雲端匯出位置](/help/components/exports/manage-export-locations.md)
      + [管理匯出](/help/components/exports/manage-exports.md)
      + [管理匯出記錄](/help/components/exports/manage-export-logs.md)
      + [疑難排解匯出](/help/components/exports/troubleshoot-exports.md)
   + 資料字典 {#data-dictionary}
      + [概觀](../components/data-dictionary/data-dictionary-overview.md)
      + [檢視資料字典中的元件資訊](../components/data-dictionary/view-data-dictionary.md)
      + [編輯資料字典中的元件條目](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [監視資料字典健康狀況](../components/data-dictionary/monitor-data-dictionary-health.md)
   + 即時報告 {#real-time-reporting}
      + [概觀](/help/components/real-time/real-time.md)
      + [使用即時報告](/help/components/real-time/use-real-time.md)
   + [已排程的專案](../components/scheduled-projects-manager.md)
+ Report Builder {#cja-reportbuilder}
   + [概觀](../report-builder/rb-overview.md)
   + [Report Builder 設定](../report-builder/report-builder-setup.md)
   + [建立資料區塊](../report-builder/create-a-data-block.md)
   + [Report Builder 中心](../report-builder/report-builder-hub.md)
   + [選取資料檢視](../report-builder/select-data-view.md)
   + [選取日期範圍](../report-builder/select-date-range.md)
   + [使用區段](../report-builder/work-with-filters.md)
   + [篩選器維度](../report-builder/filter-dimensions.md)
   + [管理資料區塊](../report-builder/manage-reportbuilder.md)
   + [安排用於電子郵件的活頁簿](../report-builder/schedule-reportbuilder.md)
   + [安排用於雲端匯出的活頁簿](../report-builder/report-builder-export.md)
   + [管理活頁簿排程](/help/report-builder/manage-schedules-reportbuilder.md)
   + [受限制的標籤](../report-builder/restricted-labels.md)
   + [Report Builder 設定](../report-builder/report-builder-settings.md)


+ 報告活動管理器 {#reporting-activity-manager}
   + [概觀](../reporting-activity-manager/reporting-activity-overview.md)
   + [檢視報告活動](../reporting-activity-manager/reporting-activity.md)
   + [取消報告請求](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ 拼接 {#stitching}
   + [概觀](/help/stitching/overview.md)
   + [依欄位匯整](/help/stitching/fbs.md)
   + [依圖表匯整](/help/stitching/gbs.md)
   + [使用匯整](/help/stitching/use-stitching.md)
   + [使用匯整](/help/stitching/use-stitching-ui.md)
   + [建立和管理拼接資料集](/help/stitching/stitching-ui.md)
   + [驗證拼接](/help/stitching/validate.md)
   + [常見問題](/help/stitching/faq.md)

+ Adobe 整合 {#integrations}
   + [概觀](/help/integrations/overview.md)
   + [整合 Adobe Analytics](/help/integrations/aa.md)
   + [整合 Target](/help/integrations/at.md)
   + [整合 Journey Optimizer 資料](/help/integrations/ajo.md)
   + [整合決策管理資料](/help/integrations/ajo-od.md)
   + [整合 Customer AI](/help/integrations/customer-ai.md)
   + [整合 Adobe Advertising](/help/integrations/advertising.md)

+ 資料治理 {#cja-privacy}
   + [資料控管](../privacy/privacy-overview.md)
   + [稽核記錄](../privacy/audit-log.md)
   + [客戶自控金鑰](../privacy/cmk.md)

+ 使用案例 {#cja-usecases}
   + [Customer Journey Analytics 使用案例](../use-cases/cja-usecases.md)
   + Adobe Analytics 資料 {#aa-data}
      + [使用行銷管道維度](../use-cases/aa-data/marketing-channels.md)
      + [結合報告套裝與不同的結構描述](../use-cases/aa-data/combine-report-suites.md)
   + B2B {#b2b}
      + [人員型 B2B 專案範例](../use-cases/b2b/example.md)
      + B2B Edition {#b2b-edition}
         + [使用案例概觀](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)
         + [設定](/help/use-cases/b2b/b2b-edition/setup.md)
         + [將帳戶行銷最佳化](/help/use-cases/b2b/b2b-edition/optimize-account-marketing.md)
         + [拓展重點客戶](/help/use-cases/b2b/b2b-edition/grow-key-accounts.md)
         + [建置產品價值](/help/use-cases/b2b/b2b-edition/build-product-value.md)
   + 複雜的資料 {#complex-data}
      + [使用物件陣列](../use-cases/object-arrays.md)
   + 跨管道的資料 {#cross-channel}
      + [跨管道分析資料](../use-cases/cross-channel/cross-channel.md)
      + [匯入客服中心和網頁的資料](../use-cases/cross-channel/call-center.md)
   + 資料匯出 {#data-export}
      + [概觀](../use-cases/data-export/overview.md)
      + [BI 擴充功能](../use-cases/data-export/bi-extension.md)
      + [匯出資料集](../use-cases/data-export/export-datasets.md)
      + [匯出完整表格](../use-cases/data-export/export-full-table.md)
      + [查詢服務和匯出資料集](../use-cases/data-export/queryservice-export-datasets.md)
   + 資料攝取 {#data-ingestion}
      + [收錄並使用 Marketo Engage 資料](../use-cases/data-ingestion/marketo.md)
      + [收錄並使用 Experience Platform 對象](../use-cases/data-ingestion/ingest-aep-segments.md)
   + 資料檢視 {#data-views}
      + [資料檢視使用案例](/help/use-cases/data-views/data-views-usecases.md)
      + [使用繫結維度和量度](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [使用摘要資料](/help/use-cases/data-views/summary-data.md)
      + [BI 擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)
   + 衍生欄位 {#derived-fields}
      + [LLM和AI產生的流量報告](/help/use-cases/ai-traffic.md)
      + [報告目標](../use-cases/goals-using-derived-fields.md)
   + 產品分析 {#product-analysis}
      + [產品分析](/help/use-cases/product-analysis.md)
   + 拼接 {#stitching}
      + [共用裝置](/help/use-cases/stitching/shared-devices.md)
   + 第三方資料 {#third-party}
      + [概觀](/help/use-cases/third-party/overview.md)
      + Google Analytics {#ga}
         + [從 Google Analytics 移轉資料](/help/use-cases/third-party/ga/overview.md)
         + [攝取 Google Analytics 歷史資料](/help/use-cases/third-party/ga/backfill.md)
         + [設定 Google Analytics 串流資料](/help/use-cases/third-party/ga/streaming.md)
         + [報告 Google Analytics 資料](/help/use-cases/third-party/ga/report.md)
      + Quantum Metric {#qm}
         + [概觀](/help/use-cases/third-party/quantum-metric/qm-overview.md)
         + [連結工作階段重播](/help/use-cases/third-party/quantum-metric/tie-session-replays.md)
         + [使用熱度圖](/help/use-cases/third-party/quantum-metric/heatmap.md)
         + [新增摩擦事件](/help/use-cases/third-party/quantum-metric/friction-events.md)
         + [來源連接器](/help/use-cases/third-party/quantum-metric/source-connector.md)

+ Labs {#labs}
   + [Labs 使用手冊](../labs/labs.md)

+ 疑難排解 {#troubleshooting}
   + [比較Source聯結器資料](../troubleshooting/compare.md)
   + [量度和客群的一致性](../troubleshooting/consistency-rcdp-cja.md)
   + [缺乏權限](../troubleshooting/lack-of-permissions.md)

+ 技術說明 {#technotes}
   + [存取控制](../technotes/access-control.md)
   + [資料中心](../technotes/data-centers.md)
   + [刪除關聯](../technotes/deletion.md)
   + [網域](../technotes/domains.md)
   + [字彙表](../technotes/glossary.md)
   + [護欄](../technotes/guardrails.md)
   + [IP 位址](../technotes/ip-addresses.md)
   + [效能最佳化](../technotes/optimizing-performance.md)
   + [管理使用情況](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
