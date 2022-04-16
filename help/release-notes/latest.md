---
title: 檢視目前的 Customer Journey Analytics 版本注意事項
description: 最新 CJA 版本注意事項
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# 本Customer Journey Analytics(CJA)發行說明（2022年4月）

>[!NOTE]
>
>此頁包含可更改的預發行資訊。

**上次更新**:2022年4月13日

## 主要功能

| 功能 | 說明 | [目標日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimension子字串 | 提供多種方法以提取字串的所需部分，以用作尺寸項。 如果字串包含分隔值，則此功能還允許您將字串維視為陣列。 [了解更多](../data-views/component-settings/substring.md) | 2022 年 4 月 20 日 |
| 分析源連接器的資料準備 | 的 [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) 現在與 [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) 由Adobe Experience Platform提供。 Adobe Real-time Customer Data Platform(RTCDP)、 CJA和Adobe Journey Optimizer(AJO)客戶現在可以擴展分析欄位組，並添加其他欄位組。 他們還可以利用100多個資料準備操作員在接收到Adobe Experience Platform(AEP)期間豐富分析資料。 RTCDP客戶現在可以為配置檔案啟用多個支援資料準備的報告套件。<p>通過分析源連接器接收多個報表套件的CJA客戶現在可以消除報表套件之間的列差異。 例如，如果「搜索術語」儲存在 `eVar1` 在一個報告套件中 `eVar2` 在另一個報表套件中，使用Data Prep，您可以使用合併兩個eVar的值的新列來擴展「分析」欄位組。 | 2022 年 4 月 25 日 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
