---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陸頁面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 6b5a9050d6c13e3c9d637a3ed992840a46058cee
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 59%

---

# Customer Journey Analytics 指南

本技術文件指南提供 Customer Journey Analytics 的自助協助。Customer Journey Analytics可讓您將您選擇之任何管道的客戶資料（線上及離線皆可）整合到Adobe Experience Platform中。 接著依您目前使用Analysis Workspace分析現有數位資料的方式來分析這些資料。

Customer Journey Analytics可讓您控制如何在Analysis Workspace中連線任何常見客戶ID的線上和離線資料，讓您進行歸因、篩選、流量與流失等分析。 進行全部客戶資料的歸因、篩選器、流量與流失等分析。

## 新增功能？

快速一覽 Customer Journey Analytics 產品和文件的最新增強功能！如需功能、改進項目與修正的完整清單，請參閱詳細的[發行說明](../release-notes/latest.md)。造訪 [檔案更新頁面](../release-notes/doc-changes.md) 以掌握最新變更。

>[!BEGINTABS]

>[!TAB BI擴充功能*]

BI擴充功能可讓SQL存取您在Customer Journey Analytics中定義的資料檢視。 您現在可以使用您最愛的BI工具，根據Customer Journey Analytics使用者在其Analysis Workspace專案中使用的相同資料檢視建立報告和儀表板。

[![影像](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

<span style="color:gray">*_您必須有Select套件或更高版本才能使用BI擴充功能。_</span>


<!--
>[!TAB Improved Audience Publising] 

Audiences that are published from Customer Journey Analytics are now available in the new **Audiences** section in Adobe Experience Platform. Audiences are now available in Experience Platform seconds after they are published from Customer Journey Analytics. Improved sorting and filter options in Experience Platform for Customer Journey Analytics audiences. 

[![image](assets/learn-more-button.svg)](/help/components/audiences/publish.md)

-->


>[!TAB 新檔案]

新檔案現在可從以下網址取得：<ul><li>如何從Adobe Analytics升級至Customer Journey Analytics。</li><li>資料匯出使用案例和必要的Experience Platform及Customer Journey功能。 </li></ul>選取 **[!UICONTROL 瞭解更多]** 本檔案和其他檔案的更新內容。

[![影像](assets/learn-more-button.svg)](/help/release-notes/doc-changes.md)

>[!TAB 預測]

預測是 Analysis Workspace 的功能，用於以任何支援的時間詳細程度 (每小時、每天、每週、每月和每年) 預測標準或計算量度。預測僅適用於時間序列相關資料。

[![影像](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)

>[!TAB 引導式分析* - 保留率]

一種新的視圖類型，顯示在所需日期範圍內初次參與後傳回的使用者百分比。橫軸表示自使用者初次參與以來的天數。縱軸表示再次參與使用者的百分比。

[![影像](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_引導式分析是 Adobe Product Analytics 的一部分；Adobe Product Analytics 是 Customer Journey Analytics 的付費附加元件。_</span>


>[!TAB 引導式分析* - 趨勢線]

使用情況視圖中現在提供了趨勢線覆蓋，這有助於描繪更清晰的資料模式。現有趨勢線類型有線性、對數和移動平均線。

[![影像](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_引導式分析是 Adobe Product Analytics 的一部分；Adobe Product Analytics 是 Customer Journey Analytics 的付費附加元件。_</span>

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
    <div><strong>擷取及使用資料</strong><br/>瞭解您必須將資料內嵌至Experience Platform並使用於Customer Journey Analytics中的分析和報表的選項。</div>
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

瞭解Customer Journey Analytics與Adobe Analytics的落差。 以及如何在解決方案中取得資料，然後準備、檢視、分析這些資料，並將其大眾化，最後形成分析和報告。

<table style="table-layout:auto">
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
      <strong>資料檢視</strong><br/><a href="/help/data-views/data-views.md">概觀</a> - <a href="/help/data-views/create-dataview.md">建立或編輯</a> - <a href="/help/data-views/session-settings.md">工作階段設定</a> - <a href="/help/data-views/derived-fields/derived-fields.md">衍生欄位</a> - <a href="/help/data-views/component-reference.md">元件參考</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace專案</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本</a> &amp; <a href="/help/analysis-workspace/perform-adv-analysis.md">進階分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">專案</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">視覺效果</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">面板</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>引導式分析</strong><br/><a href="/help/guided-analysis/overview.md">概述</a> - <a href="/help/guided-analysis/types/active.md">使用者成長</a> - <a href="/help/guided-analysis/types/usage.md">趨勢</a>  - <a href="/help/guided-analysis/types/friction.md">漏斗</a> - <a href="/help/guided-analysis/types/release.md">影響</a> - <a href="/help/guided-analysis/industry-use-cases.md">產業使用案例</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>分享、匯出、整合</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">專案</a> - <a href="/help/mobile-app/home.md">Analytics 儀表板</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">整合</a>
    </td>
  </tr>
</table>

## 其他資源

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">教學課程</a> - <a href="https://helpx.adobe.com/tw/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 產品說明</a> - <a href="https://helpx.adobe.com/tw/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics 附加元件) 產品說明</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a>
</td>
<td><strong>資料擷取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概述</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a>  - <a href="/help/data-ingestion/aepmobilesdk.md">行動 SDK</a> - <a href="/help/data-ingestion/batch.md">批次</a> - <a href="/help/data-ingestion/streaming.md">串流</a> -  <a href="/help/data-ingestion/sources.md">來源</a> - <a href="/help/data-ingestion/serverapi.md">伺服器 API</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>隨時掌握情況、為社群做出貢獻並提升您的 Customer Journey Analytics 體驗！</b><br>請造訪Adobe Analytics社群，與其他從業人員討論此功能。 <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社群！</a></td></tr></tbody></table>
