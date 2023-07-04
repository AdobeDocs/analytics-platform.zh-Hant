---
title: Customer Journey Analytics 術語
description: Customer Journey Analytics 術語。
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
feature: Basics
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 88%

---

# Customer Journey Analytics 術語

部分 Customer Journey Analytics 術語與 Adobe Analytics 中一般所使用的術語不同：

| Customer Journey Analytics 新術語 | Adobe Analytics 術語 | 說明 |
| --- | --- | --- |
| 查詢資料集 | 分類 | 使用查詢功能，從具有 1 對 1 關係的指定資料集中擷取金鑰/相符金鑰 (位於事件資料集中) 的值。例如，您可以指定「tracking_code」作為符合事件資料集中「tracking_code」的金鑰。 |
| 設定檔資料集 | 客戶屬性 | 如果您在客戶關係管理 (CRM) 資料庫中擷取企業客戶資料，可將這些資料上傳至 Adobe Experience Platform 上的設定檔資料集中。在 Customer Journey Analytics 中建立與該資料集的連線並建立資料檢視後，可在工作區中使用資料。 |
| Experience Cloud 組織 | 登入公司 | 請參閱[組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=zh-Hant#topic_C31CB834F109465A82ED57FF0563B3F1)。 |
| 不適用 | 報告套裝 | 傳統 Adobe Analytics 環境中的報告套裝已不存在，改為需從您建立連線的 Platform 資料集建立 (虛擬) [資料檢視](/help/data-views/create-dataview.md)。 |
| 篩選器 | 區段 | 區段現在稱為篩選器。Customer Journey Analytics 中的篩選器行為與區段相同，只有使用的術語有所不同。 |
| 資料檢視 | 虛擬報告套裝 | 在 Adobe Analytics 中，虛擬報告套裝是父報告套裝的篩選檢視。虛擬報表套裝與Customer Journey Analytics資料檢視的主要差異在於，虛擬報表套裝是「基本」或「父」報表套裝的子集，因此會繼承其部分設定。 由於父/基本報告套裝已不存在，因此可以使用其自己的設定來定義資料檢視。 |

## Adobe Experience Platform 術語

Adobe Experience Platform 可標準化整個企業的資料和內容、提供即時的消費者個人檔案、運用資料科學，以及加快內容速度，藉此促進客戶歷程中的體驗個人化。
如需詳細資訊，請參閱 [Adobe Experience Platform 術語](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html)。
