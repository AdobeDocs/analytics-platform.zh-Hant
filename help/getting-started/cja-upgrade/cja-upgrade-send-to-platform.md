---
title: 移轉至 Customer Journey Analytics 時，將資料傳送至 Adob​​e Experience Platform
description: 移轉至 Customer Journey Analytics 時，將資料傳送至 Adob​​e Experience Platform
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '897'
ht-degree: 100%

---

# 步驟 3：升級時將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform

+++ 展開此部分，查看此頁面資訊在更大規模升級程序中的位置。確保所有先前的升級步驟都已完成。

在繼續此部分之前，請先確保您已完成所有先前的升級工作。

本頁資訊涵蓋升級程序的步驟 3，重點如下表所示：

| 升級工作 | 詳細資料 |
|---------|----------|
| **步驟 1：[開始進行升級](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升級到 Customer Journey Analytics 的好處和基本升級流程。 |
| **步驟 2：[選擇升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多種方法可以升級到 Customer Journey Analytics。根據您組織目前的 Adob&#x200B;&#x200B;e Analytics 環境和長期目標，選擇最適合您組織的方法。 |
| <span class="preview">**步驟 3： 將資料發送至 Adob&#x200B;&#x200B;e Experience Platform**</span> | <span class="preview">將資料發送送至 Adob&#x200B;&#x200B;e Experience Platform 的流程會因您在步驟 2 選擇的升級路徑而不同。</span> |
| **步驟 4：[保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多數組織需要保留其歷史 Adob&#x200B;&#x200B;e Analytics 資料達一段時間。有多種選項可以達到此目的。 |
| **步驟 5： [執行額外的實施工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段中，您需要執行各類工作後，您的 Customer Journey Analytics 環境才可供使用。<p>這些額外工作適用於 Adob&#x200B;&#x200B;e Analytics 的升級以及新的 Customer Journey Analytics 實施。</p><p>這些工作包括：</p><ul><li>將其他資料引入 Experience Platform</li><li>建立 Platform 資料集和 Customer Journey Analytics 之間的連線</li><li>建立資料檢視</li><li>轉移報告 API 用法</li><li>考量資料摘要和 Data Warehouse</li><li>移轉專案和元件</li><li>規劃使用者上線</li></ul> <p>如需更多資訊，請參閱「[Customer Journey Analytics 快速入門手冊](/help/getting-started/cja-getting-started.md)」。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>此頁面上的資訊將被以下更全面的升級資訊取代： <ul><li>**建議的升級步驟**<p>如需詳細資訊，請參閱[從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升級指南**<p>新的升級指南現已推出，可動態產生適合您組織和獨特情況的升級步驟。</p><p>若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。</p></li></ul>

在您「[選擇最適合您組織的升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)」後，您可以開始將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform，以便在 Customer Journey Analytics 中使用。

以下顯示每個升級路徑傳送資料至 Experience Platform 的過程。請按表格內連結取得詳細的設定資訊。

| 升級路徑 | 將資料傳送至平台的流程 | 其他資訊 |
|---------|----------|----------|
| Experience Platform Web SDK 全新實施 | <ol><li>為您的組織建立 XDM 結構描述。<p>與您的資料團隊合作，確定您組織使用 Customer Journey Analytics 理的理想結構描述設計。</p></li><li>實施 Experience Platform Web SDK。</li><li>將資料傳送到 Platform。</li></ol><p>有關這些步驟的各個詳細資訊，請參閱「[透過 Adob&#x200B;&#x200B;e Experience Platform Web SDK 擷取資料](/help/data-ingestion/aepwebsdk.md)」。 | 由於這是 Experience Platform Web SDK 的新實施，因此不需要結構描述對應，這是因為首要步驟之一是您必須在實施過程中建立結構描述。 |
| 移轉您的 Adobe Analytics 實施以使用 Web SDK | <ol><li>將現有的 Adob&#x200B;&#x200B;e Analytics 實施移動至 Experience Platform Web SDK，並驗證 Ad&#x200B;&#x200B;ob&#x200B;&#x200B;e Analytics 中的一切是否正常運作。<p>有關如何執行此操作的資訊，請使用以下資源；實際要取決於您目前的實施是 Analytics 標記擴充功能或 AppMeasurement：</p><ul><li>如果您正在使用 Analytics 標記擴充功能，請參閱[從 Adob&#x200B;&#x200B;e Analytics 標記擴充功能移轉至 Web SDK 標記擴充功能](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>如果您正使用 AppMeasurement，請參閱[從 AppMeasurement 移轉至 Web SDK](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[為您的組織建立 XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>與您的資料團隊合作，確定您組織使用 Customer Journey Analytics 理的理想結構描述設計。</p></li><li>[使用資料準備功能，將資料物件中所有欄位對應到您的 XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-prep/home)。</li><li>透過[設定資料流](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream)，開始發送資料至 Platform。</li></ol> |  |
| 設定現有的 Adobe Analytics Web SDK 實作以傳送資料至平台 | <ol><li>透過[設定資料流](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)，開始發送資料至 Platform。<p>由於您的 Adob&#x200B;&#x200B;e Analytics 實施已在使用 Experience Platform Web SDK，因此您可以忽略[透過 Adob&#x200B;&#x200B;e Experience Platform Web SDK 攝取資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)中的其他部分。</p><p>如果您已經使用 Adobe Analytics 實施將資料傳送到 Platform，則不需要此步驟。您只需要在 Platform 資料集和 Customer Journey Analytics 之間建立連線，如本過程後面所述。</p></li><li>(選用) [為您的組織建立 XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>與您的資料團隊合作，確定您組織使用 Customer Journey Analytics 理的理想結構描述設計。</p><p>注意：有關建立 XDM 結構描述的優勢資訊，請參閱「[選擇您的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema)」。</li><li>(選用) 如果您建立了 XDM 結構描述，請[使用資料準備功能將資料物件中的所有欄位對應到您的 XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-prep/home)。</li></ol> |  |
| 使用 Analytics 來源連接器 | [從傳統 Adobe Analytics 攝取和使用資料](/help/data-ingestion/analytics.md) | 當您使用 Analytics 來源連接器時，Adobe Analytics 資料會自動對應到 XDM 結構描述。不需要額外的對應。 |

## 接下來，保留歷史資料

接下來，決定您將如何[保留 Adob&#x200B;&#x200B;e Analytics 歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)。
