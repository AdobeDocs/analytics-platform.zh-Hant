---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新 CJA 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 673aed4daf7029ddec032055789f94125395e7f9
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 40%

---

# 最新Customer Journey Analytics(CJA)發行說明（2023年1月）

**上次更新**:2023年1月13日

Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 主要功能和更新

| 功能 | 說明 | [開始推出](/help/release-notes/releases.md) | [全面發佈](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Workspace 資料夾** | 資料夾可協助您組織和分類專案，以便更妥善地擷取和存取。 此外，共用 **[!UICONTROL 公司]** 資料夾可讓管理員輕鬆建立內容，並與所有工作區使用者共用內容。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html) | 不適用 | 2023年1月11日 |
| **預設登陸頁面** | 此 [新登陸頁面](/help/getting-started/landing.md) 於2022年初推出的體驗，將成為 **2023年1月11日**. 舊版登錄頁面將遭取代，而且每個人都需要使用新體驗。 | 不適用 | 2023年1月11日 |
| **已棄用專案管理員頁面** | 隨著新登錄頁面的發行，我們已棄用 **[!UICONTROL 專案經理]** 列於 **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 元件]**. 新登錄頁面具有舊「專案管理員」頁面的所有功能，以及更多功能。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | 不適用 | 2023年1月11日 |
| **排程Report Builder中的活頁簿** | 在Customer Journey Analytics中，您可以建立排程以定期傳送活頁簿。 現在，收件者可定期接收您活頁簿的最新更新。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | 不適用 | 2023年1月11日 |
| **自動儲存新專案** | Analysis Workspace現在會自動儲存新建立的專案。 如果出於任何原因，在手動保存新建立的項目之前意外丟失了對該項目的訪問權限，則您的項目的恢復版本現在可用。 過去，專案只會在初次手動儲存後自動儲存。 [了解更多](/help/analysis-workspace/build-workspace-project/save-projects.md) | 不適用 | 2023年1月11日 |
| **增強的使用者偏好設定** | 您現在可以在使用者層級設定其他偏好設定(在 [!UICONTROL 元件] > [!UICONTROL 偏好設定])。 當您設定使用者偏好設定時，您的選取項目會跨越專案、表格和視覺效果。 「首選項」頁現在包含以下新頁簽，每個頁簽都包含許多新配置選項：<ul><li>自由表格</li><li>視覺效果>/li></ul>. 此外，您現在可以在 **[!UICONTROL 一般]** 和 **[!UICONTROL 專案]** 頁簽。<p>以前，其中許多偏好設定只能針對個別專案、表格和視覺效果進行設定。 [了解更多](/help/analysis-workspace/user-preferences.md) | 不適用 | 2023年1月11日 |
| **設定檔和查詢資料集的物件陣列支援** | 設定檔資料集和查詢資料集現在支援物件陣列，以用於CJA。 | 不適用 | 2023年1月11日 |

{style=&quot;table-layout:auto&quot;}

## 修正

AN-287349;AN-301684;AN-305491;AN-305769;AN-307912

## 給 CJA 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 29 日 | Adobe 的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics已將此新資料集的採用延後至 **2023年1月11日**. 新資料庫將會比舊版更準確。在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p> 透過 [!UICONTROL Analytics 來源連接器]提供的 CJA 資料也將自動利用新的對應。 |

{style=&quot;table-layout:auto&quot;}


## 相關資源

* [2022 年舊版 CJA 發行說明](/help/release-notes/2022.md)

* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)

* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)

* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)

* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
