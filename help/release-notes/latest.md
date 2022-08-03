---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b2a6225d6f94b158e217df4963611cb6d55580e
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 100%

---

# 最新 Customer Journey Analytics (CJA) 發行說明 (2022 年 7 月)

**上次更新日期**：2022 年 7 月 28 日

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 支援數值欄位做為查閱鍵和查閱值 | 如果您想使用數值欄位 (例如產品 SKU 上的 COGS 或利潤) 對字串值進行分類，這很有用。 允許來自查閱的量度可協助您將這些資料點納入報告中。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022 年 7 月 20 日 |
| 首次與重複工作階段報告 | 您現在可以探索特定工作階段是否為使用者的首次工作階段。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hant#new-repeat) | 2022 年 8 月 17 日 |
| 「媒體同時檢閱者」面板 | 了解高峰期同時觀看或使用者數下降的位置。 取得內容品質和檢閱者參與的寶貴見解，並取得疑難排解或規劃數量和規模的協助。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022 年 8 月 31 日 |
| 「媒體播放時間」面板 | 「媒體播放時間」提供寶貴的觀眾參與度深入分析，並可讓媒體組織透過進階花費時間分析及日時段分割功能，取得更深入、更細微的分析並包含每分鐘的使用者參與度。 您可以觀察使用者在特定時間點觀看您的媒體串流所花的時間多寡。 您可以依不同的資料粒度 (包括新的 5 分鐘、15 分鐘和 30 分鐘資料粒度) 分割播放持續時間。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022 年 8 月 31 日 |

{style="table-layout:auto"}

## 修正

AN-288455；AN-288828；AN-289323

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **已改良 IP 對地理位置的對應** | 2022 年 7 月 11 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics 將在 **2022 年 10 月**&#x200B;的時間範圍內採用這個新資料集。 新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
