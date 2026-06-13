---
title: 從 Google Analytics 移轉資料
description: 學習關於如何將資料從 Google Analytics 移轉到 Adobe Experience Platform 包羅萬象的工作流程，並在 Customer Journey Analytics 檢視報告。
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 70%

---

# 從 Google Analytics 移轉資料

>[!BEGINSHADEBOX]

本指南說明管理員的資料移轉。 如果您是想要在Customer Journey Analytics中尋找GA4報表的分析師，請參閱[從Google Analytics 4轉變為Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md)和[Customer Journey Analytics中的GA4報表](/help/getting-started/ga-to-cja/reports.md)。

>[!ENDSHADEBOX]

如果您第一次使用 Customer Journey Analytics，貴組織可能在另一個 Analytics 平台已經有既存的資料，例如 Google Analytics 等。 您可以依照這些包羅萬象的步驟，將資料移轉到 Adobe Experience Platform，讓您在 Customer Journey Analytics 檢視報告。

所提供的工作包括歷史資料與最新的資料彙集。 如果貴組織的資料需求而定，您可以依照下列其中一項或二項工作流程：

## 從 Google Analytics 將歷史資料帶入 Adobe Experience Platform

擷取歷史 (回填) 資料涉及將資料從 Google 匯出，並將資料匯入 Adobe Experience Platform。 請參閱[將 Google Analytics 資料擷取至 Adobe Experience Platform ](backfill.md)。

成功將歷史資料帶入Platform後，您可以[設定串流最新的資料](streaming.md)，或透過[建立連線](/help/connections/create-connection.md)立即開始報告Customer Journey Analytics中的回填資料。

## 設定既存的 Google Analytics 實作，以用於 Adobe Experience Platform {#configure}

擷取目前（串流）資料涉及將資料傳送至Adobe Experience Platform Edge Network，然後再將資料轉送至Adobe Experience Platform。 請參閱[在 Adobe Experience Platform 設定 Google Analytics 資料](streaming.md)。

## 在Customer Journey Analytics中設定連線和資料檢視

在成功將歷史資料和/或設定資料彙集至 Adobe Experience Platform 後，您可以[建立連線](/help/connections/create-connection.md)，允許 Customer Journey Analytics 參照該資料。

使用連線建立一個或多個[資料檢視](/help/data-views/create-dataview.md)，以用於 Analysis Workspace。

## 建立報告

在「資料檢視」中設定維度和度量之後，您可以開始使用 Analysis Workspace 產生想要的報告。 請參閱[在 Customer Journey Analytics 中關於 Google Analytics 的報告](report.md)。
