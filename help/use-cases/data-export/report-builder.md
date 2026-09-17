---
title: Customer Journey Analytics Report Builder
description: 說明如何使用Report Builder將Customer Journey Analytics資料提取到Excel中以製作週期性報表。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

本文概述如何使用[!DNL Report Builder]實作下列[資料匯出使用案例](overview.md)：

* 臨時和週期性報表

## 簡介

[!DNL Report Builder] [!DNL Report Builder]是Microsoft Excel增益集，可將Customer Journey Analytics資料提取至活頁簿中的資料區塊中。 已熟悉Excel的業務使用者無需學習Analysis Workspace或SQL，便可建立週期性報表。

## 更多資訊

[!DNL Report Builder]中的每個資料區塊最多會傳回50,000列。 若要擷取更多列，請使用&#x200B;**[!UICONTROL 頁面]**&#x200B;和&#x200B;**[!UICONTROL 列]**&#x200B;選項，在超過50,000列限制的循序頁面中提取資料。 如需詳細資訊，請參閱[篩選維度](/help/report-builder/filter-dimensions.md)。

您可以排程活頁簿以透過電子郵件傳送，或將其匯出至雲端目的地，例如Amazon S3、Google Cloud Platform或Azure。 如需詳細資訊，請參閱[透過電子郵件共用排程活頁簿](/help/report-builder/schedule-reportbuilder.md)和[匯出至雲端目的地排程活頁簿](/help/report-builder/report-builder-export.md)。

如需設定和使用[!DNL Report Builder]的簡介，請參閱[Report Builder概觀](/help/report-builder/rb-overview.md)。
