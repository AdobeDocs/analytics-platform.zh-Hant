---
title: Customer Journey Analytics 文件更新
description: 列出 2019 年 12 月以來 Customer Journey Analytics 文件集的內容更新。
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: 5f02b6eff63f7efcfbec586186506f2c50ec52d7
workflow-type: tm+mt
source-wordcount: '4216'
ht-degree: 99%

---

# Customer Journey Analytics - 文件更新

Customer Journey Analytics 文件從開始建立以來完成以下更新。

## 2024

| 功能 | 說明 |
| --- | --- |
| **2024 年 11 月** | |
| BI 擴充功能使用案例 | 針對BI工具(例如Power BI案頭版和Tableau案頭版)的多個[BI擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)的檔案。 |
| 拼接和隱私權要求 | 新增通知，說明因為隱私權要求而造成[拼接過程中即將發生的變更](/help/stitching/faq.md#frequently-asked-questions)。 |
| **2024 年 10 月** | |
| 共用裝置 | 新增了[使用案例文章](/help/use-cases/stitching/shared-devices.md)，提供有關共用裝置的背景、如何使用拼接處理和緩解來自共用裝置的資料，以及使用查詢服務了解資料中的共用裝置暴露情況。 |
| 有關 Analysis Workspace Performance 請求因素的新資訊 | [Analysis Workspace 效能最佳化](/help/technotes/optimizing-performance.md)文章中的新[請求因素](/help/technotes/optimizing-performance.md#request-factors)部分介紹了如何處理請求以及影響處理時間的各種因素。 |
| Workspace 和元件 | 重新整理了有關 Analysis Workspace 專案 (專案、視覺效果和面板) 與元件 (註解、維度、(經計算的) 量度、篩選器、日期範圍、警報、已排程專案和客群) 的文件。 |
| 引導式分析 | 已將文件更新為可從 Analysis Workspace 內部使用[引導式分析](/help/guided-analysis/overview.md)。 |
| **2024 年 9 月** | |
| 摘要資料更新 | 已更新摘要資料文章，其中包含有關在報告摘要資料時如何正確使用[查詢資料](/help/data-views/summary-data.md#lookup-data)的資訊。 |
| BI 擴充功能更新 | 在 BI 擴充功能文件中新增[預設和限制](/help/data-views/bi-extension.md#defaults-and-limitations)區段。 |
| 警報 | 將 Customer Journey Analytics 中現已提供的[警報](/help/components/c-intelligent-alerts/intelligent-alerts.md)功能新增到文件。 |
| **2024 年 8 月** | |
| B2B 專案範例 | 新增[使用案例](/help/use-cases/b2b/example.md)，記錄如何使用新的[轉換資料集以進行 B2B 查詢](/help/connections/transform-datasets-b2b-lookups.md)功能，在 Customer Journey Analytics 中設定、配置和報告基於設定檔 (個人) 層級的 B2B 資料。 |
| 更新了資料匯出使用案例 | 新增更多詳細的查詢範例到[查詢服務 (資料蒸餾器) 和匯出資料集](/help/use-cases/data-export/queryservice-export-datasets.md)，以說明如何使用回顧期間將歸因正確套用至工作階段。 |
| 摘要資料 | 新增有關[摘要資料](/help/data-views/summary-data.md)、[摘要資料群組元件設定](/help/data-views/component-settings/summary-data-group.md)和[摘要資料使用案例](/help/use-cases/data-views/summary-data.md)的文件。 |
| **2024 年 7 月** | |
| 已新增快速計算量度的相關資訊。 | 已更新[量度](/help/components/apply-create-metrics.md)中的資訊，以釐清這兩者之間的差異：[在計算量度產生器中建立的計算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects)，[在單一專案中作為快速計算量度建立的計算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)。也新增更多有關如何建立快速計算量度的詳細資料。<p>在計算量度產生器中建立的計算量度可在元件清單中使用，並可套用到整個組織的專案，而作為快速計算量度建立的計算量度只能在建立它們的專案中使用。</p><p>也更新[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中的資訊以做出類似的釐清。</p> |
| 衍生欄位移除重複資料功能 | 新增有關衍生欄位[移除重複資料](/help/data-views/derived-fields/derived-fields.md#deduplicate)功能的文件。 |
| 已更新常見錯誤訊息 | 對[常見錯誤訊息](/help/analysis-workspace/workspace-faq/error-messages.md)進行了小幅更新。 |
| **2024 年 6 月** | |
| 已更新提及串流媒體功能的產品名稱 | 當提到專門收集串流媒體資料並將其顯示在 Analysis Workspace 的一組串流媒體功能時，出現「媒體分析」和「串流媒體」的地方將替換為名稱「串流媒體收集附加元件」。 <p>這些更新可在 Customer Journey Analytics 文件以及[串流媒體收集附加元件之文件](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-overview)中取得。</p> |
| 圖表式匯整 | 以圖表式匯整簡介更新和重組[匯整文件](/help/stitching/overview.md)。 |
| AI 助理 | 新增有關 Customer Journey Analytics 之 AI 助理的[文件](../ai-assistant.md)。 |
| 轉換資料集以進行 B2B 查詢 | 新增有關如何使用 B2B 查詢資料集的轉換來支援[在 B2B 資料上進行人員型查詢](/help/connections//transform-datasets-b2b-lookups.md) (包括帳戶、機會、行銷清單和行銷活動)。 |
| 衍生欄位函數和函數範本 | 新增有關其他衍生欄位函數 ([數學](/help/data-views/derived-fields/derived-fields.md#math)、[下一個或上一個](/help/data-views/derived-fields/derived-fields.md#next-or-previous)和[總結](/help/data-views/derived-fields/derived-fields.md#summarize)) 及 [函數範本](/help/data-views/derived-fields/derived-fields.md#function-templates)的文件。 |
| **2024 年 5 月** | |
| Target 整合 | 在有關如何整合 Target 和 Customer Journey Analytics 的 [Adobe 整合區段中新增文章](/help/integrations/at.md)。 |
| 使用組織政策限制時，將 Customer Journey Analytics 報告匯出到 Google 雲端平台時的所需資訊 | 將 Adobe 擁有的 Google 雲端平台組織 ID 新增至[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)文件，以便將 Customer Journey Analytics 報告匯出至 Google 雲端平台。 <p>只有當組織在 Google Cloud Platform 中使用[組織原則限制](https://cloud.google.com/storage/docs/org-policy-constraints)時才需要此資訊。</p> |
| 有關將元件新增至專案的文件 | 新增了有關如何[將各種類型的元件新增至 Analysis Workspace 中的專案](/help/components/use-components-in-workspace.md)的一般資訊。 |
| 資料匯出使用案例 | 一組新文章，說明[資料匯出使用案例](/help/use-cases/data-export/overview.md)以及如何使用 Experience Platform 和 Customer Journey Analytics 功能來實施這些使用案例 |
| 關於從 Adobe Analytics 升級到 Customer Journey Analytics 的新文件 | 對於從 Adobe Analytics 升級到 Customer Journey Analytics 的組織來說，根據組織目前的 Adobe Analytics 實作和長期目標，有多種升級選項和許多需要牢記的考量事項。<p>現在提供新的文件資源來協助您更加瞭解：</p><ul><li>存在的各種升級路徑</li><li>根據組織目前的 Adobe Analytics 實施可以使用哪些升級路徑</li><li>每種升級路徑的優點和缺點</li><li>每個升級路徑的逐步操作指導</li><li>處理歷史資料的考量事項</li><li>及更多內容！</li></ul><p>[開始升級到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)。</p> |
| 關於自訂日期範圍的更新文件 | 更新螢幕擷圖以及與[範例日期範圍](/help/components/date-ranges/custom-date-ranges.md)相關的程序，以符合目前的產品特色和設計。 |
| 有關維度的概觀資訊 | 新增有關[維度](/help/components/dimensions/overview.md)的資訊。 |
| 來源連接器範例 | 說明如何[使用來源連接器](/help/data-ingestion/sources.md#use-a-source-connector)擷取資料時，新增可用的來源連接器範例。 |
| **2024 年 4 月** | |
| 預測統計技術 | 新增文章以說明[用於預測服務的統計技術](../analysis-workspace/c-forecast/statistics-forecasting.md)。 |
| 新增建議完整表格匯出以用於高基數維度的資訊 | 在[高基數維度的最佳做法](/help/components/dimensions/high-cardinality.md)中新增項目符號，以建議對高基數維度使用完整表格匯出。 |
| 在行動計分卡中新增有關智慧型註解的文件 | [智慧型註解](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)可協助非分析師在沒有分析師協助下更了解他們的資料。 |
| Adobe Product Analytics 功能的新文件 | <ul><li>[功能矩陣](/help/guided-analysis/types/funnel.md)</li><li>強化[保留](/help/guided-analysis/types/retention.md)</li><li>[強化漏斗中的深入解析](/help/guided-analysis/types/funnel.md)</li><li>比較單一漏斗步驟中的事件</li></ul> |
| **2024 年 3 月** | |
| 關於「使用於」欄的使用情況資訊，僅從 2023 年 9 月開始提供。 | 澄清[專案登陸頁面](/help/getting-started/landing.md)上的「**使用於**」欄的使用情況資訊只能追溯到 2023 年 9 月。 |
| 新增有關針對僅限專案的 Workspace 元件之權限強化的文件 | 如果您與其他使用者共用專案，這些使用者可以編輯[快速篩選器](/help/components/filters/quick-filters.md)以及共用專案中嵌入的其他僅限專案的元件。 |
| **2024 年 2 月** | |
| 專案共用文件更新 | 新增有關如何[檢視與您共用之專案](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you)的資訊。<p>同時也簡化有關[共用個別或多個專案](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role)的資訊。</p> |
| 新增設定雲端匯出位置時將檔案上傳到 Azure SAS 和 Azure RBAC 的權限要求 | 新增在[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)和[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)時，將檔案上傳到 Azure SAS 和 Azure RBAC 的確切權限要求。 |
| 新增設定雲端匯出位置時，將檔案上傳到 Amazon S3 角色 ARN 和 GCP 貯體的權限要求 | 新增[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)時，將檔案上傳到 Amazon S3 角色 ARN 和 Google Cloud Platform 貯體時的確切權限要求。 |
| 澄清產品管理員始終有權限將完整表格匯出 | 進行以下變更，以釐清獲指派產品管理員角色的使用者預設擁有從 Analysis Workspace 匯出完整表格的存取權： <ul><li>新增一個新項目符號至[產品管理員預設權限](/help/technotes/access-control.md#product-admin-default-permissions)。</li><li>在[將完整表格匯出至雲端的最低要求](/help/analysis-workspace/export/export-cloud.md#minimum-requirements)下方新增註釋。</li></ul> |
| 釐清從 Adobe Analytics 移轉元件期間會重新建立區段 | 在 [Adobe Analytics 使用者的使用手冊](/help/getting-started/aa-to-cja-user.md)中，釐清在元件移轉過程中會在 Adobe Analytics 中自動重新建立區段，因此無需手動重新建立。 |
| 略過記錄詳細資料 | 新增有關在連線中略過記錄詳細資料功能的文件。請參閱[連線詳細資料](../connections/manage-connections.md#connection-details)以了解更多資訊。 |
| **2024 年 1 月** | |
| 預測 | 新增有關[預測](../analysis-workspace/c-forecast/forecasting.md) (Analysis Workspace 的新功能) 的文件，用於使用任何支援的時間詳細程度 (每小時、每天、每週、每月和每年) 為自由格式表格和折線圖預測標準或計算量度。 |
| 更新有關匯出完整表格時新增帳戶和位置的文件 | 更新文件，以反映[從 Analysis Workspace 匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)時，在設定新帳戶或位置時的小幅度介面更新。<p>新的&#x200B;[!UICONTROL **新增帳戶**]&#x200B;選項現在可以在&#x200B;[!UICONTROL **帳戶**]&#x200B;下拉式選單中使用。[!UICONTROL **新增位置**]&#x200B;選項 (先前作為&#x200B;[!UICONTROL **位置名稱**]&#x200B;下拉式選單旁邊的按鈕提供) 現在可在選單內使用。 |
| 從 Adobe Analytics 移轉時的新元件移轉資訊 | 新增資訊至[從 Adobe Analytics 發展而來](/help/getting-started/aa-to-cja.md)，以參考新的[元件移轉](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)功能 (記錄在 Adobe Analytics 管理員指南中)。 |
| 釐清部分資訊僅供管理員使用 | 新增資訊，說明[計算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)和[篩選器管理器](/help/components/filters/manage-filters.md)內所述的「上次使用」和「使用於」欄位僅供系統管理員使用。 |
| 匯出資料集所需的權限 | 新增資訊，說明將資料集匯出至雲端目標[所需的權限](/help/technotes/access-control.md)。 |
| 管理連線 | 根據客戶意見回饋更新[管理連線](../connections/manage-connections.md)文章。 |
| 衍生欄位 | 新增功能[限制](/help/data-views/derived-fields/derived-fields.md#limitations)摘要，以及說明如何決定[運算子](/help/data-views/derived-fields/derived-fields.md#operators) (用於函數) 的數量。 |

{style="table-layout:auto"}


## 2023

| 功能 | 說明 |
| --- | --- |
| **2023 年 12 月** | |
| 資料中心 | 新增有關 Customer Journey Analytics [託管位置](../technotes/data-centers.md)的文章。 |
| 護欄 | 新增列出 Customer Journey Analytics [護欄](../technotes/guardrails.md)的文章。 |
| 貨幣轉換更新 | 釐清有關如何[設定貨幣轉換](/help/data-views/component-settings/format.md)的文件。 |
| 異常偵測文件的更新 | 異常偵測的文件先前位於有關虛擬分析人員的區段中。以下是所做的變更： <ul><li>術語 Virtual Analyst 已從文件中刪除。</li><li>「[異常偵測](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)」的區段直接移至 Analysis Workspace 區段下方。</li></ul> |
| **2023 年 10 月** | |
| 使用衍生欄位來設定目標 | 新增[使用案例](../use-cases/goals-using-derived-fields.md)文章，說明如何使用衍生欄位來設定目標並加以報告。 |
| 將完整表格匯出至雲端 | 新增有關將包含數百萬 Workspace 列的完整表格匯出到雲端目標的文件。 <p>匯出完整表格可提供在 Workspace 中設計之資料表格的一次性或排程傳送，最多可支援五個劃分、五個量度、篩選器和計算量度，且全部都可以在串連表格中完成。這是 Adobe Analytics 中 Data Warehouse 報告的演化，其中包含許多經常要求且目前在 Data Warehouse 中尚未提供的新功能。</p><p>如需更多資訊，請參閱[將 Customer Journey Analytics 報告匯出至雲端](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html)。 |
| 報告活動管理器 | 新增報告活動管理器的文件。 <p>報告活動管理器可讓您查看組織中每個連線的報告容量。它為管理員提供報告使用量的詳細可見度，以便在尖峰報告時段輕鬆診斷和修正容量問題。</p> <p>已新增下列新文章：<ul><li>[報告活動管理器概觀](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md)</li><li>[在報告活動管理器中取消請求](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| 在管理頁面上新增欄 | 記錄現在可在[計算量度管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html)和[篩選器管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html)記錄中使用的新欄。 |
| 與 Adobe Analytics 比較 | 新增[概觀頁面](../getting-started/aa-vs-cja/overview.md)作為比較和理解 Customer Journey Analytics 和 Adobe Analytics 之間差異的簡介。 |
| 其他衍生欄位功能 | 更新有關新 [`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup) 函數的文件。 |
| **2023 年 9 月** | |
| 已更新「媒體播放時間」面板的文章結構 | 已移除名為「媒體播放時間」的資料夾，並將該資料夾的內容合併為一篇文章：[「媒體播放時間」面板](/help/analysis-workspace/c-panels/media-playback-time-spent.md)。 <p>此變更會更符合其他面板的文件。</p> |
| 附加衍生欄位功能 | 已更新新的 [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase) 和 [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim) 功能，以及新增到 [`Classify`](/help/data-views/derived-fields/derived-fields.md#classify) 功能的附加 CSV 功能的文件。 |
| 地區資料收集 | 已更新的[常見問題](../getting-started/cja-faq.md#12-regional-data-collection)，含有使用 Customer Journey Analytics 時關於區域資料收集的資訊。 |
| **2023 年 8 月** | |
| 「媒體播放時間」面板 | 已更新[媒體播放時間面板](/help/analysis-workspace/c-panels/media-playback-time-spent.md)的內容以提高可讀性。 |
| Report Builder 改良功能 | 已更新[排程活頁簿](/help/report-builder/schedule-reportbuilder.md)的內容，提供關於下載已排程任務的資訊。已更新[建立資料區塊](/help/report-builder/create-a-data-block.md)的內容，提供關於使用開始日期作為維度的資訊。 |
| 已移動關於管理已排程專案的內容 | 在「Analytics 元件指南」中建立了一篇新文章，名為[已排程專案](/help/components/scheduled-projects-manager.md)。此內容之前位於「Analytics 工具指南」的[已排程專案](/help/analysis-workspace/export/t-schedule-report.md)文章。 |
| Adobe Customer Journey Analytics 功能支援 | 相較於 Adobe Analytics，Customer Journey Analytics 已在工作階段化功能的&#x200B;*以新方式支援*&#x200B;表格中新增更多資訊。[了解更多](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| 從 Adobe Analytics 發展而來 | 已更新 *(重新) 設定行銷管道*&#x200B;區段，並引用衍生欄位行銷管道功能範本。[了解更多](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| 行動應用程式和其他平台的資料擷取快速入門指南 | 新增額外的資料擷取快速入門指南，旨在概述如何在 Customer Journey Analytics 中擷取和使用來自行動應用程式或其他平台 (例如桌面應用程式、遊戲主機上的遊戲、機上盒和 IoT 裝置上的應用程式) 的資料。[了解更多](../data-ingestion/data-ingestion.md) |
| **2023 年 7 月** | |
| 工作階段設定 | 新增此資料檢視設定的主題。[了解更多](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics 是一種與 Customer Journey Analytics 跨管道資料和深入見解進行互動的新方式。這些新功能使產品團隊能夠透過[引導式分析](/help/guided-analysis/overview.md)工作流程取得有關其產品體驗的自助資料和深入見解。 |
| 衍生欄位 | [衍生欄位](/help/data-views/derived-fields/derived-fields.md)可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。 |
| 已擴大對輪廓和查詢資料的查詢支援 | 提供功能，可將資料集新增為輪廓或查詢資料集內的欄位查詢。之前僅支援事件資料集。[了解更多](/help/connections/create-connection.md) |
| Report Builder 改良功能 | <ul><li>[從儲存格篩選多個資料區塊](/help/report-builder/select-data-view.md)</li><li>[顯示和隱藏行與欄標題](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html#build-the-data-block)</li></ul> |
| Edge Network 地理位置查詢 | [資料流設定](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html)現已具備地理位置查詢服務，提供統一的地理位置資料。 |
| **2023 年 6 月** | |
| 跨管道分析與彙整 | 因為預期即將進行的變更會啟用彙整並進一步釐清如何使用彙整來提升跨管道分析，我們編輯了與跨管道分析功能相關的文件，以便參照[跨管道分析](../use-cases/cross-channel/cross-channel.md)做為 Customer Journey Analytics 功能和使用案例，並參照[彙整](../stitching/overview.md)做為完成此目標的重要功能。 |
| PowerBI 和 Tableau 可存取 Customer Journey Analytics 資料檢視 | Customer Journey Analytics BI 擴充功能可讓 SQL 存取您在 Customer Journey Analytics 中定義的資料視圖。[了解更多](/help/data-views/bi-extension.md) |
| Adobe Journey Optimizer 資料檢視 | Customer Journey Analytics 管理員可以存取 Customer Journey Analytics 中一些額外的資料檢視，標題為「AJO 資料檢視 (沙箱名稱)」。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/reporting/channel-report/reporting-configuration)。 |
| 貨幣轉換 | 已更新[貨幣轉換](../data-views/component-settings/format.md#currency)支援的文件。 |
| 計算量度更新 | 已針對計算量度文件進行以下更新，使其與目前的 Customer Journey Analytics 功能維持一致： <ul><li>已更新 Customer Journey Analytics 中可用的[預設計算量度](/help/components/calc-metrics/default-calcmetrics.md)清單</li><li>已更新各種計算量度文章中的螢幕擷取畫面和程序 </li></ul> |
| **2023 年 5 月** | |
| 深度連結 (行動應用程式) 文件 | 可讓使用者傳送計分卡連結，這些連結會直接導向應用程式中的計分卡專案。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) |
| Report Builder 中關於「從儲存格中選取資料檢視」的文件 | 此功能可讓使用者從儲存格中選取資料區塊的資料檢視。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) |
| Analytics 儀表板應用程式 (行動應用程式) 更新首頁的文件 | 更新的首頁可讓您在一個綜合計分卡清單中檢視所有計分卡。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) |
| 最佳化更新 | 已更新關於[最佳化 Customer Journey Analytics 效能](/help/technotes/optimizing-performance.md)的文章 |
| Analysis Workspace 概觀 | 更新 [Analysis Workspace 概觀](/help/analysis-workspace/home.md)以包含更多一般概觀資訊和相關內容的連結。 |
| 建立專案 | 建立新文章，其中詳細說明如何在 Analysis Workspace [建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)。 |
| 排序左側邊欄中的元件 | 已新增排序左側邊欄中元件清單的資訊。請參閱[元件概觀](/help/components/overview.md)中的「搜尋、篩選和排序元件清單」一節。 |
| 從自由格式表格中刪除包含動態維度的列 | 已新增如何使用 x 圖示快速刪除包含動態維度的特定列的資訊。請參閱[篩選和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的「從表格中快速排除特定列」一節。 |
| 在面板中新增視覺效果的按鈕 | 已在 Analysis Workspace 中每個面板底部新增有關新按鈕的資訊，讓您可快速新增視覺效果。請參閱[視覺效果概觀](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)中的「將視覺效果新增到面板」一節。 |
| 智慧標題文件 | 使用台詞視覺效果[自然語言摘要](/help/analysis-workspace/visualizations/intelligent-captions.md)來增強使用者的故事講述效果。 |
| 衍生欄位 | 已新增[衍生欄位](../data-views/derived-fields/derived-fields.md)功能的文章。 |
| **2023 年 4 月** |  |
| 關於使用篩選器做為維度的影片 | 更新關於使用篩選器做為維度的影片 <p>該影片連結自「[建立篩選器](/help/components/filters/create-filters.md)」頁面。</p> <p>以下是影片的直接連結：[在 Analysis Workspace 中使用篩選器做為維度](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html)。</p> |
| 篩選器文件 | 新增說明如何使用[篩選器產生器](/help/components/filters/filter-builder.md)的文章。 <p>簡化了[建立篩選器](/help/components/filters/create-filters.md)和[篩選器概觀](/help/components/filters/filters-overview.md)文件。</p> |
| 實驗面板文件更新 | 新增有關[解釋非隨機維度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html#non-randomized)的章節。 |
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
| 更新至 Audiences 文件 | 有關[延遲的注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)的新章節。 |
| Audiences 文件的更新 | 建立客群之後，Adobe 會[為每個新的 Customer Journey Analytics 客群建立一個 Experience Platform 串流細分群體](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=zh-Hant#after-audience-created)。 |
| Workspace 行事曆和日期範圍 | 更新內容以說明相對日期範圍、公式計算更新和行事曆 UI 變更。查看[關於相對面板日期範圍](/help/components/date-ranges/overview.md#custom-date-ranges)。 |
| Mobile 計分卡 | 新文件部分會說明如何顯示和隱藏比較日期範圍。請參閱 Customer Journey Analytics 中的「[顯示比較日期範圍](/help/mobile-app/create-scorecard.md#show-comparison-dates)」。 |
| **2023 年 1 月** | |
| 篩選和排序表格 | 已更新[篩選和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的內容 (包括新增過程和說明可用選項)。重新命名本文的「分頁、篩選和排序表格」。 |
| 資料擷取快速入門指南 | 新增有關如何在 Customer Journey Analytics 中[擷取和使用資料](/help/data-ingestion/data-ingestion.md)的文件內容。 |
| 工作區資料夾 | [資料夾管理](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)的專用頁面。 |
| 工作區使用者偏好設定 | [偏好設定](/help/analysis-workspace/user-preferences.md)現在提供許多其他使用者偏好設定。 |
| 自動儲存工作區專案 | 已更新內容，在[儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)中加入自動儲存功能。 |
| 登陸頁面 | 新的登陸頁面更新[登陸頁面](/help/getting-started/landing.md)。 |
| 排程活頁簿 | 說明如何在 Report Builder 中[排程活頁簿](/help/report-builder/schedule-reportbuilder.md)的專用頁面。 |
| 針對輪廓及查閱資料集提供物件陣列支援 | 已更新[使用物件陣列](/help/use-cases/object-arrays.md)和[攝取 Adobe Experience Platform 客群](/help/use-cases/data-ingestion/ingest-aep-segments.md)，以反映針對輪廓及查閱資料集的物件陣列支援。 |

{style="table-layout:auto"}

## 2022

| 日期 | 更新說明 |
| --- | --- |
| **2022 年 12 月** |  |
| 2022 年 12 月 16 日 | 新增有關[測量及管理 Customer Journey Analytics 資料使用情況](/help/technotes/estimate-usage.md)的主題。 |
| **2022 年 10 月** | |
| 2022 年 10 月 | 有關[排程專案的密碼保護](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#password)的新主題。此功能支援 [HIPAA 整備程度](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html)。 |
| 2022 年 10 月 | 有關[客戶自控金鑰](/help/privacy/cmk.md)的新主題。此功能支援 [HIPAA 整備程度](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html)。 |
| 2022 年 10 月 | 新增有關 [Customer Journey Analytics 稽核記錄](/help/privacy/audit-log.md)的主題。 |
| 2022 年 10 月 | 新主題：[關鍵量度摘要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html)視覺化。 |
| 2022 年 10 月 | 新章節：[資料檢視中的日期和日期-時間功能](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#date) |
| 2022 年 10 月 | 行動應用程式：新主題：[自訂詳細檢視](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#view-detail-slides)。 |
| 2022 年 10 月 | [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)主題的更新。 |
| **2022 年 9 月** | |
| 2022 年 9 月 | 新增有關[將 Google Analytics 資料移轉到 Customer Journey Analytics](/help/use-cases/ga/overview.md) 的使用案例。 |
| 2022 年 9 月 | Workspace [組合圖表](/help/analysis-workspace/visualizations/combo-charts.md)的新主題。 |
| 2022 年 9 月 | Workspace [實驗面板](/help/analysis-workspace/c-panels/experimentation.md)的新主題。 |
| **2022 年 8 月** | |
| 2022 年 8 月 | 有關 [Analytics 來源連接器的跨區域支援](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)的 Adobe Experience Platform 文章 |
| 2022 年 8 月 | 大幅更新有關 [Customer Journey Analytics 存取控制](/help/technotes/access-control.md)的文章。 |
| 2022 年 8 月 | 新增有關 [Customer Journey Analytics 支援資料控管標籤和原則](/help/data-views/data-governance.md)的文章。 |
| 2022 年 8 月 | 新增[比較透過 Analytics 來源連接器傳遞的 Analytics 資料的術語](/help/getting-started/aa-vs-cja/terminology.md)的文章 |
| 2022 年 8 月 | 新增有關[將對象發佈到即時客戶輪廓](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=zh-Hant)的文件。 |
| **2022 年 7 月** | |
| 2022 年 7 月 | [「媒體播放時間」面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=zh-Hant)文件。 |
| 2022 年 7 月 | [「媒體同時檢閱者」面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=zh-Hant)文件。 |
| 2022 年 7 月 | [第一個工作階段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat)報告文件。 |
| **2022 年 6 月** | |
| 2022 年 6 月 | 關於 [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hant)的新文章 |
| 2022 年 6 月 | 新增 [Adobe Analytics 處理規則、VISTA 和分類與 Analytics 來源連接器的「資料準備」的比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)的文章 |
| 2022 年 6 月 | 新增有關[虛擬報告環境和沙箱環境](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)的文章。 |
| 2022 年 6 月 | 新增有關[比較在 Adobe Analytics 和 Customer Journey Analytics 報告功能的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)文章。 |
| 2022 年 6 月 | 新增有關[結合報告套裝與不同的結構描述](/help/use-cases/aa-data/combine-report-suites.md)的文章。 |
| 2022 年 6 月 | 新增有關[以行動計分卡共用註解](/help/components/annotations/mobile-annotations.md)的文章。 |
| 2022 年 6 月 | 新增有關 [Customer Journey Analytics 中 Analytics Labs](/help/labs/labs.md) 的文章。 |
| 2022 年 6 月 | 新增有關[支援數值欄位做為查閱鍵和查閱值](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#numeric)的區段。 |
| 2022 年 6 月 | 更新[流量視覺效果工作流程](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。 |
| **2022 年 5 月** | |
| 2022 年 5 月 | 大幅更新有關在 Customer Journey Analytics 中[建立連線](/help/connections/create-connection.md)的文章。 |
| 2022 年 5 月 | 新增有關如何[在 Customer Journey Analytics Report Builder 中管理資料區塊](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=zh-Hant)的文章。 |
| 2022 年 5 月 | 新增有關[將 Adobe Experience Platform 客群帶進 Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md) 的文章。 |
| **2022 年 4 月** | |
| 2022 年 4 月 | [維度子字串](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=zh-Hant)文件。 |
| 2022 年 4 月 | 新增 [Adobe Analytics 使用者適用的 Customer Journey Analytics 使用指南](/help/getting-started/aa-to-cja-user.md)。 |
| **2022 年 3 月** | |
| 2022 年 3 月 | 新增 [Customer Journey Analytics 註解 API 文件](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)。 |
| 2022 年 3 月 | 有關[工作區中註解](/help/components/annotations/overview.md)的新文件。 |
| 2022 年 3 月 | 有關[估算連線規模](/help/getting-started/cja-faq.md)的重大更新內容。 |
| **2022 年 2 月** | |
| 2022 年 2 月 | 新增適用於從 Adobe Analytics 移至 Customer Journey Analytics 的管理員指南：[Adobe Analytics 至 Customer Journey Analytics 的發展進程](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html) |
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
| 2021 年 4 月 | 有關「工作區」中[排程報告](/help/analysis-workspace/export/t-schedule-report.md)的新增主題。 |
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
| 2020 年 11 月 13 日 | 新增有關[跨管道分析](/help/stitching/overview.md)的主題，可讓您為資料集的人員 ID 重設金鑰，並啟用多個資料集的無縫結合。 |
| 2020 年 11 月 13 日 | 新增有關[匯入客服中心和 Web 資料](/help/use-cases/cross-channel/call-center.md)的新使用案例。 |
| 2020 年 11 月 10 日 | 新增有關刪除資料元件對[常見問題集](/help/getting-started/cja-faq.md)之影響的區段。 |
| 2020 年 11 月 2 日 | [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)頁面的更新。 |
| 2020 年 11 月 | 新增有關[移除回填限制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#backfill-historical-data)以完成連線的內容。 |
| 2020 年 10 月 7 日 | 新增有關[合併事件資料集](/help/connections/combined-dataset.md)的主題。 |
| 2020 年 9 月 15 日 | 新增有關[資料擷取](/help/data-ingestion/data-ingestion.md)的主題。 |
| 2020 年 9 月 2 日 | 更新有關[使用者權限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hant)的區段。 |
| 2020 年 7 月 | 新增有關[使用者 ID 恆等映射選項](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant)的資訊。 |
| 2020 年 7 月 | 有關[物件陣列](/help/use-cases/object-arrays.md)或「資料階層」的新主題已新增。 |
| 2020 年 4 月 14 日 | 對[建立連線](/help/connections/create-connection.md)主題中最新 UI 的更新。 |
| 2020 年 2 月 27 日 | 更新 [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md) |
| 2019 年 12 月 | Customer Journey Analytics 文件的第一份草稿 |

{style="table-layout:auto"}
