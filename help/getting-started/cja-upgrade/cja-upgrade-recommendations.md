---
title: 從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 6%

---

# 從Adobe Analytics升級至Customer Journey Analytics

在開始從Adobe Analytics升級至Customer Journey Analytics的流程之前，請先瞭解建議的升級步驟。

>[!NOTE]
>
>本節所述的升級步驟是建議的升級步驟，任何組織都可使用此步驟成功從Adobe Analytics升級至Customer Journey Analytics。
>
>不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。 在這種情況下，請使用[Adobe AnalyticsCustomer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)，以動態產生針對貴組織獨特環境量身打造的升級步驟。

## 針對大多陣列織建議的升級步驟

從Adobe Analytics升級為Customer Journey Analytics的建議步驟是全新實施的Experience Platform Web SDK，這是Customer Journey Analytics的偏好資料收集方法。 在與Web SDK搭配使用時，Adobe也建議使用Analytics來源聯結器，以保留歷史Adobe Analytics資料並執行並排資料比較。

完全轉換為Customer Journey Analytics後，可以關閉Analytics來源聯結器，並專門使用Experience Platform Web SDK。

### 高階建議升級程式

1. **實作Experience PlatformWeb SDK**

   新的實施Experience Platform Web SDK是收集資料以進行Customer Journey Analytics的最佳方式。 這是充份運用Customer Journey Analytics的最佳基礎，因為這是實作Customer Journey Analytics最具效能、最簡單明瞭、也最經得起未來考驗的方法。

   * 高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供即時個人化使用案例而建置

   * 在其他Experience Cloud產品(AJO、RTCDP等)之間整合Adobe Experience Cloud資料收集實作

   * 不依賴Adobe Analytics命名法(屬性、eVar、事件等)

1. **設定Adobe Analytics來源聯結器**

   為協助順利過渡到使用Experience Platform Web SDK搭配Customer Journey Analytics，Adobe也建議使用Adobe Analytics來源聯結器。 這可讓您保留現有Adobe Analytics實作的歷史資料並檢視其Customer Journey Analytics資料，並與新Experience Platform Web SDK實作的資料並排。

   Analytics來源聯結器可讓您：

   * 將您的Adobe Analytics歷史報表套裝資料匯入Adobe Experience Platform並進行Customer Journey Analytics。

     您可以將Analytics來源聯結器維持執行，只要您需要保留歷史Adobe Analytics資料即可。

   * 在Customer Journey Analytics中檢視使用原始Adobe Analytics實作(AppMeasurement、Analytics擴充功能或Web SDK擴充功能)收集的資料。 您可以並排比較這些資料與新的Web SDK實作。

     您可以讓Analytics來源聯結器保持執行，直到您熟悉並熟悉各種差異為止。<!--elaborate on what those differences are? -->

   不建議將Analytics來源聯結器作為獨立實作來長期使用Customer Journey Analytics。 這是由於高延遲、複雜而雜亂的結構描述、依賴Adobe Analytics命名法(prop、eVar等)，以及最終難以從來源聯結器移至建議的Web SDK實施。

### 詳細的建議升級步驟

下列步驟說明從Adobe Analytics升級至Customer Journey Analytics的建議流程。

根據您組織獨特的環境和要求，這些建議的步驟可能不適合您的組織。 在這種情況下，請使用[Adobe AnalyticsCustomer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)，以動態產生針對貴組織獨特環境量身打造的升級步驟。

1. [規劃您的XDM結構描述架構](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [在Adobe Experience Platform中建立您需要的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

1. [在Adobe Experience Platform中建立資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. 展開說明目前Adobe Analytics實作的區段，然後完成相關步驟：

   +++適用於使用AppMeasurement的Adobe Analytics實作

   1. [在Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)中建立資料串流。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++適用於使用Analytics擴充功能（標籤）的Adobe Analytics實施

   1. [在Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)中建立資料串流。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ 針對使用Web SDK的Adobe Analytics實作

   不需要執行其他步驟。

+++

1. [將Adobe Experience Platform作為服務新增至您的資料流](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. 使用下表來識別您要繼續在Customer Journey Analytics中使用的任何Adobe Analytics功能，然後使用提供的資訊來瞭解如何在升級至Customer Journey Analytics的過程中設定這些功能：

   | Adobe Analytics功能 | Customer Journey Analytics的實作需求 | 其他資訊 |
   |---------|----------|---------|
   | 分類資料 | 為每個包含分類資料的維度建立查詢資料集。 |  |
   | 行銷管道 | 建立行銷管道衍生的欄位。 |  |
   | Activity Map覆蓋和連結追蹤 | 不適用 | Adobe目前正在處理Customer Journey Analytics的Activity Map覆蓋支援。 |
   | 資料摘要 | 實作期間不需要設定。<br/>[瞭解Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md)中的各種匯出選項。 | 雖然Customer Journey Analytics尚無法直接取代資料摘要，但您可以從Analysis Workspace匯出Customer Journey Analytics報表，以用於協力廠商工具或與外部資料結合。 |
   | Data Warehouse | 實作期間不需要設定。<br/>[瞭解Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md)中的完整資料表匯出。 | 「Customer Journey Analytics完整表格匯出」是Adobe Analytics中Data Warehouse報表的發展成果，其中包含許多經常請求的新功能，目前在Data Warehouse中尚未提供。 |
   | 串流媒體資料 |  |  |

1. （選用）使用Analytics來源聯結器從Adobe Analytics匯入歷史資料。

   如需詳細資訊，請參閱[在[使用來源聯結器](/help/data-ingestion/sources.md)擷取和使用資料](/help/data-ingestion/sources.md#use-a-source-connector)。

1. 使用下表來識別您想要的任何Customer Journey Analytics功能，然後使用提供的資訊來瞭解如何設定這些功能，作為升級至Customer Journey Analytics的一部分：

   | Customer Journey Analytics您想要的功能 | Customer Journey Analytics的實作需求 | 其他資訊 |
   |---------|----------|---------|
   | 將網路資料與其他管道的資料繫結，例如客服中心資料 | 建立連線後（如稍後步驟所述），在Customer Journey Analytics中將其他資料集新增到您的連線。 |  |
   | 與RTCDP整合 | 在您的結構描述中啟用設定檔，並建立用於RTCDP的設定檔資料集 | 建立XDM結構描述時必須執行此操作。 |
   | 整合Adobe Journey Optimizer | 在您的實作中使用個人化物件，以用於Adobe Journey Optimizer |  |

1. 展開說明所需Customer Journey Analytics實作的區段，然後完成相關步驟：

   +++手動實施（JS檔案）

   1. [新增alloy.js至您的網站](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)。

+++

   +++標籤

   1. [在Adobe Experience Platform資料彙集中建立標籤屬性](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property)。

+++

+++ API

   1. 使用Edge Network API傳送資料至所需的資料流。

+++

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)中建立連線。

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)中建立資料檢視。

1. [驗證資料是否流入Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. [移轉專案和元件](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。

1. 比較舊實作與新實作的資料，確定您瞭解所有差異及其存在原因。

1. 規劃使用者上線。

   如同在 Adobe Analytics 一樣，Analysis Workspace 是 Customer Journey Analytics 中面向使用者的主要工具。不過，在 Customer Journey Analytics 中使用 Analysis Workspace 時，使用者需要注意一些主要差異。

   您應該給使用者充足的時間 (3 - 6 個月) 來熟悉 Analysis Workspace 在 Customer Journey Analytics 中的主要差異。

   有關 Adobe Analytics 和 Customer Journey Analytics 之間一些主要差異的資訊，請參閱「[Adobe Analytics 使用者的使用手冊](/help/getting-started/aa-to-cja-user.md)」。

1. 停用AppMeasurement資料收集。

1. 停用Analytics來源聯結器。

   若使用Experience Platform Web SDK實作，Analytics來源聯結器僅適用於Adobe Analytics歷史資料，以及比較原始實作與新實作的資料。

   當您的新實作已有足夠的歷史資料，而且您熟悉Customer Journey Analytics中的報告差異時，您應該關閉Analytics來源聯結器。

## 為您的組織動態產生升級步驟

根據數個因素，例如時間表和資源限制，[瞭解建議的升級步驟](#1-understand-the-recommended-upgrade-steps)中所述的建議升級步驟可能對您的組織不實用。

若要根據組織獨特的情況動態產生升級步驟：

1. 完成[Adobe Analytics以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

   完成此問卷調查後，系統會為您提供逐步指示，概述組織需求所獨有的最佳升級步驟。 這些升級步驟最能符合您現有的Adobe Analytics環境和Customer Journey Analytics目標。

1. 請依照產生的逐步指示升級至Customer Journey Analytics。

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









