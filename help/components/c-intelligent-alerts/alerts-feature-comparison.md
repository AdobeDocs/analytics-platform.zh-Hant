---
description: 瞭解Customer Journey Analytics與Adobe Analytics的警報有何不同
title: 警報功能比較Customer Journey Analytics與Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
TQID: https://experienceleague.adobe.com/NEm3Mu7q6RDKbCyG-PJzOFPrjJF4Y-unHgyBXyKd1HM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
    internal-label: Alerts
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 4f3c4a214bb9676ced6fe3c9627c969413013790
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 23%
---
# 警報功能比較Customer Journey Analytics與Adobe Analytics

在 Customer Journey Analytics 中使用警報的流程，與在 Adobe Analytics 中使用警報的流程幾乎相同。 儘管如此，還是有些重要差異。 以下各節將說明主要差異。

## 針對特定型別的資料，每小時警報可能不切實際

由於您可以將各種型別的資料擷取至Adobe Experience Platform，因此並非所有可包含在警報中的資料都適合每小時警報。 特定型別的資料無法可靠地擷取，且在一小時的限制內提供。

如需詳細資訊，請參閱[資料擷取時間會有所不同](#data-ingestion-times-vary)。

## 資料擷取時間不盡相同

資料完成及可在Customer Journey Analytics中報告之前所需的時間因組織而異。

原因如下：

* Platform儲存各種資料結構和型別的能力

  不同於Adobe Analytics （僅報告網頁資料），可以將[許多不同型別的資料擷取到Adobe Experience Platform](/help/data-ingestion/data-ingestion.md)中以在Customer Journey Analytics中報告，並且不是所有型別的資料都可以依序即時傳送。

* 將批次資料傳遞至Platform資料集時的延遲

  雖然有些資料可能可以更早報告，但所有[批次資料都會內嵌到Platform資料集](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)中，通常是在資料事件時間後的3到9小時。 若要讓警報準確，資料擷取必須完成，且資料集中提供所有批次資料。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

基於這些原因，對於可以擷取的各種事件資料而言，資料擷取只有在延遲一段時間後才會完成，延遲時間通常比資料事件時間晚3至9小時。 為了確保警報準確，特定事件範圍的事件資料必須完整，這表示 Adob&#x200B;&#x200B;e 不再接收指定事件範圍的任何事件資料。

為了解決攝取時間的延遲，警報發送前的預設延遲時間為 9 小時。

您可以將預設延遲時間從 9 小時調整為 0 至 24 小時之間的任意值。 但是，將延遲時間減少到 9 小時以下可能表示您報告的資料不完整，這會導致警報資訊不準確。

如需有關如何調整延遲的詳細資訊，以及調整延遲時應考慮的因素，請參閱[建立警示](/help/components/c-intelligent-alerts/alert-builder.md)。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## 建立警報的次數較少

在Adobe Analytics的Analysis Workspace中，您可以[以多種方式從Analysis Workspace建立警報](https://experienceleague.adobe.com/zh-hant/docs/analytics/components/alerts/alert-builder)。 在Customer Journey Analytics中，您只能從自由格式表格中的選取範圍[在Analysis Workspace中建立警報](alert-builder.md)。

Adobe Analytics和Customer Journey Analytics都支援透過[警報管理器](alert-manager.md)建立警報
