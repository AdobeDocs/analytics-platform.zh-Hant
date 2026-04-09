---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 701279f92877ee186160f901f0d4df74fd42f547
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 35%

---

# 最新Customer Journey Analytics發行說明（2026年4月）

**上次更新日期**： 2026年4月9日

這些發行說明涵蓋2026年4月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能和說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **義大利語支援**<br/>&#x200B;義大利語言環境(it-IT)現在在Customer Journey Analytics的Analysis Workspace中受到支援。 <p>Customer Journey Analytics支援Experience Platform UI支援的所有語言，如[Experience Platform UI的瀏覽器和語言支援](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)中所述。</p><p>您可以在Experience Platform中[變更您的預設語言](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)。</p> | | 2026年4月8日 |
| **Adobe工程代理程式中的資料驗證** <br/>Data Engineering Agent中有新的資料驗證技能。 這些技能可協助團隊在Customer Journey Analytics中分析資料之前，直接在Adobe Experience Platform中快速評估資料品質。 <p>資料驗證技能可啟用隨選、欄位層級和資料集層級驗證，將統計摘要與無效或異常值的智慧型偵測結合在一起。 </p><p>使用資料驗證技能可減少手動QA工作量，並加快跨資料工程工作流程的可信資料上線和轉換。</p><p>(文件連結待補充。)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年4月底 <p>（原計畫於2026年3月31日發行）</p> |
| **適用於Customer Journey Analytics的MCP伺服器** <br/>您現在可以使用MCP （模型內容通訊協定）將Customer Journey Analytics連結到您現有的代理式工作流程。 您可以使用自然語言來請求報表和深入分析。<p>(文件連結待補充。)</p> | | 2026年4月底 |
| **串流媒體服務：支援排程資料** <br/>您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤觀看率。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |
| **多個維度API報告**<br/>&#x200B;在單一API請求中報告多個維度，並執行維度層級的搜尋。 [了解更多](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026 年 3 月 |
| **多欄API排序**<br/>&#x200B;在API要求中排序多個維度和量度物件。 在相同的排序定義中混合維度和量度。 [了解更多](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026 年 3 月 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-442813、AN-442410、AN-442231、AN-441943、AN-441717、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**元件**：
**連線**： AN-442824、AN-440937、AN-440092、AN-429781
**Content Analytics**：
**引導式分析**：
**匯出**：
**資料檢視**： AN-442809、AN-434824、AN-434210、AN-424000
**實作**：
**Report Builder**： AN-441136、AN-438147、AN-425150
**報告**： AN-443900、AN-441811、AN-441506、AN-440919、AN-440545、AN-440505、AN-440300
**分段**：
**排程報告**：
**共用的量度和維度**：
**Other**： AN-423359、AN-406242、AN-397985


## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| **移除TLS 1.2加密套件** | 2026年2月11日 | 管理員須知： Adobe預計於2026年5月27日從Adobe資料收集伺服器上移除下列TLS 1.2加密套裝的支援。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>大部分實施不需要客戶採取任何動作。 這項變更主要影響從使用過時TLS程式庫的舊版原生應用程式傳送的Analytics資料，以及在過時瀏覽器或作業系統上的少數網頁訪客。 移除對這些加密套裝的支援，可增強安全性，並使Adobe符合現代化的加密標準。 目前，不到0.1%的資料收集流量依賴這些加密套件。</p> |

## 相關資源

* [2025 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2025.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
