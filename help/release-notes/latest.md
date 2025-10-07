---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0a45bf12ec63f0820923aa6c947edc93bff12afd
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 93%

---

# 目前的 Customer Journey Analytics 發行說明 (2025 年 9 月)

**上次更新日期**：2025 年 9 月 23 日


這些發行說明涵蓋 2025 年 9 月至 10 月初的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用情況介面的更新** | [使用情況介面](/help/connections/manage-connections.md#usage)現在加入關於核心資料量和平均列大小的資訊。<p>如需詳細資訊，請參閱[管理連線](/help/connections/manage-connections.md#usage)。</p> | | 2025 年 9 月 4 日 |
| **將專案和元件移轉到 Customer Journey Analytics 時改良功能** | 現在起，將專案和元件從 Adobe Analytics 移轉到 Customer Journey Analytics 時，已可使用以下改良功能：<ul><li>一次移轉多個專案。<br/>您一次最多可以移轉 20 個專案。<br/>以前，您一次只能移轉一個專案。</li><li>更新已透過先前專案移轉完成對應的維度和量度對應。<br/>現在起，即使已透過先前移轉對應了相同的維度和量度，您還是可以在每次移轉專案時更新這些對應。<br/>之前，您選擇的任何對應對所有未來專案移轉而言都是永久的。</li><li>為擁有大量專案的組織提升效能。</li></ul><p>此功能可從 Adobe Analytics 介面取得。如需詳細資訊，請參閱[將元件和專案從 Adobe Analytics 移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/component-migration/component-migration)。</p> | 2025 年 9 月 15 日 | 2025 年 9 月 18 日 |
| **查閱鍵限制增加至 10 億** | 現在起，視您的 Customer Journey Analytics 授權而定，查詢資料集的唯一關鍵值數量上限可高達 10 億。 <p>之前，所有權限的數量上限都是 1000 萬。<p>如需詳細資料，請參閱[護欄](/help/technotes/guardrails.md)。</p> | | 2025 年 9 月 25 日 |
| **支援 Ad hoc 和模型式結構描述** | [Ad hoc](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/tutorials/ad-hoc) 和模型式結構描述是在 Experience Platform 的資料攝取和 Data Mirror 工作流程中使用。 |  | 2025 年 9 月 23 日 (原規劃於 2025 年 8 月 28 日發行) |
| **即時報告** | Customer Journey Analytics 中的即時報告會即時顯示並更新 Analysis Workspace 中一個或多個面板內的資料和視覺化呈現內容。<br/><br/>(文件連結待補充。) | 2025 年 9 月 18 日 (原規劃於 2025 年 8 月 15 日發行) | 2025年10月8日 |
| **支援 Data Mirror** | 藉由支援 Experience Platform 中特定來源連接器的模型式結構描述和變更資料擷取 (CDC) 功能，Customer Journey Analytics 將能夠支援如 [!DNL Snowflake]、[!DNL Azure Databrick] 和 [!DNL Google BigQuery] 等資料倉儲解決方案的 Data Mirror 功能。<p>若要存取 Beta 版，請聯絡您的 Adobe 帳戶團隊。</p><p>(文件連結待補充。)</p> | Beta 版，始於 2025 年 9 月 24 日 | 待定 |
| **串流媒體服務：支援排程資料** | 您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤收視率。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或計畫區段的收視率資料。</p><p>無論您以何種方式實施串流媒體收集，都可以使用這些功能。</p><p>先前，在分析即時內容時，很難準確地將特定工作階段連結到特定計畫，也無法將特定工作階段連結到個別主題或計畫區段。</p><p>(後續文件連結。)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025年10月29日 |
| **串流媒體：XDM 欄位已更新，可將串流媒體資料收集至 Adobe Experience Platform** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下顯示的 XDM 欄位路徑。在 2025 年 5 月 9 日前實作 Analytics 來源連接器，將串流媒體資料收集至 Platform 的客戶，必須將其現有設定移轉至 mediaReporting 欄位路徑 (如串流媒體參數文件的「報告 XDM 欄位路徑」標題之下的內容所示)。<p> 這些欄位路徑位於以下頁面，並標記為「已棄用」：[音訊和視訊參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)，以及[品質參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。(在 2025 年 5 月 9 日之後實作 Analytics 來源連接器，且僅使用 mediaReporting XDM 路徑的客戶，則無需採取任何行動。) </p><p>已棄用的 XDM 欄位路徑上的資料攝取將持續至 2025 年 10 月底。之後會完全移除已棄用的欄位路徑，不再顯示於 Adobe Experience Platform Schema UI 中，並且僅使用 mediaReporting 欄位路徑傳送資料。</p><p>如需更多詳細資訊，請參閱[移轉 Analytics 來源連接器實作至已更新的 XDM 串流媒體欄位](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>如需移轉支援，請聯絡您的 Adobe Consulting 服務或帳戶團隊。 </p> |  | 2025 年 10 月 |
| **在連線中進行拼接** | 簡化 Customer Journey Analytics 拼接。現在只需將資料攝取至 Customer Journey Analytics 中即可完成拼接，而不是複製資料集並在重複的資料集上套用拼接，因此不需要使用重複的資料集和結構描述。 <p>此外，您現在可以從更新的 Connections UI 自行啟用拼接，而無需透過客戶支援要求拼接。</p><p> *由於需要投入更多精力，先前公告的發行日期已延遲。新的發行日期與假期重疊，導致額外的發行限制。目前規劃分階段推出，以確保穩定性，並盡量減少假期期間的干擾。*</p> <p>(文件連結待補充。)</p> | 2025 年 10 月底 | 2026 年 1 月底 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**：AN-391719、AN-380838、AN-389402、AN-389373、AN-390851、AN-391593、AN-391404、AN-393064、AN-379337
**元件**：AN-393810
**Content Analytics**：
**引導式分析**：
**平台**：
**Report Builder**：AN-387741、AN-386777、AN-388720、AN-389343
**報告**：AN-391439、AN-391228、AN-393620、AN-393640、AN-391334、AN-393304
**細分**：
**排程報告**：AN-391150、AN-390474
**共用的量度和維度**：
**其他**：AN-387858


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
