---
description: 瞭解Customer Journey Analytics與Adobe Analytics的警報有何不同
title: 警報功能比較Customer Journey Analytics和Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 23%

---

# 警示功能比較

在 Customer Journey Analytics 中使用警報的流程，與在 Adobe Analytics 中使用警報的流程幾乎相同。不過，兩者之間還是有重大差異。 以下各節將說明主要差異。

## 無法使用每小時警報

每小時警示是&#x200B;**在Customer Journey Analytics中無法使用**，而每小時警示是在Adobe Analytics中可用。 在 Customer Journey Analytics 中，可以將警報設定為每日、每週或每月。

您可以透過多種方式將資料內嵌至Adobe Experience Platform中。 因此，在一小時的限制內，資料完整性和可用性無法可靠達成。  資料擷取的靈活性意味著，由於不完整資料的可能性很高，每小時的警報是不切實際的。 如需詳細資訊，請參閱[資料擷取時間會有所不同](#data-ingestion-times-vary-in-customer-journey-analytics)。

## 資料擷取時間不盡相同

資料完成及可在Customer Journey Analytics中報告之前所需的時間因組織而異。

原因如下：

* Platform儲存各種資料結構和型別的能力

  不同於Adobe Analytics （僅報告網頁資料），可以將[許多不同型別的資料擷取到Adobe Experience Platform](/help/data-ingestion/data-ingestion.md)中以在Customer Journey Analytics中報告，並且不是所有型別的資料都可以依序即時傳送。

* 將批次資料傳遞至Platform資料集時的延遲

  雖然有些資料可能可以更早報告，但所有[批次資料都會內嵌到Platform資料集](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)中，通常是在資料事件時間後的3到9小時。 若要讓警報準確，資料擷取必須完成，且資料集中提供所有批次資料。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

基於這些原因，對於可以擷取的各種事件資料而言，資料擷取只有在延遲一段時間後才會完成，延遲時間通常比資料事件時間晚3至9小時。 為了確保警報準確，特定事件範圍的事件資料必須完整，這表示 Adob&#x200B;&#x200B;e 不再接收指定事件範圍的任何事件資料。

為了解決攝取時間的延遲，警報發送前的預設延遲時間為 9 小時。

您可以將預設延遲時間從 9 小時調整為 0 至 24 小時之間的任意值。但是，將延遲時間減少到 9 小時以下可能表示您報告的資料不完整，這會導致警報資訊不準確。

如需有關如何調整延遲的詳細資訊，以及調整延遲時應考慮的因素，請參閱[建立警示](/help/components/c-intelligent-alerts/alert-builder.md)。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## 從Analysis Workspace建立警報無法使用

在Adobe Analytics的Analysis Workspace中，您可以透過以下所述的任何方式從Analysis Workspace建立警報。 Customer Journey Analytics尚不提供從Analysis Workspace建立警報的選項。 請改為存取警報產生器，如[建立警報](/help/components/c-intelligent-alerts/alert-builder.md)中所述。

Adobe Analytics提供下列選項：

* 在自由表格中選取一或多個行專案，然後按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL 從選取範圍建立警報]**。

  如此會立即預先填入警報產生器，使用正確的量度和區段建立警報。

* 在 Analysis Workspace 中開啟專案，然後選取「**[!UICONTROL 元件]**」>「**[!UICONTROL 建立警報]**」。

* 在Analysis Workspace中開啟專案，然後使用下列捷徑： **[!UICONTROL *ctrl *]**+**[!UICONTROL * shift *]** + **[!UICONTROL *a *]**(Windows)或&#x200B;**[!UICONTROL * cmd *]** + **[!UICONTROL *shift *]**+**[!UICONTROL * a *]** (macOS)。
