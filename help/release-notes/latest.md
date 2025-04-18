---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 44%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2025 年 4 月)

**上次更新日期**：2025年4月16日

這些發行說明涵蓋2025年3月27日至5月15日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新了數值維度中的「無值」條列項目** | 對於數值維度，此更新內容可讓您<ul><li>在區段中使用「沒有值」維度專案。</li><li>在報告中對「無值」條列項目進行劃分。</li></ul> [了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 2025 年 3 月 27 日 |
| **Adobe Content Analytics** | Adobe Content Analytics 可讓您快速且輕鬆地調查大量內容資料，以發現趨勢、發現異常、識別內容疲勞，並從內容曝光中獲取見解。<p>開箱即用，您可以使用預先建立的報告範本和新功能 (如資產檢查器) 來節省時間。此功能讓您不僅能將資產與資料一起視覺化，還可以打開每個資產以查看摘要細節，包括效能、展示位置、屬性等。<p>您可以在完整的客戶旅程背景下調查這組新的內容資料，以回答重要的業務問題、評估內容效能、提升細分、識別最佳化機會，並定義新的對象以進行啟動。<p>Content Analytics 是 Customer Journey Analytics 的附加功能。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025 年 3 月 27 日 |
| **媒體集合：全新媒體報告 XDM 的 Adobe 來源連接器更新內容** | Analytics 來源連接器會自動將 Adobe Analytics 中的串流媒體資料對應至 Web SDK 所使用的相同欄位。過去，資料會對應到舊位置和新位置，但將來只會使用新位置。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025 年 3 月 31 日 |
| **已更新將串流媒體資料收集到Adobe Experience Platform的XDM欄位** | 新的XDM欄位群組`mediaReporting`可用於將串流媒體資料收集到Adobe Experience Platform中。 新的`mediaReporting`欄位群組會取代先前使用的`media.mediaTimed`欄位群組。<p>在三個月的過渡期間，`media.mediaTimed`欄位上的資料擷取將會繼續。 但在2025年7月底，`the media.mediaTimed`欄位將完全棄用，且不再顯示在Adobe Experience Platform結構描述UI中，資料將僅使用`mediaReporting`欄位傳送。<p>在2025年4月22日之前實作Analytics來源聯結器以收集串流媒體資料至Platform的客戶，必須移轉其現有設定，以使用新欄位群組傳送資料。 此移轉必須在2025年7月底前完成。 如需移轉支援，請聯絡您的Adobe Consulting服務或帳戶團隊。 在2025年4月22日之後實施Analytics來源聯結器的客戶無需採取任何動作。 |  | 2025年4月22日 |
| **術語變更：「篩選器」變更為「區段」** | 之前，Adobe Customer Journey Analytics將區段稱為「篩選器」。 此術語現在已與Adobe Analytics一致。 「篩選器」現在稱為「區段」。 （顯然，搜尋篩選器仍稱為「篩選器」。） UI已更新，檔案正在更新中。 |  | 2025年4月16日 |
| **拼接：從XDM IdentityMap**&#x200B;擷取持續性和暫時性ID | 此功能支援在銜接程式中使用儲存在XDM identityMap中的身分識別。 identityMap可用於欄位式拚接的永久性或暫時性ID，也可用於圖表式拚接的永久性ID。  您可以使用特定名稱空間或來自identityMap的主要身分。 (文件連結待補充) |  | 2025年4月25日 |
| **在資料檢視間共用量度和維度** | 可讓您在多個資料檢視中套用維度和量度設定。 對共用維度或量度所做的變更，會套用至該維度或量度在所有適用資料檢視中的所有例項。 此介面可讓Customer Journey Analytics管理員在使用許多資料檢視時更輕鬆地管理元件。 (文件連結待補充) |  | 2025年4月30日 |


## Customer Journey Analytics 中的修正

**Admin Console**： AN-370228
**Analysis Workspace**： AN-371933； AN- 371933； AN-371979
**對象**： AN-373032
**元件設定**： AN-367400
**衍生欄位**： AN-370614； AN-370959
**匯出位置**： AN-371670
**完整資料表匯出**： AN-360492； AN-369204； AN-370755；AN-372294； AN-372363； AN-372754； AN-373040； AN-373081； AN-373168
**歷程畫布**： AN-373294
**行動應用程式**： AN-363169； AN-368496； AN-371766
**產品使用量**： AN-369501
**報告**： AN-369085； AN-371094； AN-372580


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
