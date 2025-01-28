---
title: 從協力廠商分析解決方案升級至Customer Journey Analytics
description: 瞭解如何從協力廠商分析解決方案升級至Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 8%

---

# 從協力廠商分析解決方案升級至Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="協力廠商分析產品"
>abstract="為協力廠商分析產品(例如Google Analytics)收集資料的實作。 選取此選項會停用調查問卷中的數個選項，這些選項在從協力廠商分析產品升級至Customer Journey Analytics時並不適用。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中的問題時，使用此頁面上的資訊。

建議的從協力廠商分析解決方案升級為Customer Journey Analytics的程式是Experience Platform Web SDK的新實作，這是Customer Journey Analytics的偏好資料收集方法。 Adobe也建議結合使用網頁SDK將協力廠商分析解決方案的歷史資料擷取至Adobe Experience Platform。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

從協力廠商分析解決方案(例如Google Analytics)移至Customer Journey Analytics時，請使用下列程式：

1. ...


如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

| 現有的分析解決方案 | 說明 | 可用的升級路徑 |
|---------|----------|----------|
| AppMeasurement | AppMeasurementJavaScript向來是實施Adobe Analytics的常用方法。<p>如需此實作型別的詳細資訊，請參閱[使用JavaScript的AppMeasurement實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)。</p> | <ul><li>[（建議）新的實作Experience PlatformWeb SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新實作](/help/data-ingestion/aepwebsdk.md) </li><li>將Adobe Analytics移轉至Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics擴充功能（標籤） | <p>Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。</p><p>如需此實作型別的詳細資訊，請參閱[使用Analytics擴充功能實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)。</p> | <ul><li>[（建議）新的實作Experience PlatformWeb SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新實作](/help/data-ingestion/aepwebsdk.md) </li><li>將Adobe Analytics移轉至Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform網頁SDK (alloy.js) | Experience PlatformWeb SDK是Adobe目前建議的實施Adobe Analytics方法。 Adobe Experience PlatformEdge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience PlatformEdge Network實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)。</p> | <ul><li>[（建議）新的實作Experience PlatformWeb SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新實作](/help/data-ingestion/aepwebsdk.md) </li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| Experience PlatformWeb SDK擴充功能（標籤） | Experience PlatformWeb SDK是Adobe目前建議用於為網頁資料實作Adobe Analytics的方法。 Adobe Experience PlatformEdge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience Platform Web SDK實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[（建議）新的實作Experience PlatformWeb SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新實作](/help/data-ingestion/aepwebsdk.md)</li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK是Adobe目前為行動資料實作Adobe Analytics的建議方法。 Adobe Experience PlatformEdge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。<p>Adobe Experience Platform Mobile SDK有助於在行動應用程式中強化Adobe的Experience Cloud解決方案和服務。 </p><p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience Platform Mobile SDK實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[（建議）新的實作Experience PlatformWeb SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新實作](/help/data-ingestion/aepwebsdk.md) </li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| 大量資料插入 API | 大量資料插入API (BDIA)是Adobe Analytics的功能，可讓您以批次檔案的方式上傳伺服器呼叫資料，而不需使用AppMeasurement等使用者端資料庫。 </p><p>如需此實作型別的詳細資訊，請參閱[大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。</p> | <ul><li>[（建議）新的實作Experience PlatformWeb SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新實作](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience PlatformEdge Network伺服器API與Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}