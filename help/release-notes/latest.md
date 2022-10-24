---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3028024c97355cb43fb7a844acef5771d2f5cbcf
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 76%

---

# Customer Journey Analytics(CJA)發行說明（2022年10月/11月）

**上次更新日期**：2022 年 10 月 19 日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 主要功能和更新

| 功能 | 說明 | [轉出開始](/help/release-notes/releases.md) | [全面發佈](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL 關鍵量度摘要]視覺化** | [!UICONTROL 關鍵量度摘要]視覺化可讓您查看重要量度在單一時間範圍內的趨勢分析。也能讓您比較兩個時間範圍內的量度成效。[了解更多](/help/analysis-workspace/visualizations/key-metric.md) | 2022 年 10 月 5 日 | 2022 年 10 月 19 日 |
| **不區分大小寫的多值變數** | 對於不區分大小寫的多值變數，儲存在 `mvvar1` - `mvvar3` 中的值將不再自動採用小寫。相反的，透過 Analytics Source Connector 傳遞到 Adobe Experience Platform 和 CJA 的資料將反映從頁面傳入的原始大小寫。 | 不適用 | 2022 年 10 月 24 日 |
| **CJA稽核記錄** | Customer Journey Analytics(CJA)可讓您以「稽核記錄」的形式，稽核各種服務和功能的使用者活動。 這些日誌形成了一個審核跟蹤，可以幫助排除問題，並幫助您的企業有效遵守公司資料管理政策和法規要求，如健康保險可移植性和責任法案(HIPAA)。 這些記錄檔先前只能透過稽核記錄API使用。 [後續文件] | 不適用 | 2022 年 10 月 26 日 |
| **CJA HIPAA整備** | 後續說明 | 不適用 | 2022 年 10 月 26 日 |

{style=&quot;table-layout:auto&quot;}

## 修正

* 修正最新MacOS版本未正確命名為「Macintosh」的問題。 透過此修正，作業系統維度將從MacOS 11開始，開始使用「MacOS」版本編號。 (AN-301834)

### 其他  修正

AN-302367；AN-302562

## 給 CJA 管理員的重要通知

| 通知 | 已新增或更新通知 | 說明 |
| --- | --- | --- |
| **預設登陸頁面** | 2023 年 9 月 29 日 | 今年早些時候推出的[新登陸頁面](/help/getting-started/landing.md)將在 **2023 年 1 月**&#x200B;成為所有使用者的預設體驗。目前頁面將被淘汰，將要求所有人都使用新體驗。 |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 29 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics 已將這個新資料集的採用延後到 **2023 年 1 月**。新資料庫將會比舊版更準確。在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過 [!UICONTROL Analytics Source Connector] 提供的 CJA 資料也將自動利用新的對應。 |
| **[!UICONTROL 異常偵測]自動執行條件** | 2022 年 9 月 29 日 | 今天，[!UICONTROL 異常偵測]會在時間序列任意格式表的所有欄上自動執行。為確保資料可用於分析並加快專案載入速度，Adobe 將改變[!UICONTROL 異常偵測]自動執行的方式。自&#x200B;**2022 年 10 月 26 日**&#x200B;開始，異常偵測將僅在表格中的第一個量度欄上自動執行。如果需要，您可以設定欄設定以在其他欄上執行[!UICONTROL 異常偵測]。 |

{style=&quot;table-layout:auto&quot;}


## 相關資源

* [2022 年舊版 CJA 發行說明](/help/release-notes/2022.md)

* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)

* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
