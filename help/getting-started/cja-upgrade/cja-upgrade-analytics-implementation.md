---
title: 了解您的 Adobe Analytics 實作情況，以及它如何影響您升級至 Customer Journey Analytics
description: 瞭解從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 27%

---

# 了解您的 Adobe Analytics 實作情況，以及它如何影響您升級至 Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (手動 JS 檔案)"
>abstract="一種 JavaScript 實作，會在頁面上載入 AppMeasurement.js，並使用 s 物件 (例如 s.eVar1) 將資料傳送至 Adobe。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics 擴充功能 (標籤)"
>abstract="一種標籤實作，可載入 Adobe Experience Platform 資料收集 (先前稱為 Launch)。此標籤已安裝 Adobe Analytics 擴充功能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK (alloy.js)"
>abstract="一種 JavaScript 實作，會在頁面上載入 Web SDK 資料庫 (alloy.js)，並使用 JSON 承載將資料傳送至 Adobe。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK 擴充功能 (標籤)"
>abstract="一種標籤實作，會載入 Adobe Experience Platform 資料收集 (先前稱為 Launch)。此標籤已安裝 Web SDK 擴充功能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="資料插入 API"
>abstract="一種實作，會使用資料插入 API 或大量資料插入 API。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="一種實作，會使用 Adobe Experience Platform Mobile SDK。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="未知的實作"
>abstract="如果您不是管理實作的人員，可以暫時選取此選項。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中的問題時，使用此頁面上的資訊。

Adobe Analytics有多種實施方式。 升級至Customer Journey Analytics時，並非所有Adobe Analytics實施都可使用所有升級路徑。 不過，不論Adobe Analytics在您的組織中如何實作，都提供建議的升級路徑。

使用下列資訊瞭解您目前的Adobe Analytics實作，以及貴組織可用的升級路徑。

如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

| 現有的Adobe Analytics實作 | 說明 | 可用的升級路徑 |
|---------|----------|----------|
| AppMeasurement | 適用於JavaScript的AppMeasurement向來是實施Adobe Analytics的常用方法。<p>如需此實作型別的詳細資訊，請參閱[使用JavaScript的AppMeasurement實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)。</p> | <ul><li>[（建議）新實作Experience Platform Web SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[新的Experience Platform Web SDK實作](/help/data-ingestion/aepwebsdk.md) </li><li>將Adobe Analytics移轉至Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics擴充功能（標籤） | <p>Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。</p><p>如需此實作型別的詳細資訊，請參閱[使用Analytics擴充功能實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)。</p> | <ul><li>[（建議）新實作Experience Platform Web SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[新的Experience Platform Web SDK實作](/help/data-ingestion/aepwebsdk.md) </li><li>將Adobe Analytics移轉至Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK是Adobe目前建議的實施Adobe Analytics方法。 Adobe Experience Platform Edge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience Platform Edge Network實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)。</p> | <ul><li>[（建議）新實作Experience Platform Web SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[新的Experience Platform Web SDK實作](/help/data-ingestion/aepwebsdk.md) </li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| Experience Platform Web SDK擴充功能（標籤） | Experience Platform Web SDK是Adobe目前建議用於為Web資料實作Adobe Analytics的方法。 Adobe Experience Platform Edge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience Platform Web SDK實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[（建議）新實作Experience Platform Web SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[新的Experience Platform Web SDK實作](/help/data-ingestion/aepwebsdk.md)</li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK是Adobe目前為行動資料實作Adobe Analytics的建議方法。 Adobe Experience Platform Edge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。<p>Adobe Experience Platform Mobile SDK有助於在行動應用程式中強化Adobe的Experience Cloud解決方案和服務。 </p><p>如需此實作型別的詳細資訊，請參閱[使用Adobe Experience Platform Mobile SDK實作Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[（建議）新實作Experience Platform Web SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[新的Experience Platform Web SDK實作](/help/data-ingestion/aepwebsdk.md) </li><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li></ul> |
| 大量資料插入 API | 大量資料插入API (BDIA)是Adobe Analytics的功能，可讓您以批次檔案的方式上傳伺服器呼叫資料，而不需使用AppMeasurement等使用者端資料庫。 </p><p>如需此實作型別的詳細資訊，請參閱[大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。</p> | <ul><li>[（建議）新實作Experience Platform Web SDK以進行持續資料收集；Analytics Source Connector用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[新的Experience Platform Web SDK實作](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network伺服器API與Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
