---
title: 檢視目前的 Customer Journey Analytics 版本注意事項
description: 最新 CJA 版本注意事項
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e1e147b63053f63c90d8e433d90e1bc5a4f1acd4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 49%

---

# 本Customer Journey Analytics(CJA)發行說明（2022年7月）

**上次更新**:2022年7月19日

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 支援數值欄位做為查閱鍵和查閱值 | 如果您想使用數值欄位 (例如產品 SKU 上的 COGS 或利潤) 對字串值進行分類，這很有用。 允許來自查閱的量度可協助您將這些資料點納入報告中。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022年7月20日 |
| 媒體同時檢閱者面板 | 了解尖峰並行存取發生在何處或是下降發生在何處。取得內容品質和檢閱者參與的寶貴見解，並取得疑難排解或規劃數量和規模的協助。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022年7月30日 |
| 「媒體播放時間」面板 | 媒體播放所花時間可提供對觀眾參與的寶貴洞察力，並使媒體組織能夠通過利用日分段功能進行的高級時間分析，逐分鐘地獲得更深入、更細緻的見解。 您可以觀察在特定時間點觀看您的媒體串流所花費的時間多寡。您可以依不同的資料粒度 (包括新的 5 分鐘、15 分鐘和 30 分鐘資料粒度) 分割播放持續時間。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022年7月30日 |
| 第一個會話報告與重複會話報告 | 現在，您可以發現特定會話是否是用戶首次會話。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 2022 年 8 月 17 日 |

{style=&quot;table-layout:auto&quot;}

## 修正

AN-288455; AN-288828; AN-289323

## CJA管理員的重要通知

| 注意 | 已添加或更新通知 | 說明 |
| --- | --- | --- |
| **改進的IP到地理位置映射** | 2022 年 7 月 11 日 | Adobe負責IP查找的供應商Digital Element正在升級到新的改進資料集(NetAcuity Pulse)，以進行IP到地理位置的映射。 Adobe Analytics將在 **2022年10月**，時間範圍。 新資料庫將比以前的版本更準確。 當採用新資料庫時，某些IP到地理的映射會發生變化/改進。<p> 通過分析源連接器提供的CJA資料也將自動利用新映射。 |

{style=&quot;table-layout:auto&quot;&quot;

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
