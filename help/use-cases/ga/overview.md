---
title: 將資料從 Google Analytics 移轉到 Customer Journey Analytics
description: 學習關於如何將資料從 Google Analytics 移轉到 Adobe Experience Platform 包羅萬象的工作流程，並在 Customer Journey Analytics 檢視報告。
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 79%

---

# 將資料從 Google Analytics 移轉到 Customer Journey Analytics

如果您第一次使用 Customer Journey Analytics，貴組織可能在另一個 Analytics 平台已經有既存的資料，例如 Google Analytics 等。 您可以依照這些包羅萬象的步驟，將資料移轉到 Adobe Experience Platform，讓您在 Customer Journey Analytics 檢視報告。

所提供的工作包括歷史資料與最新的資料彙集。 如果貴組織的資料需求而定，您可以依照下列其中一項或二項工作流程：

## 從 Google Analytics 將歷史資料帶入 Adobe Experience Platform

擷取歷史 (回填) 資料涉及將資料從 Google 匯出，並將資料匯入 Adobe Experience Platform。 請參閱[將 Google Analytics 資料擷取至 Adobe Experience Platform ](backfill.md)。

將歷史資料成功攜入平台後，您可以 [設定串流目前的資料](streaming.md)，或立即開始回報Customer Journey Analytics中的回填資料，回報者： [建立連線](/help/connections/create-connection.md).

## 設定既存的 Google Analytics 實作，以用於 Adobe Experience Platform {#configure}

擷取目前（串流）資料涉及將資料傳送至Adobe Experience Platform Edge Network，然後再將資料轉送至Adobe Experience Platform。 請參閱[在 Adobe Experience Platform 設定 Google Analytics 資料](streaming.md)。

## 在Customer Journey Analytics中設定連線和資料檢視

在成功將歷史資料和/或設定資料彙集至 Adobe Experience Platform 後，您可以[建立連線](/help/connections/create-connection.md)，允許 Customer Journey Analytics 參照該資料。

使用連線建立一個或多個[資料檢視](/help/data-views/create-dataview.md)，以用於 Analysis Workspace。

## 建立報告

在「資料檢視」中設定維度和度量之後，您可以開始使用 Analysis Workspace 產生想要的報告。 請參閱[在 Customer Journey Analytics 中關於 Google Analytics 的報告](report.md)。
