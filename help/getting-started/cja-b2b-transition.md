---
title: Transition指南
description: 瞭解如何從Customer Journey Analytics轉換至Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# 轉變指南

本指南會說明如何從Customer Journey Analytics轉換至Customer Journey Analytics的B2B edition。

本文假設您已在某種程度上使用Customer Journey Analytics：

* 您有[個連線](/help/connections/overview.md)可將資料擷取到Customer Journey Analytics。
* 您有[個資料檢視](/help/data-views/data-views.md)使用這些連線的資料。
* 您有[個專案](/help/analysis-workspace/home.md)，其中包含利用這些資料檢視的報告和視覺效果。

如果您之前未使用Customer Journey Analytics，請參閱[B2B edition快速入門手冊](cja-b2b-quick-start-guide.md)。

如果您是Adobe Analytics使用者並計畫使用Customer Journey Analytics B2B edition，請先參閱[從Adobe Analytics升級至Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md)檔案。


## 現有實施

一旦您獲得Customer Journey Analytics的授權並完成布建，Customer Journey Analytics B2B edition的現有實作根本不會變更。

所有現有的連線都視為[以人員為基礎的連線](cja-b2b-concepts-features.md#connections-and-identifiers)，並且在不進行任何更新的情況下繼續運作。 依賴這些人員型連線資料的所有專案（例如資料檢視、工作區專案、區段、已排程的匯出、警報等）都會繼續如期運作。

>[!IMPORTANT]
>
>您無法將現有的以人員為基礎的連線變更為以帳戶為基礎的連線。 需要新的帳戶式連線才能使用B2B edition功能。
>


## 實作B2B功能

若要在現有實作中實作B2B功能，您必須依照下列步驟操作：

1. 為您的B2B資料建立模型。 Customer Journey Analytics B2B edition至少會假設帳戶型時間序列事件資料，且受益於其他設定檔或查詢記錄資料。 例如帳戶資料、購買群組資料、機會資料、行銷清單成員資料等。

   * 定義您要用來作為主要帳戶識別碼的識別碼（帳戶ID）。 通常，現有的CRM或其他工具（例如：Demandbase）可協助您判斷該識別碼。
   * 識別您計畫使用的其他B2B資料的其他識別碼：全域帳戶識別碼、商機識別碼、購買群組識別碼和個人識別碼。

1. 準備您的B2B資料。 確保您新增並收集所有時間序列事件資料的帳戶識別碼和相關記錄資料。 同樣地，請確保您的時間序列事件資料和查詢記錄包含相關事件的其他識別碼。 例如：表示已移至另一個銷售階段的事件，應具有機會識別碼。 該識別碼應該是機會查詢資料的一部分。

1. [建立以帳戶為基礎的新連線](/help/connections/create-connection.md#account-based-connection)。 選取您要包含哪些選用容器，[新增資料集](/help/connections/create-connection.md#add-datasets)並定義每個資料集的[設定](/help/connections/create-connection.md#dataset-settings)。 儘可能使用[容器](cja-b2b-concepts-features.md#match-by-container)比對資料集以查詢記錄資料集。

1. 根據您的新連線[建立資料檢視](/help/data-views/create-dataview.md)。

   * 請確定您從已擷取的資料中新增所有相關欄位，作為量度或維度。
   * 必要時套用元件設定（例如持續性、歸因等等）。
   * 視需要新增其他衍生欄位。

1. [建立Workspace專案](/help/analysis-workspace/build-workspace-project/create-projects.md)以報告您的B2B資料並獲得深入分析。 使用特定的B2B功能（例如[容器](cja-b2b-concepts-features.md#containers)）來深入分析。

   您可以在一個工作區專案中使用多個[面板](/help/analysis-workspace/c-panels/panels.md)，以合併B2B （以人員為基礎）和B2B （以帳戶為基礎）報表和深入分析。
