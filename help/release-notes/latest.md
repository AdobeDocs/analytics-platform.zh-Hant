---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5621dbf7328fd64979c440a107ced634164736
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 68%

---

# 最新Customer Journey Analytics發行說明（2025年10月）

**上次更新日期**：2025年10月14日

這些發行說明涵蓋2025年10月至11月初的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **包含線上圖視覺效果和走勢圖中的篩選條件** | 您套用至自由表格篩選器的任何搜尋篩選條件，現在一律會包含在走勢圖中。 此外，您也可以將搜尋篩選條件納入任何連線的線條視覺效果中。<p>您可以選取所連線表格之量度欄標題中的走勢圖，將線條視覺效果設定為包含搜尋篩選條件。</p><p>以往，搜尋篩選條件不會包含在走勢圖或連線的線段視覺效果中。</p><p>(文件連結待補充。) | | 2025 年 10 月 15 日 |
| **從Workspace報表產生投影片簡報** | 您現在可以根據Analysis Workspace報告自動產生投影片簡報（採用.pptx格式）。 Workspace會偵測報表中的關鍵深入分析，並將其轉換為利害關係人就緒的投影片。<p>此功能可減少呈現發現、建立主管敘事及溝通業務影響所需的時間和精力。</p><p>(文件連結待補充。)</p> | 2025年10月22日 | 2026 年 1 月 |
| **即時報告** | Customer Journey Analytics 中的即時報告會即時顯示並更新 Analysis Workspace 中一個或多個面板內的資料和視覺化呈現內容。<br/><br/>(文件連結待補充。) | 2025 年 9 月 18 日 (原規劃於 2025 年 8 月 15 日發行) | 2025年10月27日 |
| **支援 Data Mirror** | 透過Experience Platform中特定來源聯結器的模型型結構描述和變更資料擷取(CDC)功能支援，Customer Journey Analytics將能支援[!DNL Snowflake]、[!DNL Azure Databricks]和[!DNL Google BigQuery]等資料倉儲解決方案的資料映象功能。<p>若要存取 Beta 版，請聯絡您的 Adobe 帳戶團隊。</p><p>(文件連結待補充。)</p> | Beta發行日期： 2025年9月24日 | 待定 |
| **在連線中進行拼接** | 簡化 Customer Journey Analytics 拼接。現在只需將資料攝取至 Customer Journey Analytics 中即可完成拼接，而不是複製資料集並在重複的資料集上套用拼接，因此不需要使用重複的資料集和結構描述。 <p>此外，您現在可以從更新的 Connections UI 自行啟用拼接，而無需透過客戶支援要求拼接。</p><p> *由於需要投入更多精力，先前公告的發行日期已延遲。新的發行日期與假期重疊，導致額外的發行限制。目前規劃分階段推出，以確保穩定性，並盡量減少假期期間的干擾。*</p> <p>(文件連結待補充。)</p> | 2025年10月28日 | 2026年4月30日 |
| **串流媒體服務：支援排程資料** | 您現在可以上傳過往串流媒體直播內容的排程資料，以便更輕鬆且更準確地追蹤觀看人數。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>(文件連結待補充。)<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025 年 10 月 29 日 |
| **Analytics來源聯結器： Experience Platform中的搜尋報告套裝** | 報告套裝數量很大的客戶現在可以在Analytics Source Connector資料流工作流程中，搜尋他們想要連線的報告套裝。 <p>以前，客戶必須逐頁顯示可能很長的報表套裝清單。</p><p>(文件連結待補充。) | | 2025年10月30日 |
| **串流媒體：XDM 欄位已更新，可將串流媒體資料收集至 Adobe Experience Platform** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下顯示的 XDM 欄位路徑。在 2025 年 5 月 9 日前實作 Analytics 來源連接器，將串流媒體資料收集至 Platform 的客戶，必須將其現有設定移轉至 mediaReporting 欄位路徑 (如串流媒體參數文件的「報告 XDM 欄位路徑」標題之下的內容所示)。<p> 這些欄位路徑位於以下頁面，並標記為「已棄用」：[音訊和視訊參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)，以及[品質參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。(在 2025 年 5 月 9 日之後實作 Analytics 來源連接器，且僅使用 mediaReporting XDM 路徑的客戶，則無需採取任何行動。) </p><p>已棄用的 XDM 欄位路徑上的資料攝取將持續至 2025 年 10 月底。之後會完全移除已棄用的欄位路徑，不再顯示於 Adobe Experience Platform Schema UI 中，並且僅使用 mediaReporting 欄位路徑傳送資料。</p><p>如需更多詳細資訊，請參閱[移轉 Analytics 來源連接器實作至已更新的 XDM 串流媒體欄位](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>如需移轉支援，請聯絡您的 Adobe Consulting 服務或帳戶團隊。 </p> |  | 2025 年 10 月 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-400507、AN-400265、AN-399209、AN-397146、AN-394992、AN-390795
**元件**：
**Content Analytics**：
**匯出**： AN-399012、AN-388578
**引導式分析**：
**實作**： AN-397551、AN-397550、AN-397190、AN-396127
**Report Builder**： AN-401127、AN-400618、AN-392971、AN-391692
**報告**：
**分段**：
**排程報告**：
**共用的量度和維度**：
**其他**：


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
