---
title: 客戶歷程分析隱私權概觀
description: 說明隱私權設定在「客戶歷程分析」中的運作方式。
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# 客戶歷程分析隱私權概觀

一般而言，「客戶歷程分析」中任何與隱私權相關的設定都會繼承自Adobe Experience Platform。

## GDPR

客戶歷程分析將不直接訂閱通用資料保護規則(GDPR)中央服務，而會繼承Experience Platform中所有資料集變更。 我們依賴Platform Data Lake強制執行GDPR刪除請求，並在Pipeline上完成時通知我們。 我們會監聽Pipeline，並同步客戶歷程分析中針對事件資料集對受影響批次的所有變更。 每個刪除請求後，受GDPR刪除請求影響的描述檔和查閱資料集都會完全重新收錄。 我們可以保證刪除請求會在資料湖的刪除事件發生7天內執行。

## CCPA

加州消費者隱私權法案 (California Consumer Privacy Act, CCPA) 強化了美國加州居民的隱私權和消費者保護力道。此法案已訂於 2020 年 1 月 1 日生效。CCPA 為加州居民提供了新的資料隱私權，例如有權存取和刪除其個人資料、有權得知其個人資料是否遭到販售或揭露 (以及對象是誰)，以及有權拒絕廠商販售其個人資料。有鑑於 CCPA 即將生效，隱私權服務將會支援請求退出個人資料販售行列的功能。
