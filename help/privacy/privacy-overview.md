---
title: Customer Journey Analytics和資料治理
description: 介紹資料治理在Customer Journey Analytics中的工作方式。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 61850e8a1da80a115bf850c64358a512770f852e
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics和資料治理

一般來說，Customer Journey Analytics中任何與資料治理相關的設定都是從Adobe Experience Platform繼承的。

## 資料控管

CJA支援在Adobe Experience Platform設定的資料治理標籤和策略。 有關詳細資訊，請參閱CJA對Adobe Experience Platform資料治理的支援。

## GDPR

Customer Journey Analytics 不會直接訂閱一般資料保護規 (GDPR) 集中服務，而是繼承自 Experience Platform 中所有資料集的變更內容。我們仰賴 Platform Data Lake 強制執行 GDPR 刪除請求，並於這些請求在 Pipeline 上完成時通知我們。我們會監聽 Pipeline，並針對事件資料集，同步 Customer Journey Analytics 中對受影響批次所作的所有變更內容。在每次刪除請求後，受 GDPR 刪除請求所影響的設定檔和查詢資料集都會完全重新內嵌。我們可以保證刪除請求會在 Data Lake 中發生刪除事件後的 7 天內執行。

## CCPA

加州消費者隱私權法案 (California Consumer Privacy Act, CCPA) 強化了美國加州居民的隱私權和消費者保護力道。此法案已訂於 2020 年 1 月 1 日生效。CCPA 為加州居民提供了新的資料隱私權，例如有權存取和刪除其個人資料、有權得知其個人資料是否遭到販售或揭露 (以及對象是誰)，以及有權拒絕廠商販售其個人資料。有鑑於 CCPA 即將生效，隱私權服務將會支援請求退出個人資料販售行列的功能。
