---
title: Customer Journey Analytics 和資料控管
description: 說明資料控管如何在 Customer Journey Analytics 中運作。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 612fce23fe4cb9920c05f3253d69e543668a7cf1
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 54%

---

# Adobe Customer Journey Analytics和資料控管

一般而言，Customer Journey Analytics 中的任何資料控管相關設定是從 Adobe Experience Platform 繼承。

## 資料控管

Adobe Customer Journey Analytics與[Adobe Experience Platform資料控管](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html)之間的整合可讓您標示敏感的Customer Journey Analytics資料強制執行隱私權原則。

在 Experience Platform 使用的資料集上所建立的隱私權標籤和原則，可以出現在 Customer Journey Analytics 資料檢視工作流程中。這些標籤會阻止或警告從敏感性欄位建立量度和/和維度的使用者。

此外，從Customer Journey Analytics （透過報告、匯出、API等）匯出資料時，便會新增警告或標籤，以通知使用者報告包含需要以特定方式處理敏感性資訊。

此整合可讓您更輕鬆地管理合規性。在您組織中的資料監管員可以設定限制使用的原則。因此，您的Customer Journey Analytics使用者可以更自信地使用資料，瞭解資料符合資料管理員定義的原則。

[了解更多](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics 不會直接訂閱一般資料保護規 (GDPR) 集中服務，而是繼承自 Experience Platform 中所有資料集的變更內容。Customer Journey Analytics仰賴Platform Data Lake強制執行GDPR刪除請求，並在請求完成時通知Customer Journey Analytics。 事件資料集之Customer Journey Analytics中對受影響批次所做的所有變更都會與Platform資料同步。 在每次刪除請求後，受GDPR刪除請求影響的設定檔和查詢資料集都會完全重新內嵌。 刪除請求通常會在Data Lake中發生刪除事件後的7天內完成。

## CCPA

加州消費者隱私權法案 (California Consumer Privacy Act, CCPA) 強化了美國加州居民的隱私權和消費者保護力道。本法案自 2020 年 1 月 1 日起生效。CCPA 為加州居民提供了新的資料隱私權，例如有權存取和刪除其個人資料、有權得知其個人資料是否遭到販售或揭露 (以及對象是誰)，以及有權拒絕廠商販售其個人資料。
根據 CCPA，Privacy Service 將會支援請求退出個人資料販售行列的功能。

>[!MORELIKETHIS]
>
>* [部落格：如何在Adobe Customer Journey Analytics中維持有效治理](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
