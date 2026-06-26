---
description: 瞭解如何使用資料摘要從Customer Journey Analytics中取得原始資料。 了解使用資料摘要的先決條件以及接下來該做的步驟。
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: Analytics 資料摘要概觀
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: b31ae6194d30115f4d653addaf5efff5790e987c
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 21%

---

# 資料摘要概觀

資料摘要是從Customer Journey Analytics中取得原始資料的有力方式。 您可以由組織自行決定，在Adobe以外的其他平台中使用這些原始資料。 資料會在每小時結束時以小時的批次傳送，或在每天結束時以當天的批次傳送。

## 先決條件

在使用資料摘要之前，請確定您符合下列所有需求：

* 具有已擷取至Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->之資料的有效實作
* 您的帳戶是Analytics產品管理員，或屬於可存取資料摘要<!--???-->的產品設定檔
* 在[!DNL Amazon S3]、[!DNL Google Cloud Platform]、[!DNL Azure RBAC]或[!DNL Azure SAS]上設定的貯體

## 開始使用

若要開始使用Customer Journey Analytics中的資料摘要，請先瞭解Customer Journey Analytics中的資料摘要與Adobe Analytics中的資料摘要有何不同。 瞭解差異後，您可以將Adobe Analytics資料摘要對應至Customer Journey Analytics，然後開始建立資料摘要。

1. [瞭解Customer Journey Analytics和Adobe Analytics中的資料摘要之間的差異](/help/components/exports/cja-data-feeds/df-comparison.md)。

1. [將Adobe Analytics資料摘要資料行對應至Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

1. [建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)。
