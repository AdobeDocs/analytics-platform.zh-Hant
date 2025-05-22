---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 13790d3857f1635f8efd5d98347fd02b9cbcc144
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 50%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2025 年 5 月)

**上次更新日期**：2025 年 5 月 14 日


這些發行說明涵蓋2025年4月22日至6月18日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B Edition 透過提供可操作的客戶洞察來推動收入成長，幫助 B2B 公司協調其行銷、銷售和產品團隊。由於客戶是資料模型的中心，因此所有分析都集中在客戶歷程上。在人員和時間型事件上新增實體（帳戶、機會和購買群組）的新層，可建立B2B行銷和收入生命週期的完整面貌。 [了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日 |
| **Data Insights Agent** | Data Insights Agent是Customer Journey Analytics中AI助理的一部分，屬於產生式AI交談代理程式。 它會使用您資料檢視的元件和實際資料，在Analysis Workspace中建立相關的視覺效果，快速並有效率地回答以資料為中心的問題。 [了解更多](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 2025年5月28日 |
| **在Analysis Workspace專案中新增並檢視註解** | Analysis Workspace中的新[註解功能](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)可讓您在Analysis Workspace專案的內容中分享見解和提出問題。 如此可簡化有關資料的討論，讓對話保持在討論的資料內容中。 您可以 <ul><li>針對您有權存取的任何Analysis Workspace專案發表評論</li><li>註解視覺效果中的特定點或發表專案的一般註解</li><li>標籤其他使用者，通知他們您的評論</li><li>管理現有註解（編輯、釘選、解析等）</li></ul>Customer Journey Analytics管理員可以[停用組織層級](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)的註解。 專案所有者可以[停用專案層級](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)的註解。 |  | 2025 年 5 月 29 日 |
| **增加完整資料表匯出限制** | Adobe將您可以搭配[完整表格匯出](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics)使用的欄數從5個維度和5個量度增加到10個維度和10個量度。 這適用於所有Customer Journey Analytics階層。 可匯出的列數權益沒有變更。 |  | 2025 年 4 月 30 日 |
| **XDM 欄位已更新，用於將串流媒體資料收集到 Adobe Experience Platform** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下顯示的 XDM 欄位路徑。這些欄位路徑位於以下頁面，並標記為「不推薦使用」：[音訊和視訊參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)，以及[品質參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>客戶應改移轉至`mediaReporting`欄位路徑，如上方參考的串流媒體引數檔案的「報告XDM欄位路徑」標題下所示。<p>在三個月的過渡期間，將會繼續擷取已停用XDM欄位路徑上的資料。 但在2025年7月底，已棄用的欄位路徑將完全移除且不再顯示在Adobe Experience Platform結構描述UI中，資料將僅使用`mediaReporting`欄位路徑傳送。<p>在2025年4月22日之前實作Analytics來源聯結器以收集串流媒體資料至Platform的客戶必須移轉其現有設定，以使用新的欄位路徑。 此次移轉須在 2025 年 7 月底前完成。如需移轉支援，請聯絡您的 Adobe 諮詢服務或帳戶團隊。在 2025 年 4 月 22 日之後實作 Analytics 來源連接器的客戶，無需採取任何行動。</p> |  | 2025 年 4 月 22 日 |
| **拼接：從 XDM IdentityMap 擷取永久和暫時 ID** | 此功能支援在拼接過程中使用儲存在 XDM IdentityMap 中的身分識別。欄位型拼接可使用 IdentityMap 作為永久或暫時 ID，而識別圖型拼接可使用 identityMap 作為永久 ID。您可以使用 identityMap 中的特定命名空間或主要身分識別。在[此處](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap)和[此處](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap)了解更多資訊 |  | 2025年4月28日 |
| **跨資料視圖共用的量度和維度** | 允許您在多個資料視圖中套用維度和量度設定。對共用維度或量度所做的變更，將應用於所有適用資料視圖中該維度或量度的所有執行個體。透過這個介面，Customer Journey Analytics 管理員在使用許多資料視圖時，可以更輕鬆地管理元件。[了解更多](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025 年 4 月 30 日 |
| **事件深度維度** | 新的[事件深度維度](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components)已新增至資料檢視的必要標準元件清單。 |  | 2025年5月8日 |
| **當游標停留時，Analysis Workspace 的左側面板不再開啟和關閉** | 您可以使用 Analysis Workspace 中的左側面板，將元件、面板和視覺效果等內容新增至專案。將游標停留在最左側的其中一個圖示來暫時開啟左側面板的選項不再適用。現在改為按一下其中一個圖示可保持面板開啟，再按一下相同的圖示可將面板關閉。 |  | 2025 年 5 月 29 日 |
| **匯出完整資料表時停用資訊清單檔案** | 可讓您停用從Analysis Workspace匯出完整表格時預設包含的資訊清單檔案。 [了解更多](/help/analysis-workspace/export/export-cloud.md) |  | 2025年5月20日 |


## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-361874； AN-371360； AN-373079； AN-374382； AN-374447； AN-375277； AN-375680
**對象**： AN-372343
**稽核記錄**： AN-378168
**連線**： AN-373121； AN-372996
**資料刪除**： AN-375450
**衍生欄位**： AN-373689； AN-377852
**匯出位置**： AN-374167
**歷程畫布**： AN-373319
**Report Builder**： AN-369786
**報告**： AN-377326； AN-378051
**報告活動管理員**： AN-377148


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
