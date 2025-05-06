---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4d0ad58193217ebcff8dcf15b3d5a65f0977133f
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 72%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2025 年 4 月)

**上次更新日期**：2025年4月30日

這些發行說明涵蓋 2025 年 3 月 27 日至 2025 年 5 月 15 日的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **增加完整資料表匯出限制** | 客戶可以從5個維度和5個量度匯出完整表格，我們增加了可用於匯出完整表格的欄數，至10個維度和10個量度。 這適用於所有Customer Journey Analytics階層。 可匯出的列數權益沒有變更。 |  | 2025 年 4 月 30 日 |
| **更新了數值維度中的「無值」條列項目** | 對於數值維度，此更新內容可讓您<ul><li>在區段中使用「無值」維度項目。</li><li>在報告中對「無值」條列項目進行劃分。</li></ul> [了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | | 2025 年 3 月 27 日 |
| **Adobe Content Analytics** | Adobe Content Analytics 可讓您快速且輕鬆地調查大量內容資料，以發現趨勢、發現異常、識別內容疲勞，並從內容曝光中獲取見解。<p>開箱即用，您可以使用預先建立的報告範本和新功能 (如資產檢查器) 來節省時間。此功能讓您不僅能將資產與資料一起視覺化，還可以打開每個資產以查看摘要細節，包括效能、展示位置、屬性等。<p>您可以在完整的客戶旅程背景下調查這組新的內容資料，以回答重要的業務問題、評估內容效能、提升細分、識別最佳化機會，並定義新的對象以進行啟動。<p>Content Analytics 是 Customer Journey Analytics 的附加功能。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025 年 3 月 27 日 |
| **媒體集合：全新媒體報告 XDM 的 Adobe 來源連接器更新內容** | Analytics 來源連接器會自動將 Adobe Analytics 中的串流媒體資料對應至 Web SDK 所使用的相同欄位。過去，資料會對應到舊位置和新位置，但將來只會使用新位置。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025 年 3 月 31 日 |
| **XDM 欄位已更新，用於將串流媒體資料收集到 Adobe Experience Platform** | 將串流媒體資料收集到Adobe Experience Platform時，不應再使用串流媒體引數檔案的「XDM欄位路徑」標題下方顯示的XDM欄位路徑。 這些欄位路徑可在下列頁面上找到，並標示為「已棄用」： [音訊和視訊引數](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告引數](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節引數](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態引數](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters)以及[品質引數](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>客戶應改移轉至`mediaReporting`欄位路徑，如上方參考的串流媒體引數檔案的「報告XDM欄位路徑」標題下所示。<p>在三個月的過渡期間，將會繼續擷取已停用XDM欄位路徑上的資料。 但在2025年7月底，已棄用的欄位路徑將完全移除且不再顯示在Adobe Experience Platform結構描述UI中，資料將僅使用`mediaReporting`欄位路徑傳送。<p>在2025年4月22日之前實作Analytics來源聯結器以收集串流媒體資料至Platform的客戶必須移轉其現有設定，以使用新的欄位路徑。 此次移轉須在 2025 年 7 月底前完成。如需移轉支援，請聯絡您的 Adobe 諮詢服務或帳戶團隊。在 2025 年 4 月 22 日之後實作 Analytics 來源連接器的客戶，無需採取任何行動。</p> |  | 2025 年 4 月 22 日 |
| **術語變更：將「篩選器」更改為「區段」** | 先前，Adobe Customer Journey Analytics 將區段稱為「篩選器」。該術語現已與 Adobe Analytics 維持一致。「篩選器」現稱為「區段」。（顯然，搜尋篩選器仍稱為「篩選器」。） UI和檔案已更新。 | | 2025 年 4 月 16 日 |
| **拼接：從 XDM IdentityMap 擷取永久和暫時 ID** | 此功能支援在拼接過程中使用儲存在 XDM IdentityMap 中的身分識別。欄位型拼接可使用 IdentityMap 作為永久或暫時 ID，而識別圖型拼接可使用 identityMap 作為永久 ID。您可以使用 identityMap 中的特定命名空間或主要身分識別。在[此處](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap)和[此處](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap)了解更多資訊 |  | 2025年4月28日 |
| **跨資料視圖共用的量度和維度** | 允許您在多個資料視圖中套用維度和量度設定。對共用維度或量度所做的變更，將應用於所有適用資料視圖中該維度或量度的所有執行個體。透過這個介面，Customer Journey Analytics 管理員在使用許多資料視圖時，可以更輕鬆地管理元件。[了解更多](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025 年 4 月 30 日 |


## Customer Journey Analytics 中的修正

**Admin Console**：AN-370228
**Analysis Workspace**：AN-371933；AN-371933；AN-371979
**客群**：AN-373032
**元件設定**：AN-367400
**衍生欄位**：AN-370614；AN-370959
**匯出位置**：AN-371670
**完整表格匯出**：AN-360492；AN-369204；AN-370755；AN-372294；AN-372363；AN-372754；AN-373040；AN-373081；AN-373168
**歷程畫布**：AN-373294
**行動應用程式**：AN-363169；AN-368496；AN-371766
**產品使用情況**；AN-369501
**報告**：AN-369085；AN-371094；AN-372580


## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | | |

## 相關資源

* [2025 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2025.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
