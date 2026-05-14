---
description: 瞭解如何使用資料摘要從Customer Journey Analytics中取得原始資料。 了解使用資料摘要的先決條件以及接下來該做的步驟。
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: Analytics 資料摘要概觀
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 21%

---

# 資料摘要概觀

資料摘要是從Customer Journey Analytics中取得原始資料的有力方式。 您可以由組織自行決定，在Adobe以外的其他平台中使用這些原始資料。 資料會在每小時結束時以小時的批次傳送，或在每天結束時以當天的批次傳送。

## 先決條件

在使用資料摘要之前，請確定您符合下列所有需求：

* 具有已擷取至Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->之資料的有效實作
* 您的帳戶是Analytics產品管理員，或屬於可存取資料摘要<!--???-->的產品設定檔
* 在{DNL Amazon S3}、{DNL Google Cloud Platform}、{DNL Azure RBAC}或上設定的貯體 {DNL Azure SAS}

## 開始使用

若要開始使用Customer Journey Analytics中的資料摘要，請先瞭解Customer Journey Analytics中的資料摘要與Adobe Analytics中的資料摘要有何不同。 瞭解差異後，您可以將Adobe Analytics資料摘要對應至Customer Journey Analytics，然後開始建立資料摘要。

1. [瞭解Customer Journey Analytics和Adobe Analytics中的資料摘要之間的差異](/help/components/exports/cja-data-feeds/df-comparison.md)。

1. [將Adobe Analytics資料摘要資料行對應至Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

1. [建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)。
