---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陸頁面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: c29b1b8678579b58c42fce2fc02fffd81c1a633f
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 92%

---

# Customer Journey Analytics 指南

本技術文件指南提供 Customer Journey Analytics 的自助協助。Customer Journey Analytics 可讓您將客戶資料從您選擇的任何管道 (線上和離線) 引入 Adob&#x200B;&#x200B;e Experience Platform。然後，就可以像使用 Analysis Workspace 分析現有數位資料一樣來分析這些資料。

Customer Journey Analytics 可讓您控制如何在 Analysis Workspace 中連接任何常見客戶 ID 的線上和離線資料，進而允許您進行歸因、篩選器、流量與流失等分析。進行全部客戶資料的歸因、篩選器、流量與流失等分析。

## 新增功能？

快速一覽 Customer Journey Analytics 產品和文件的最新增強功能！如需功能、改進項目與修正的完整清單，請參閱詳細的[發行說明](../release-notes/latest.md)。請造訪「[文件更新頁面](../release-notes/doc-changes.md)」，了解最新變更內容。

>[!BEGINTABS]

>[!TAB AI 助理]

AI 助理是一種對話式體驗，可讓從業人員快速執行任務，包括理解概念、對問題進行疑難排解或搜尋資訊等。它也可讓非專家執行專家任務，並提高整體工作品質。

[![影像](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB 引導式分析]

引導式分析現在可以直接在 Analysis Workspace 中使用，讓使用者可以建立儀表板，呈現來自面板、視覺化呈現和引導式分析的全方位深入分析。

[![影像](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)


>[!TAB 智慧型字幕v2]

智慧型字幕現在已支援[行](/help/analysis-workspace/visualizations/line.md) （包括多行）、[列](/help/analysis-workspace/visualizations/bar.md)、[水準列](/help/analysis-workspace/visualizations/horizontal-bar.md)、[區域](/help/analysis-workspace/visualizations/area.md) （包括多區域行）、[環圈圖](/help/analysis-workspace/visualizations/donut.md)、[流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[流量](/help/analysis-workspace/visualizations/c-flow/flow.md)視覺效果，並搭配其他介面改良功能。

[![影像](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB 警報]

警報可讓您根據變更的百分比或特定資料點來接收通知。您可以預覽警報觸發的頻率、透過電子郵件或簡訊傳送警報、建立堆疊警報等。

[![影像](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB 摘要資料]

允許您引入沒有人員 ID 的時間序列資料。此時間序列資料可用於支援各種使用案例，例如

- 將高層級效能指標作為事件層級資料的一部分或隨附提供。
- 每小時或每天上傳目標，然後將這些目標與事件層級量度進行對比。

[![影像](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

>[!TAB 圖表式匯整*]

圖表式匯整功能可讓您使用 Experience Platform Identity Service 中的身分識別圖來更清楚地掌握客戶歷程，方法包括： <ul><li>無需擷取、轉換並載入額外資料來反映單一識別碼，即可連接不同識別碼的資料集。</li> <li>在資料集之間共用身分識別，以提高單一資料集的首選或黃金身分識別涵蓋範圍，</li><li>讓 Real-Time Customer Data Platform 和 Journey Optimizer 中建立的輪廓與 Customer Journey Analytics 中的人員保持一致。</li></ul>

[![影像](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_您必須擁有 Prime 套件才能進行圖表式匯整。_*

>[!TAB B2B 查詢]

在設定連線時，您可以轉換特定 B2B 查詢結構描述的資料集，以便在 B2B 資料上更完善地支援人員型查詢。

[![影像](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB 衍生欄位]

新的衍生欄位函數 (數學、下一個或上一個、總結、重複) 和附加函數範本 (如跳出數、易記的資料集名稱、假期季節、每月目標、簡單的機器人偵測等) 現已推出。

[![影像](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB BI 擴充功能*]

BI 擴充功能可讓 SQL 存取您在 Customer Journey Analytics 中定義的資料視圖。您現在可以使用您最愛的BI工具(Power BI Desktop、Tableau Desktop、Looker、Juyter Notebook和RStudio)，根據Customer Journey Analytics使用者在其Analysis Workspace專案中使用的相同資料檢視來建立報告和儀表板。 提供[使用案例](/help/use-cases/data-views/bi-extension-usecases.md)。

[![影像](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_您必須擁有 Select 套件或更高版本才能使用 BI 擴充功能。_*


>[!ENDTABS]

## 從基礎知識開始

首先閱讀以下連結中的資料，進一步了解 Customer Journey Analytics 的性能和功能。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>不只是線上資料</strong><br/>了解 Customer Journey Analytics 與 Adob​​e Analytics 之間的比較、兩者共用哪些功能以及如何使用 Analytics 資料。</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>擷取和使用資料</strong><br/>了解將資料擷取到 Experience Platform 並將其用於 Customer Journey Analytics 分析和報告的選項。</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>引導式分析</strong><br/>了解如何使用工作流程來獲取有關客戶產品體驗的資料和深入解析。透過引導分析進行 Product Analytics...
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>使用 Analysis Workspace 執行基本和進階分析，例如歸因、流程圖和流失圖、維度劃分。</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## 探索文件

了解如何比較 Customer Journey Analytics 和 Adobe Analytics。同時，了解如何在解決方案中取得您的資料，然後準備、檢視、分析大眾化這些資料和產生的報告，並且使這些資料和最終報告普及化。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>與 Adobe Analytics 比較</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概述</a> - <a href="/help/getting-started/aa-to-cja.md">進展</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">使用 Adob​​e e Analytics 資料</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">功能支援</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">術語</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">資料處理</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>連線</strong><br/><a href="/help/connections/overview.md">概述</a> - <a href="/help/connections/create-connection.md">建立</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">Stitch</a> - <a href="/help/connections/combined-dataset.md">合併事件資料集</a> - <a href="/help/connections/standard-lookups.md">標準查詢</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>資料視圖</strong><br/><a href="/help/data-views/data-views.md">概述</a> - <a href="/help/data-views/create-dataview.md">建立或編輯</a> - <a href="/help/data-views/session-settings.md">工作階段設定</a> - <a href="/help/data-views/derived-fields/derived-fields.md">衍生欄位</a> - <a href="/help/data-views/summary-data.md">摘要資料</a> - <a href="/help/data-views/component-reference.md">元件引用</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace 專案</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本 </a>及<a href="/help/analysis-workspace/perform-adv-analysis.md">進階分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">專案</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">視覺化</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">面板</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>引導式分析</strong><br/><a href="/help/guided-analysis/overview.md">概述</a> - <a href="/help/guided-analysis/types/active-growth.md">使用者成長</a> - <a href="/help/guided-analysis/types/trends.md">趨勢</a>  - <a href="/help/guided-analysis/types/funnel.md">漏斗</a> - <a href="/help/guided-analysis/types/release-impact.md">影響</a> - <a href="/help/guided-analysis/industry-use-cases.md">產業使用案例</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>分享、匯出、整合</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">專案</a> - <a href="/help/mobile-app/home.md">Analytics 儀表板</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">雲端匯出</a> - <a href="/help/integrations/overview.md">整合</a>
    </td>
  </tr>
</table>

## 其他資源

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">教學課程</a> - <a href="https://helpx.adobe.com/tw/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 產品說明</a> - <a href="https://helpx.adobe.com/tw/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics 附加元件) 產品說明</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a> - <a href="/help/ai-assistant.md">AI 助理</a>
</td>
<td><strong>資料擷取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概述</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a>  - <a href="/help/data-ingestion/aepmobilesdk.md">行動 SDK</a> - <a href="/help/data-ingestion/batch.md">批次</a> - <a href="/help/data-ingestion/streaming.md">串流</a> -  <a href="/help/data-ingestion/sources.md">來源</a> - <a href="/help/data-ingestion/serverapi.md">伺服器 API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>隨時掌握情況、為社群做出貢獻並提升您的 Customer Journey Analytics 體驗！</b><br>瀏覽 Adob​​e Analytics 社群，以便與其他從業者討論功能。<a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社群！</a></td></tr></tbody></table>
