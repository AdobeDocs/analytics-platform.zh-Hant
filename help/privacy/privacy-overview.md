---
title: Customer Journey Analytics和資料治理
description: 介紹資料治理在Customer Journey Analytics中的工作方式。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 51%

---

# Customer Journey Analytics和資料治理

一般來說，Customer Journey Analytics中任何與資料治理相關的設定都是從Adobe Experience Platform繼承的。

## 資料控管

CJA與CJA的整合 [Adobe Experience Platform資料治理](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) 允許對敏感CJA資料進行標籤並強制實施隱私策略。

可以在CJA資料視圖工作流中顯示在Experience Platform使用的資料集上建立的隱私標籤和策略。 這些標籤會停止或警告從敏感欄位建立度量和/或維的用戶。

此外，當從CJA（通過報告、導出、API等）導出資料時，會添加警告或標籤以通知用戶報告包含需要以特定方式處理的敏感資訊。

此整合使您能夠更輕鬆地管理法規遵從性。 組織中的資料管理員可以設定策略以限制使用。 因此，您的CJA用戶可以更自信地使用資料，因為它遵守了由資料管理員定義的策略。

[了解更多](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics 不會直接訂閱一般資料保護規 (GDPR) 集中服務，而是繼承自 Experience Platform 中所有資料集的變更內容。我們仰賴 Platform Data Lake 強制執行 GDPR 刪除請求，並於這些請求在 Pipeline 上完成時通知我們。我們會監聽 Pipeline，並針對事件資料集，同步 Customer Journey Analytics 中對受影響批次所作的所有變更內容。在每次刪除請求後，受 GDPR 刪除請求所影響的設定檔和查詢資料集都會完全重新內嵌。我們可以保證刪除請求會在 Data Lake 中發生刪除事件後的 7 天內執行。

## CCPA

加州消費者隱私權法案 (California Consumer Privacy Act, CCPA) 強化了美國加州居民的隱私權和消費者保護力道。本法案自 2020 年 1 月 1 日起生效。CCPA 為加州居民提供了新的資料隱私權，例如有權存取和刪除其個人資料、有權得知其個人資料是否遭到販售或揭露 (以及對象是誰)，以及有權拒絕廠商販售其個人資料。有鑑於 CCPA 即將生效，隱私權服務將會支援請求退出個人資料販售行列的功能。
