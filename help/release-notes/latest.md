---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5a38bb3a792b1b5b998e60870eb40a5aeced4280
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 本Customer Journey Analytics(CJA)發行說明（2022年8月）

**上次更新**:2022年8月12日

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **媒體同時檢閱者面板** | 了解高峰期同時觀看或使用者數下降的位置。 取得內容品質和檢閱者參與的寶貴見解，並取得疑難排解或規劃數量和規模的協助。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022 年 8 月 9 日 |
| **「媒體播放時間」面板** | 「媒體播放時間」提供寶貴的觀眾參與度深入分析，並可讓媒體組織透過進階花費時間分析及日時段分割功能，取得更深入、更細微的分析並包含每分鐘的使用者參與度。 您可以觀察使用者在特定時間點觀看您的媒體串流所花的時間多寡。 您可以依不同的資料粒度 (包括新的 5 分鐘、15 分鐘和 30 分鐘資料粒度) 分割播放持續時間。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022 年 8 月 9 日 |
| **將對象發佈到即時客戶個人檔案** | 允許您將在 CJA 中發現的受眾發佈到 Adobe Experience Platform/ 即時客戶概要檔案，以便客戶定位和個性化。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=zh-Hant) | 2022 年 8 月 17 日 |
| **CJA對資料治理標籤和策略的支援** | 自動整合CJA和Adobe Experience Platform隱私標籤和策略。 在平台使用的資料集上建立的資料標籤會在CJA資料視圖中出現，以停止或警告從敏感欄位建立度量和/或維的用戶。 此外，當從CJA導出資料時(通過工作區或Report Builder報告、導出、API等) 將添加其他警告或標籤，以通知用戶報告包含需要以特定方式處理的敏感資訊。 [了解更多](/help/data-views/data-governance.md) | 2022 年 8 月 17 日 |
| **CJA（通用提升和置信度）實驗面板** | 此新的Workspace面板使CJA用戶能夠從任何來源評估任何A/B實驗的提升力和信心 — 線上、離線、Adobe解決方案、Adobe Journey Optimizer甚至BYO資料。 更多資訊。 | 2022 年 8 月 17 日 |
| **CJA中的日期欄位支援** | 允許CJA報告日期和日期時間欄位。 [了解更多](/help/data-views/data-views-usecases.md#date) | 2022 年 8 月 17 日 |
| **分析源連接器跨區域支援** | 您現在可以從任何地區（美國、英國或新加坡）接收報告套件。 但是，這些報告套件必須映射到與建立源連接的Experience Platform沙盒實例相同的組織。 [了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) | 2022 年 8 月 24 日 |
| **首次與重複工作階段報告** | 您現在可以探索特定工作階段是否為使用者的首次工作階段。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hant#new-repeat) | 2022 年 8 月 24 日 |

{style=&quot;table-layout:auto&quot;}

## 修正

AN-297141

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **已改良 IP 對地理位置的對應** | 2022 年 7 月 11 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics將在 **2022年10月** 時間範圍。 新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |

{style=&quot;table-layout:auto&quot;&quot;

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
