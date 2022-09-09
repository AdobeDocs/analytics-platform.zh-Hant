---
title: 將資料從Google Analytics移轉至Customer Journey Analytics
description: 了解如何將資料從Google Analytics移至Adobe Experience Platform，以及檢視Customer Journey Analytics中報表的整體工作流程。
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# 將資料從Google Analytics移轉至Customer Journey Analytics

如果您是初次Customer Journey Analytics，貴組織可能有其他Analytics平台上的現有資料，例如Google Analytics。 您可以依照下列總體步驟將該資料移入Adobe Experience Platform，讓您以Customer Journey Analytics檢視報表。

歷史資料和目前資料收集都提供工作流程。 您可以根據組織的資料需求，遵循其中一或兩個工作流程。

## 將歷史資料從Google Analytics帶入Adobe Experience Platform

擷取歷史（回填）資料時，會從Google匯出資料，並將該資料匯入Adobe Experience Platform。 請參閱 [在Adobe Experience Platform中內嵌Google Analytics資料](backfill.md).

成功將歷史資料帶入Platform後，您可以 [設定串流目前的資料](streaming.md)，或透過 [建立連線](/help/connections/create-connection.md).

## 設定Adobe Experience Platform的現有Google Analytics實作 {#configure}

擷取目前（串流）資料時，會將資料傳送至Adobe Experience Edge,Experience Edge再將該資料轉送至Adobe Experience Platform。 請參閱 [在Adobe Experience Platform中設定串流Google Analytics資料](streaming.md).

## 在CJA中設定連線和資料檢視

成功內嵌歷史資料及/或設定資料收集至Adobe Experience Platform後，您可以 [建立連線](/help/connections/create-connection.md) 允許Customer Journey Analytics參考該資料。

使用連線建立一或多個 [資料檢視](/help/data-views/create-dataview.md) 供Analysis Workspace使用。

## 建立報表

在「資料檢視」中設定維度和量度後，您就可以開始使用Analysis Workspace產生所需的報表。 請參閱 [報告Google Analytics資料Customer Journey Analytics](report.md).
