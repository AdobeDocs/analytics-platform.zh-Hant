---
title: 從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 8%

---

# 從Adobe Analytics升級至Customer Journey Analytics

從Adobe Analytics升級至Customer Journey Analytics時，您可以依照[建議的升級步驟](#recommended-upgrade-steps-for-most-organizations)操作。 或者，您可以[針對貴組織的獨特情況，動態產生升級步驟](#dynamically-generate-upgrade-steps-for-your-organization)。

## 針對大多陣列織建議的升級步驟 {#upgrade-process}

建議的從Adobe Analytics升級為Customer Journey Analytics的程式是Experience PlatformWeb SDK的新實作，這是Customer Journey Analytics的偏好資料收集方法。 Adobe也建議結合使用網頁SDK來協助您轉換至Customer Journey Analytics。 使用Analytics來源聯結器可保留歷史Adobe Analytics資料，並執行並排資料比較。

使用Experience PlatformWeb SDK取得足夠的歷史資料，並完全轉換為Customer Journey Analytics後，可以關閉Analytics來源聯結器，並專門使用Web SDK。

>[!NOTE]
>
>如果本節所述的升級步驟對貴組織而言並不實際，請使用[Adobe Analytics來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)，以動態方式產生針對貴組織獨特環境量身打造的升級步驟。

### 高階建議升級流程 {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Adobe Analytics 的歷史資料"
>abstract="將歷史 Adobe Analytics 報告套裝資料匯入至 Adobe Experience Platform 和 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

1. **實作Experience PlatformWeb SDK （用於持續的資料收集）**

   新的實施Experience PlatformWeb SDK是收集資料以進行Customer Journey Analytics的最佳方式。 這是充份運用Customer Journey Analytics的最佳基礎，因為這是實作Customer Journey Analytics最具效能、最簡單明瞭、也最經得起未來考驗的方法。

   * 高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供即時個人化使用案例而建置

   * 在其他Experience Cloud產品(AJO、RTCDP等)之間整合Adobe Experience Cloud資料收集實作

   * 不依賴Adobe Analytics命名法(屬性、eVar、事件等)

1. **設定Adobe Analytics來源聯結器（用於引進歷史資料）**

   為了協助順利過渡到透過Customer Journey Analytics使用Experience PlatformWeb SDK，Adobe也建議使用Adobe Analytics來源聯結器。 這可讓您保留現有Adobe Analytics實作的歷史資料並檢視其Customer Journey Analytics資料，與新Experience PlatformWeb SDK實作的資料並排。

   Analytics來源聯結器可讓您：

   * 將歷史 Adobe Analytics 報告套裝資料匯入至 Adobe Experience Platform 和 Customer Journey Analytics。

     您可以將Analytics來源聯結器維持執行，只要您需要保留歷史Adobe Analytics資料即可。

   * 在Customer Journey Analytics中檢視使用原始Adobe Analytics實施(AppMeasurement、Analytics擴充功能或網頁SDK擴充功能)收集的資料。 您可以並排比較這些資料與新的Web SDK實作。

     您可以讓Analytics來源聯結器保持執行，直到您熟悉並熟悉各種差異為止。<!--elaborate on what those differences are? -->

   不建議將Analytics來源聯結器作為獨立實作來長期使用Customer Journey Analytics。 這是因為高延遲、複雜而雜亂的結構描述、依賴Adobe Analytics命名法(prop、eVar等)，以及最終從Analytics來源聯結器移至建議的Web SDK實作時的困難。

### 詳細的建議升級步驟

下列步驟概述從Adobe Analytics升級至Customer Journey Analytics的建議程式。

每個步驟都提供更詳細流程的高層級說明。 請依照每個步驟的連結完成其相關工作，然後返回此頁面並繼續流程中的下一個步驟。

1. [規劃您的XDM結構描述架構](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [在Adobe Experience Platform中建立您需要的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   建立結構描述時，請考慮下列選項：

   * 如果您要將Customer Journey Analytics與RTCDP整合，您必須在結構描述上啟用&#x200B;**[!UICONTROL 設定檔]**&#x200B;選項，如[建立XDM結構描述以與Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)搭配使用。 啟用此選項後，當資料根據此結構擷取到資料集時，該資料會合併到即時客戶個人檔案。

   * 若要包含串流媒體資料，您必須[設定您的結構描述以擷取及使用串流媒體資料](/help/data-ingestion/streaming.md)。

1. [在Adobe Experience Platform中建立資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. （選用）如果您在Adobe Analytics中使用分類資料，可以在Customer Journey Analytics中將分類資料新增到您的資料集。

   若要這麼做，[請為每個包含分類資料的維度建立查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

1. 對於使用AppMeasurement或Analytics擴充功能（標籤）的Adobe Analytics實作，[在Adobe Experience Platform中建立資料串流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   對於使用Web SDK的Adobe Analytics實作，資料流已存在。

1. [將Adobe Experience Platform作為服務新增至您的資料流](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. （選用）如果您想要將Customer Journey Analytics與Adobe Journey Optimizer整合，請在實施中使用個人化物件，以便用於Adobe Journey Optimizer。

1. 展開說明要如何為Customer Journey Analytics實施實施Experience PlatformWeb SDK的區段，然後完成相關步驟：

   +++手動實施（JS檔案）

   1. [新增alloy.js至您的網站](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)。

   1. 填入XDM物件並將其傳送至資料流。

+++

   +++標籤

   1. [建立標籤屬性並新增Adobe Experience Platform Web SDK擴充功能](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)。

   1. [將Adobe Experience Platform Web SDK擴充功能新增至標籤屬性](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [在您的網站上實作載入器標籤](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [將XDM資料收集邏輯新增至您的標籤](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)。

+++

+++ API

   1. 使用Edge Network API傳送資料至所需的資料流。

+++

1. [驗證您的Web SDK實作是否正在傳送資料到資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)。

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)中建立連線。

1. （選用）將網路資料與其他管道的資料（例如客服中心資料）連結。

   如[匯入客服中心和網路資料](/help/use-cases/cross-channel/call-center.md)中所述，透過將其他資料集新增到您的Customer Journey Analytics連線來完成此操作。

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)中建立資料檢視。

1. [驗證資料是否流入Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)的資料檢視。

1. [移轉專案和元件](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. （選擇性）如果您在Adobe Analytics中使用行銷管道，您可以[在Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels)中建立行銷管道衍生欄位。

   衍生欄位是Customer Journey Analytics中即時報表的重要層面。 衍生欄位可讓您透過可自訂的規則產生器，即時定義（通常為複雜的）資料操控。

   衍生欄位的一種用途是定義衍生行銷管道欄位，該欄位會根據一或多個條件（例如URL引數、頁面URL或頁面名稱）來決定適當的行銷管道。

   在衍生欄位中使用[行銷管道功能範本](/help/data-views/derived-fields/derived-fields.md#marketing-channels)，快速建立行銷管道的衍生欄位。

1. 比較Adobe Analytics中來自舊實作的資料與來自新實作的Customer Journey Analytics資料，並確定您瞭解任何差異及其存在原因。<!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. 使用Analytics來源聯結器從Adobe Analytics匯入歷史資料：

   >[!NOTE]
   >
   >如果您先前未建立Analytics來源聯結器，請使用下列步驟。
   >
   >如果您已使用Analytics來源聯結器搭配Customer Journey Analytics，請依照[從Analytics來源聯結器轉換至Web SDK以進行Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)中的步驟操作。

   1. [建立 Analytics 來源連接器的 XDM 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. 如果您還沒有Analytics來源聯結器，請[建立Analytics來源聯結器，並將欄位對應到您的XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

      或

      如果您已有Analytics來源聯結器，請從來源聯結器[將欄位對應到您的XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

   1. [將Analytics來源聯結器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. 規劃使用者上線。

   如同在 Adobe Analytics 一樣，Analysis Workspace 是 Customer Journey Analytics 中面向使用者的主要工具。不過，在 Customer Journey Analytics 中使用 Analysis Workspace 時，使用者需要注意一些主要差異。

   您應該給使用者充足的時間 (3 - 6 個月) 來熟悉 Analysis Workspace 在 Customer Journey Analytics 中的主要差異。

   有關 Adobe Analytics 和 Customer Journey Analytics 之間一些主要差異的資訊，請參閱「[Adobe Analytics 使用者的使用手冊](/help/getting-started/aa-to-cja-user.md)」。

1. 瞭解Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)中的[功能支援。 Customer Journey Analytics支援大部分的Adobe Analytics功能，Customer Journey Analytics也提供許多其他功能。

1. 當您的Customer Journey AnalyticsWeb SDK實作完成，而且您熟悉所收集的資料時，請停用Adobe Analytics 。

   Adobe建議您在實作Customer Journey Analytics後，讓Adobe Analytics環境持續執行一段時間。

   如需有關升級期間和之後使用Adobe Analytics的詳細資訊，以及停用Adobe Analytics的建議時間，請參閱[評估升級至Customer Journey Analytics後需要Adobe Analytics多久](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)。

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
