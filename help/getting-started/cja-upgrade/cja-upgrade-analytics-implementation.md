---
title: 了解您的 Adobe Analytics 實作情況，以及它如何影響您升級至 Customer Journey Analytics
description: 了解關於從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 100%

---

# 了解您的 Adobe Analytics 實施情況，以及它如何影響您升級至 Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (手動 JS 檔案)"
>abstract="一種 JavaScript 實作，會在頁面上載入 AppMeasurement.js，並使用 s 物件 (例如 s.eVar1) 將資料傳送至 Adobe。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics 擴充功能 (標記)"
>abstract="一種標籤實作，可載入 Adobe Experience Platform 資料收集 (先前稱為 Launch)。標記已安裝 Adobe Analytics 擴充功能。"

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
>id="cja-upgrade-appmeasurement-third-party"
>title="使用第三方標記管理工具的 AppMeasurement"
>abstract="使用第三方標記管理工具的實作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="未知的實作"
>abstract="如果您不是管理實作的人員，可以暫時選取此選項。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="確認您現有的實作類型"
>abstract="與組織內部合作，確認您目前將資料傳送至 Adobe Analytics 所使用的實作類型。當您升級至 Customer Journey Analytics 時，請與了解此資訊的個人或團隊合作。<br><br>確定組織所使用的實作類型後，請修改 Customer Journey Analytics 升級指南中的答案。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics 可以透過多種方式實施。升級至 Customer Journey Analytics 時，並非所有升級路徑都適用於所有 Adob&#x200B;&#x200B;e Analytics 實施。但是，無論您的組織如何實施 Adob&#x200B;&#x200B;e Analytics，都可以使用建議的升級路徑。

使用以下資訊了解您目前的 Adob&#x200B;&#x200B;e Analytics 實施情況，以及了解您組織可使用的升級途徑。

如果您需要更具體的建議、指導或支援，請聯絡您的 Adob&#x200B;&#x200B;e 代表。

| 現有的 Adobe Analytics 實施 | 說明 | 適用升級路徑 |
|---------|----------|----------|
| AppMeasurement | JavaScript 適用的 AppMeasurement 向來是實施 Adobe Analytics 的常用方法。<p>有關此實施類型的詳細資訊，請參閱「[使用 AppMeasurement for JavaScript 實施 Adob&#x200B;&#x200B;e Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/js/overview)」。</p> | <ul><li>[(建議) Experience Platform Web SDK 全新實施，適用於持續資料收集；Analytic 來源連接器，適用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 全新實施](/help/data-ingestion/aepwebsdk.md) </li><li>[將 Adobe Analytics 移轉至 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics 來源連接器](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics 擴充功能 (標記) | <p>Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。</p><p>有關此實施類型的詳細資訊，請參閱「[使用 Analytics 擴充功能實施 Adob&#x200B;&#x200B;e Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/launch/overview)」。</p> | <ul><li>[(建議) Experience Platform Web SDK 全新實施，適用於持續資料收集；Analytic 來源連接器，適用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 全新實施](/help/data-ingestion/aepwebsdk.md) </li><li>[將 Adobe Analytics 移轉至 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics 來源連接器](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK 是 Adobe 目前建議的 Adobe Analytics 實施方法。Adobe Experience Platform Edge Network 可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>有關此實施類型的詳細資訊，請參閱「[使用 Adob&#x200B;&#x200B;e Experience Platform Edge Network Server 實施 Adob&#x200B;&#x200B;e Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/overview)」。</p> | <ul><li>[(建議) Experience Platform Web SDK 全新實施，適用於持續資料收集；Analytic 來源連接器，適用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 全新實施](/help/data-ingestion/aepwebsdk.md) </li><li>[設定 AdobeAnalyticsWebSDK 實施，以便將資料傳送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Web SDK 擴充功能 (標記) | Experience Platform Web SDK 是 Adobe 目前建議適用於網頁資料的 Adobe Analytics 實施方法。Adobe Experience Platform Edge Network 可讓您將預計要送給多個產品的資料傳送到一個集中位置。 <p>有關此實施類型的詳細資訊，請參閱「[使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK 實施 Adob&#x200B;&#x200B;e Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/web-sdk/overview)」</p> | <ul><li>[(建議) Experience Platform Web SDK 全新實施，適用於持續資料收集；Analytic 來源連接器，適用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 全新實施](/help/data-ingestion/aepwebsdk.md)</li><li>[設定 AdobeAnalyticsWebSDK 實施，以便將資料傳送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK 是 Adobe 目前建議適用於行動資料的 Adobe Analytics 實施方法。Adobe Experience Platform Edge Network 可讓您將預計要送給多個產品的資料傳送到一個集中位置。<p>Adobe Experience Platform Mobile SDK 有助於在行動應用程式中強化 Adobe 的 Experience Cloud 解決方案和服務。 </p><p>有關此實施類型的詳細資訊，請參閱「[使用 Adob&#x200B;&#x200B;e Experience Platform Mobile SDK 實施 Adob&#x200B;&#x200B;e Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/mobile-sdk/overview)」</p> | <ul><li>[(建議) Experience Platform Web SDK 全新實施，適用於持續資料收集；Analytic 來源連接器，適用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 全新實施](/help/data-ingestion/aepwebsdk.md) </li><li>[設定 AdobeAnalyticsWebSDK 實施，以便將資料傳送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| 大量資料插入 API | 大量資料插入 API (BDIA) 是一種 Adob&#x200B;&#x200B;e Analytics 功能，可讓您以批次檔案的方式上傳伺服器呼叫資料，而不需使用 AppMeasurement 等用戶端資料庫。 </p><p>有關此實現類型的詳細資訊，請參閱「[大量資料插入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)」。</p> | <ul><li>[(建議) Experience Platform Web SDK 全新實施，適用於持續資料收集；Analytic 來源連接器，適用於歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 全新實施](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network 伺服器 API 和 Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


