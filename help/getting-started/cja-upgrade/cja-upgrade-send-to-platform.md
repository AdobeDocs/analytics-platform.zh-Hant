---
title: 移轉至Customer Journey Analytics時傳送資料至Adobe Experience Platform
description: 移轉至Customer Journey Analytics時傳送資料至Adobe Experience Platform
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 97d48d88af969705f2664781e7a972f20c1b4239
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 1%

---

# 步驟3：升級時傳送資料至Adobe Experience Platform

+++展開本節，瞭解此頁面上的資訊在大型升級程式中的適用位置。 請確定所有先前的升級步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的升級工作。

本頁資訊涵蓋升級程式的步驟3，如下表所示：

| 升級任務 | 詳細資料 |
|---------|----------|
| **步驟1：[開始升級](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 瞭解升級至Customer Journey Analytics的好處和基本升級程式。 |
| **步驟2：[選擇升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 升級至Customer Journey Analytics有多種方法可供使用。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| <span class="preview">**步驟3：傳送資料至Adobe Experience Platform**</span> | <span class="preview">傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的升級路徑而有所不同。</span> |
| **步驟4：[保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟5：[執行其他實作工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種工作。<p>這些額外工作適用於Adobe Analytics的升級以及新的Customer Journey Analytics實作。</p><p>這些工作包括：</p><ul><li>將其他資料帶入Experience Platform</li><li>在Platform資料集和Customer Journey Analytics之間建立連線</li><li>建立資料檢視</li><li>移植報表API使用量</li><li>資料摘要和Data Warehouse的會計處理</li><li>移轉專案和元件</li><li>Planning使用者上線</li></ul> <p>如需詳細資訊，請參閱[Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

在您[選擇最適合您組織的升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)後，您就可以開始將資料傳送至Adobe Experience Platform，以便在Customer Journey Analytics中使用。

針對每個升級路徑將資料傳送至Experience Platform的程式如下所示。 請依照表格中的連結取得詳細的組態資訊。

| 升級路徑 | 將資料傳送至Platform的程式 | 其他資訊 |
|---------|----------|----------|
| Experience Platform Web SDK的新實作 | <ol><li>為您的組織建立XDM結構描述。<p>與您的資料團隊合作，識別您組織適用於Customer Journey Analytics的理想結構描述設計。</p></li><li>實作Experience Platform Web SDK。</li><li>傳送資料至Platform。</li></ol><p>如需每個步驟的詳細資訊，請參閱[透過Adobe Experience Platform Web SDK擷取資料](/help/data-ingestion/aepwebsdk.md)。 | 由於這是Experience Platform Web SDK的新實作，因此不需要結構描述對應，因為您必須建立結構描述作為實作期間的首要步驟之一。 |
| 移轉Adobe Analytics實作以使用網頁SDK | <ol><li>將您現有的Adobe Analytics實作專案移至Experience Platform Web SDK，然後驗證是否一切都在Adobe Analytics中正常運作。<p>如需如何執行此動作的詳細資訊，請根據您目前的實施為Analytics標籤擴充功能或AppMeasurement，使用下列資源：</p><ul><li>如果您使用Analytics標籤擴充功能，請參閱[從Adobe Analytics標籤擴充功能移轉至Web SDK標籤擴充功能](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>如果您使用AppMeasurement，請參閱[從AppMeasurement移轉至Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[為您的組織建立XDM結構描述](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>與您的資料團隊合作，識別您組織適用於Customer Journey Analytics的理想結構描述設計。</p></li><li>[使用「資料準備」將資料物件中的所有欄位對應到您的XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home)。</li><li>透過[設定資料流](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream)開始傳送資料到Platform。</li></ol> |  |
| 設定您現有的Adobe Analytics Web SDK實作，以傳送資料至Platform | <ol><li>透過[設定資料流](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)開始傳送資料到Platform。<p>由於您的Adobe Analytics實作已使用Experience Platform Web SDK，您可以忽略[透過Adobe Experience Platform Web SDK擷取資料](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)中的其他區段。</p><p>如果您已使用Adobe Analytics實作將資料傳送至Platform，則不需要執行此步驟。 您只需要在Platform資料集和Customer Journey Analytics之間建立連線，如本流程稍後所述。</p></li><li>（選用） [為您的組織建立XDM結構描述](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>與您的資料團隊合作，識別您組織適用於Customer Journey Analytics的理想結構描述設計。</p><p>注意：如需建立XDM結構描述優點的相關資訊，請參閱[選擇您的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema)。</li><li>（視條件而定）如果您已建立XDM結構描述，[請使用「資料準備」將資料物件中的所有欄位對應到您的XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home)。</li></ol> |  |
| 使用Analytics來源聯結器 | [從傳統 Adobe Analytics 擷取和使用資料](/help/data-ingestion/analytics.md) | 當您使用Adobe Analytics來源聯結器時，Analytics資料會自動對應至XDM結構描述。 不需要其他對應。 |

## 接下來，保留歷史資料

接下來，決定如何[保留歷史Adobe Analytics資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)。
