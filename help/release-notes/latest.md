---
title: 檢視目前的 Customer Journey Analytics 版本注意事項
description: 最新 CJA 版本注意事項
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 70ca04d647645d6ba69f07110f0deced03bd0a77
workflow-type: ht
source-wordcount: '244'
ht-degree: 100%

---

# 目前的 Customer Journey Analytics (CJA) 發行說明 (2022 年 4 月)

>[!NOTE]
>
>此頁面包含可能視情況有變動的發行前資訊。

**上次更新日期**：2022 年 4 月 19 日

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 維度子字串 | 提供多種方法來擷取字串所需部分，以用作維度項目。 此功能還允許您將字串維度視為一個陳列 (如果字串包含分隔值)。 [了解更多](../data-views/component-settings/substring.md) | 2022 年 4 月 20 日 |
| Analytics 來源連接器的資料準備 | [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) 現在與 Adobe Experience Platform 提供的[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)功能整合。Adobe Real-time Customer Data Platform (RTCDP)、CJA 和 Adobe Journey Optimizer (AJO) 客戶現在可以使用其他欄位群組來擴展 Analytics 欄位群組。 他們還可以利用 100 多個資料準備運算子，在擷取至 Adobe Experience Platform (AEP) 期間擴充 Analytics 資料。 RTCDP 客戶現在可以為個人資料啟用多個資料準備啟用的報告套裝。<p>透過 Analytics 來源連接器擷取多個報告套裝的 CJA 客戶現在可以消除報告套裝之間的欄位差異。 例如，如果「搜尋用語」儲存在一個報告套裝中的 `eVar1`，以及在另一個報告套裝中的 `eVar2`，則使用資料準備就可以新增一個合併兩個 eVar 值的新欄位來擴展 Analytics 欄位群組。 | 2022 年 4 月 27 日 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
