---
title: 移轉至Customer Journey Analytics時傳送資料至Adobe Experience Platform
description: 移轉至Customer Journey Analytics時傳送資料至Adobe Experience Platform
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---

# 步驟3：移轉至Customer Journey Analytics時傳送資料至Adobe Experience Platform

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟3，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| <span class="preview">**步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。</span> |
| **步驟4： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++


在您之後 [選擇移轉方法](#step-2-choose-your-customer-journey-analytics-migration-method) 這是最適合您組織的作法，您可以開始將資料傳送至Adobe Experience Platform，以便在Customer Journey Analytics中使用。

針對每種移轉方法傳送資料至Experience Platform的程式如下所示。 請依照下表中的連結取得更多詳細資訊。

| 移轉方法 | 將資料傳送至Platform的程式 |
|---------|----------|
| Web SDK的新實作 | 由於這是Web SDK的新實作，因此您必須遵循中說明的所有步驟 [透過Adobe Experience Platform Web SDK內嵌資料](/help/data-ingestion/aepwebsdk.md). |
| 移轉您的Adobe Analytics實作以使用Web SDK | 根據您目前的實施為Analytics擴充功能或AppMeasurement，移轉至Adobe Analytics Web SDK的步驟會有所不同。 <p>如果您使用Analytics標籤擴充功能： [從Adobe Analytics標籤擴充功能移轉至Web SDK標籤擴充功能](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</p><p>或</p><p>如果您使用AppMeasurement： [從AppMeasurement移轉至Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| 設定您現有的Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics | 由於您的Adobe Analytics實作已使用Web SDK，因此您只需要 [設定資料串流](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream). 您可以忽略中的其他區段 [透過Adobe Experience Platform Web SDK內嵌資料](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk). |
| Analytics來源聯結器 | [從傳統 Adobe Analytics 擷取和使用資料](/help/data-ingestion/analytics.md) |

## 接下來，將資料對應至XDM結構描述

按照上表中的連結傳送資料給Experience Platform後，您可能需要 [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)，視您選擇的實作方法而定。

下列實作方法需要您將資料對應至XDM結構描述：

* 從Adobe Analytics標籤擴充功能移轉至Web SDK標籤擴充功能

* 設定您現有的Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics

或者，如果您選擇執行Web SDK的新實作，則不需要進行對應，因為您已經 [設定新的XDM結構描述](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 做為新實作的一部分。

如果您選擇使用Analytics來源聯結器進行移轉，則不需要進行對應，因為Analytics來源聯結器會使用您現有的Adobe Analytics結構描述，而非XDM結構描述。
