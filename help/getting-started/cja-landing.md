---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陸頁面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 79234ee442e49ebf7f5a08bd0214e8c9d547485e
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 21%

---

# Customer Journey Analytics 指南

本技術文件指南提供 Customer Journey Analytics 的自助協助。Customer Journey Analytics可將您選擇之任何管道的客戶資料（線上及離線皆可）整合到Adobe Experience Platform中，接著依您目前使用Analysis Workspace分析現有數位資料的方式加以分析。

Customer Journey Analytics 可讓您控制如何在 Analysis Workspace 中連接任何常見客戶 ID 的線上和離線資料，進而允許您所有客戶資料。

## 新增功能

快速一覽Customer Journey Analytics產品和檔案的最新增強功能！ 如需功能、改進項目與修正的完整清單，請參閱詳細的[發行說明](../release-notes/latest.md)。請造訪[文件更新頁面](../release-notes/doc-changes.md)，了解文件的最新變更。

>[!BEGINTABS]

>[!TAB 引導式分析* — 保留率]

一種新的視圖類型，顯示在所需日期範圍內初次參與後傳回的使用者百分比。水平軸表示自使用者初始參與以來的天數。 垂直軸代表再次參與的使用者百分比。

[![影像](assets/learn-more-button.svg)](/help//guided-analysis/types/retention-rates.md)

<span style="color:gray">*_引導式分析屬於Adobe Product Analytics的一部分，是Customer Journey Analytics的付費附加元件。_</span>




>[!TAB 引導式分析* — 趨勢線]

趨勢線覆蓋圖現在可在「使用情況」檢視中使用，以協助描繪出資料中更清晰的模式。 可用的趨勢線型別包括線性、對數及移動平均。

[![影像](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_引導式分析屬於Adobe Product Analytics的一部分，是Customer Journey Analytics的付費附加元件。_</span>


>[!TAB 關鍵量度摘要視覺效果]

使用「關鍵量度摘要」視覺效果時，比較日期範圍現在可以根據您選擇的「比較日期範圍」選項是相對於主要日期範圍還是固定日期範圍自動更新。

[![影像](assets/learn-more-button.svg)](/help/analysis-workspace/visualizations/key-metric.md)

>[!ENDTABS]

## 從基礎知識開始

首先請閱讀以下連結中的資料，以熟悉Customer Journey Analytics功能和特性。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>超越線上資料</strong><br/>瞭解Customer Journey Analytics與Adobe Analytics的比較、共用哪些功能，以及如何使用您的Analytics資料。</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>擷取及使用資料</strong><br/>瞭解您將資料內嵌至Experience Platform並用於分析和報告Customer Journey Analytics的選項。</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>引導式分析</strong><br/>瞭解如何使用工作流程取得有關客戶產品體驗的資料和深入分析。 透過引導式分析進行Product Analytics...
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>使用Analysis Workspace來執行基本和進階分析，例如歸因、流量和流失圖表、維度劃分。</div>
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

瞭解Customer Journey Analytics與Adobe Analytics的比較，以及如何在解決方案中取得您的資料，然後準備、檢視、分析該資料，並將其大眾化，最後形成分析和報表。

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>與Adobe Analytics比較</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概觀</a> - <a href="/help/getting-started/aa-to-cja.md">演化</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">使用Adobe Analytics資料</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">功能支援</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">術語</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">資料處理</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>連線</strong><br/><a href="/help/connections/overview.md">概觀</a> - <a href="/help/connections/create-connection.md">建立</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">拼接</a> - <a href="/help/connections/combined-dataset.md">合併事件資料集</a> - <a href="/help/connections/standard-lookups.md">標準查詢</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>資料檢視</strong><br/><a href="/help/data-views/data-views.md">概觀</a> - <a href="/help/data-views/create-dataview.md">建立或編輯</a> - <a href="/help/data-views/session-settings.md">工作階段設定</a> - <a href="/help/data-views/derived-fields/derived-fields.md">衍生欄位</a> - <a href="/help/data-views/component-reference.md">元件參考</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace專案</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本 </a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">進階分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">專案</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">視覺效果</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">面板</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>引導式分析</strong><br/><a href="/help/guided-analysis/overview.md">概觀</a> - <a href="/help/guided-analysis/types/active.md">使用者成長</a> - <a href="/help/guided-analysis/types/usage.md">趨勢</a> - <a href="/help/guided-analysis/types/friction.md">漏斗</a> - <a href="/help/guided-analysis/types/release.md">影響</a> - <a href="/help/guided-analysis/industry-use-cases.md">產業使用案例</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>共用、匯出、整合</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">專案</a> - <a href="/help/mobile-app/home.md">Analytics儀表板</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">整合</a>
    </td>
  </tr>
</table>

## 其他資源

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/overview.html" target="_blank">Tutorials</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics產品說明</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics附加元件)產品說明</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">CUSTOMER JOURNEY ANALYTICSAPI</a>
</td>
<td><strong>資料擷取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概觀</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">行動SDK</a> - <a href="/help/data-ingestion/batch.md">批次</a> - <a href="/help/data-ingestion/streaming.md">串流</a> - <a href="/help/data-ingestion/sources.md">來源</a> - <a href="/help/data-ingestion/serverapi.md">伺服器API</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>瞭解最新資訊、為社群作出貢獻，並提升您的Customer Journey Analytics體驗！</b><br>請造訪Adobe Analytics社群，與其他從業人員討論功能。 <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社群！</a></td></tr></tbody></table>
