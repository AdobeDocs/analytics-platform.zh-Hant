---
description: 瞭解警示與Adobe Analytics的Customer Journey Analytics有何不同
title: 警報功能比較Customer Journey Analytics與Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# 警報功能比較：Customer Journey Analytics和Adobe Analytics

在Customer Journey Analytics中使用警報的程式幾乎與在Adobe Analytics中使用警報的程式相同。 不過，兩者之間還是有重大差異。

以下各節將說明主要差異。

## Customer Journey Analytics中不提供每小時警報

在Adobe Analytics中，Customer Journey Analytics不提供每小時警報。 在Customer Journey Analytics中，可設定每日、每週或每月警報。

這是因為在Customer Journey Analytics中報告資料之前，可以將資料擷取到Adobe Experience Platform中的各種方式。 資料完整性與可用性無法在一小時內可靠地達成，因此每小時警示會因資料不完整的可能性高而不切實際。 如需詳細資訊，請參閱[資料擷取時間會有所不同](#data-ingestion-times-vary-in-customer-journey-analytics)。

## 資料擷取時間因Customer Journey Analytics而異

資料完成及可在Customer Journey Analytics中報告之前所需的時間因組織而異。

原因如下：

* Platform儲存各種資料結構和型別的能力

  與Adobe Analytics （僅報告網頁資料）不同，可以將[許多不同型別的資料擷取到Adobe Experience Platform](/help/data-ingestion/data-ingestion.md)中以在Customer Journey Analytics中報告，並且不是所有型別的資料都可以依序即時傳送。

* 將批次資料傳遞至Platform資料集時的延遲

  雖然有些資料可能可以更早報告，但所有[批次資料都會內嵌到Platform資料集](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)中，通常是在資料事件時間後的3到9小時。 若要讓警報準確，資料擷取必須完成，且資料集中提供所有批次資料。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

基於這些原因，對於可以擷取的各種事件資料而言，資料擷取只有在延遲一段時間後才會完成，延遲時間通常比資料事件時間晚3至9小時。 為了警示準確，指定事件範圍的事件資料必須完整，這表示Adobe不再接收指定事件範圍的任何事件資料。

考慮到這種擷取時間延遲，警報在傳送前的預設延遲為9小時。

您可以將9小時的預設延遲調整為0到24小時之間的任何時間。 但是，將延遲減少到9小時以下可能表示您報告的是不完整的資料，這會導致不準確的警報資訊。

如需有關如何調整延遲的詳細資訊，以及調整延遲時應考慮的因素，請參閱[建立警示](/help/components/c-intelligent-alerts/alert-builder.md)。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## 從Analysis Workspace建立警報的選項無法使用

在Adobe Analytics的Analysis Workspace中，您可以透過以下所述的任何方式從Analysis Workspace建立警報。 在Customer Journey Analytics中，尚未提供從Analysis Workspace建立警報的選項。 請改為存取警報產生器，如[建立警報](/help/components/c-intelligent-alerts/alert-builder.md)中所述。

Adobe Analytics提供下列選項：

* 在自由表格中選取一或多個行專案，然後按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL 從選取範圍建立警報]**。

  如此會立即預先填入警報產生器，使用正確的量度和篩選器建立警報。

* 在Analysis Workspace中開啟專案，然後選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 建立警報]**。

* 在Analysis Workspace中開啟專案，然後使用下列捷徑：

  `ctrl (or cmd) + shift + a`






