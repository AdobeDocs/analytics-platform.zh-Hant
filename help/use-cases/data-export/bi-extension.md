---
title: Customer Journey Analytics BI 擴充功能
description: 說明如何使用BI擴充功能將數位資料匯入您自己的BI工具或資料湖，以便與其他資料集搭配使用。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# BI 擴充功能

本文概述如何使用[!DNL Customer Journey Analytics BI extension]實作下列[資料匯出使用案例](overview.md)：

* Data Lake、Data Warehouse或BI工具

## 簡介

使用[!DNL Customer Journey Analytics BI extension]匯出資料可讓您從Customer Journey Analytics資料檢視匯出資料。

![BI延伸模組](../assets/bi-extension.png)

## 更多資訊

[!DNL Customer Journey Analytics BI extension] 讓 SQL 可以存取您在 Customer Journey Analytics 中定義的[資料檢視](/help/data-views/data-views.md)。 您的資料工程師和分析人員更熟悉Power BI、Tableau或其他商業智慧和視覺化工具（進一步稱為BI工具）。 他們現在可以根據 Customer Journey Analytics 使用者在建立 Analysis Workspace 專案時所使用的相同資料檢視來建立報告和儀表板。

BI擴充功能會傳回彙總資料，而非原始事件層級列。 依預設，每個查詢都會在30天的日期範圍內傳回50列，但您可以將列限制覆寫為最多50,000列，並將日期範圍覆寫為您自己的自訂範圍。 如需詳細資訊，請參閱[預設值和限制](../../data-views/bi-extension.md#defaults-and-limitations)。

如需詳細資訊，請參閱有關[BI擴充功能](../../data-views/bi-extension.md)的詳細檔案。
