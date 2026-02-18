---
title: 為 Customer Journey Analytics 設定串流媒體集合
description: 瞭解如何設定Customer Journey Analytics的串流媒體收集
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 380ed5c9ee0c21ea9855a41728afec040637ce65
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# 為 Customer Journey Analytics 設定串流媒體集合 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="設定並實作 Media Edge"
>abstract="如果您計劃將串流媒體集合與 Customer Journey Analytics 併用，升級過程的某些步驟中則需進行特定選擇。例如，您需要將 MediaAnalytics 互動詳細資料欄位群組新增至您的綱要中、在資料流中啟用媒體分析等等。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

如同Adobe Analytics中，串流媒體收集可用於收集串流媒體資料，以用於Customer Journey Analytics。 如果您搭配Adobe Analytics使用串流媒體收集，應將其納入Customer Journey Analytics的升級計畫。

在從Adobe Analytics升級至Customer Journey Analytics的步驟中，針對串流媒體收集資料做出以下選擇：

* 為Customer Journey Analytics建立結構描述時，請包含`MediaAnalytics Interaction Details`欄位群組。

  如需新增此欄位群組的詳細資訊，請參閱串流媒體收集指南中的[在Adobe Experience Platform中設定結構描述](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)。

  如需有關建立結構描述的資訊，請參閱[建立自訂結構描述以搭配Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

* 為Customer Journey Analytics設定資料流時，請啟用Media Analytics。

  如需啟用此選項的詳細資訊，請參閱串流媒體收集指南中的[在Adobe Experience Platform中設定資料流](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)。

  如需有關建立資料串流的資訊，請參閱[建立資料串流以搭配Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)使用。

  >[!NOTE]
  >
  >如果您的Adobe Analytics實作已使用Experience Platform Web SDK，則不需要執行此步驟。

* 建立Customer Journey Analytics的資料檢視時，請包含串流媒體收集所需的結構描述欄位。

  請確定您將這些結構描述欄位對應到XDM物件中的正確值。

  如需必要欄位的詳細資訊，請參閱串流媒體收集指南中的[在Customer Journey Analytics中建立資料檢視](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

  如需有關建立資料檢視的資訊，請參閱[在Customer Journey Analytics中建立資料檢視](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
