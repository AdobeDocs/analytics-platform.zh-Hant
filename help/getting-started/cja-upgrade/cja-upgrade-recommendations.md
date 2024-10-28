---
title: 從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# 從Adobe Analytics升級至Customer Journey Analytics

在開始從Adobe Analytics升級至Customer Journey Analytics的流程之前，請先瞭解建議的升級步驟。

根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。 瞭解建議的升級步驟後，請完成問卷調查，以動態產生針對貴組織獨特環境量身打造的升級步驟。

## 1.瞭解建議的升級步驟

>[!NOTE]
>
>本節所述的升級步驟是建議的升級步驟，任何組織都可使用此步驟成功從Adobe Analytics升級至Customer Journey Analytics。
>
>不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。 瞭解建議的升級步驟後，請完成[Adobe Analytics以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)，以動態產生針對貴組織獨特環境量身打造的升級步驟。

從Adobe Analytics升級為Customer Journey Analytics的建議步驟是全新實施的Experience Platform Web SDK，這是Customer Journey Analytics的偏好資料收集方法。 在與Web SDK搭配使用時，Adobe也建議使用Analytics來源聯結器，以保留歷史Adobe Analytics資料並執行並排資料比較。

完全轉換為Customer Journey Analytics後，可以關閉Analytics來源聯結器，並專門使用Experience Platform Web SDK。

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

## 2.為您的組織動態產生升級步驟

根據數個因素，例如時間表和資源限制，[瞭解建議的升級步驟](#1-understand-the-recommended-upgrade-steps)中所述的建議升級步驟可能對您的組織不實用。

若要檢視針對組織獨特環境動態產生的升級步驟：

1. 完成[Adobe Analytics以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

   完成此問卷調查後，系統會為您提供逐步指示，概述貴組織專屬的最佳升級步驟。 這些升級步驟最能符合您現有的Adobe Analytics環境和Customer Journey Analytics目標。

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









