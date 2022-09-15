---
title: 將資料從 Google Analytics 移轉到 Customer Journey Analytics
description: 學習關於如何將資料從 Google Analytics 移轉到 Adobe Experience Platform 包羅萬象的工作流程，並在 Customer Journey Analytics 檢視報告。
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# 將資料從 Google Analytics 移轉到 Customer Journey Analytics

如果您第一次使用 Customer Journey Analytics，貴組織可能在另一個 Analytics 平台已經有既存的資料，例如 Google Analytics 等。 您可以依照這些包羅萬象的步驟，將資料移轉到 Adobe Experience Platform，讓您在 Customer Journey Analytics 檢視報告。

所提供的工作包括歷史資料與最新的資料彙集。 如果貴組織的資料需求而定，您可以依照下列其中一項或二項工作流程：

## 從 Google Analytics 將歷史資料帶入 Adobe Experience Platform

擷取歷史 (回填) 資料涉及將資料從 Google 匯出，並將資料匯入 Adobe Experience Platform。 請參閱[將 Google Analytics 資料擷取至 Adobe Experience Platform ](backfill.md)。

在將歷史資料成功攜入平台後，您可以[設定串流最新的資料](streaming.md)，或是建立連線，[立即開始在 CJA 報告回填的資料](/help/connections/create-connection.md)。

## 設定既存的 Google Analytics 實作，以用於 Adobe Experience Platform {#configure}

擷取最新的 (串流) 資料涉及將資料傳送至 Adobe Experience Edge，然後再將資料轉傳至 Adobe Experience Platform。 請參閱[在 Adobe Experience Platform 設定 Google Analytics 資料](streaming.md)。

## 在 CJA 中設定連線與資料檢視

在成功將歷史資料和/或設定資料彙集至 Adobe Experience Platform 後，您可以[建立連線](/help/connections/create-connection.md)，允許 Customer Journey Analytics 參照該資料。

使用連線建立一個或多個[資料檢視](/help/data-views/create-dataview.md)，以用於 Analysis Workspace。

## 建立報告

在「資料檢視」中設定維度和度量之後，您可以開始使用 Analysis Workspace 產生想要的報告。 請參閱[在 Customer Journey Analytics 中關於 Google Analytics 的報告](report.md)。
