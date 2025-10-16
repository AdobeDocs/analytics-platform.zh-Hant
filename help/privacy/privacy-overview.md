---
title: Customer Journey Analytics 和資料控管
description: 說明資料控管如何在 Customer Journey Analytics 中運作。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
source-git-commit: 40706e3118cbaf7582d8625d307358b16f1836ac
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 100%

---

# Adobe Customer Journey Analytics 和資料控管

一般而言，Customer Journey Analytics 中的任何資料控管相關設定是從 Adobe Experience Platform 繼承。

## 資料控管

Adobe Customer Journey Analytics 和 [Adobe Experience Platform 資料控管](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html)整合後，便可以標記敏感的 Customer Journey Analytics 資料以及執行隱私權原則。

在 Experience Platform 使用的資料集上所建立的隱私權標籤和原則，可以出現在 Customer Journey Analytics 資料檢視工作流程中。這些標籤會阻止或警告從敏感性欄位建立量度和/和維度的使用者。

此外，從 Customer Journey Analytics (透過報告、匯出、API 等) 匯出資料時，便會新增其他警告或標籤，以通知使用者報告包含需要以特定方式處理敏感性資訊。

此整合可讓您更輕鬆地管理合規性。在您組織中的資料監管員可以設定限制使用的原則。因此，您的 Customer Journey Analytics 使用者可以更秘密地使用資料，了解資料符合資料監管員定義的原則。

[了解更多](/help/data-views/data-governance.md)

## 隱私權請求

Adobe 根據適用的本地和國際法律來處理隱私權請求。

由於 Customer Journey Analytics 使用可在 Adobe Experience Platform 中取得的資料，因此 Adobe 提供 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) 來提交資料存取和刪除請求。這些請求同時適用於原始和已重設金鑰的資料集。

## GDPR

Customer Journey Analytics 不會直接訂閱一般資料保護規 (GDPR) 集中服務，而是繼承自 Experience Platform 中所有資料集的變更內容。Customer Journey Analytics 是依賴 Platform Data Lake 來執行 GDPR 刪除請求，並在請求完成時通知 Customer Journey Analytics。針對事件資料集，在 Customer Journey Analytics 中對受影響批次所作的所有變更內容，都會與 Platform 資料同步。在每次刪除請求後，受 GDPR 刪除請求所影響的設定檔和查詢資料集都會完全重新攝取。刪除請求通常會在 Data Lake 中發生刪除事件後的 7 天內完成。

## CCPA

加州消費者隱私權法案 (California Consumer Privacy Act, CCPA) 強化了美國加州居民的隱私權和消費者保護力道。本法案自 2020 年 1 月 1 日起生效。CCPA 為加州居民提供了新的資料隱私權，例如有權存取和刪除其個人資料、有權得知其個人資料是否遭到販售或揭露 (以及對象是誰)，以及有權拒絕廠商販售其個人資料。
根據 CCPA，Privacy Service 將會支援請求退出個人資料販售行列的功能。

>[!MORELIKETHIS]
>
>* [部落格：如何在 Adobe Customer Journey Analytics 中保持有效治理](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
