---
title: 檢視目前的 Customer Journey Analytics 版本注意事項
description: 最新 CJA 版本注意事項
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0111cf5c9eaef92377a4d90b81e58c2a0432b074
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 44%

---

# 本Customer Journey Analytics(CJA)發行說明（2022年7月）

**上次更新**:2022年7月13日

>[!NOTE]
>
>此頁面包含發行前資訊並可能會變動。

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 第一個會話報告與重複會話報告 | 現在，您可以發現特定會話是否是用戶首次會話。 [瞭解更多資訊 — 要遵循] | 2022年7月20日 |
| 支援數值欄位做為查閱鍵和查閱值 | 如果您想使用數值欄位 (例如產品 SKU 上的 COGS 或利潤) 對字串值進行分類，這很有用。 允許來自查閱的量度可協助您將這些資料點納入報告中。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022年7月20日 |

## 修正

AN-288455; AN-288828; AN-289323

## CJA管理員的重要通知

| 注意 | 添加或更新 | 說明 |
| --- | --- | --- |
| 改進的IP到地理位置映射 | 2022 年 7 月 11 日 | Adobe負責IP查找的供應商Digital Element正在升級到新的改進資料集(NetAcuity Pulse)，以進行IP到地理位置的映射。 Adobe Analytics將在2022年10月，時間框架內採用這一新資料集。 新資料庫將比以前的版本更準確。 當採用新資料庫時，某些IP到地理的映射會發生變化/改進。<p> 通過分析源連接器提供的CJA資料也將自動利用新映射。 |

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
