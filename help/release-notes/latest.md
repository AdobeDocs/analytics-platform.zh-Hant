---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0d0494587c9472e23e6fa948043a1ad2057818df
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 20%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2025 年 8 月)

**上次更新日期**：2025年8月13日


這些發行說明涵蓋2025年8月13日至9月16日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **地圖視覺效果** | 地圖視覺效果是Analysis Workspace中的視覺效果，可讓您建立任何量度（包括計算量度）的視覺化地圖。 它適合用於識別及比較不同地理區域的量度資料。<p>以前，地圖視覺效果只能在Adobe Analytics中使用。</p><p>Customer Journey Analytics中的地圖視覺效果包含下列Adobe Analytics中地圖視覺效果的改善：</p><ul><li>使用資料檢視中的任何區段作為資料來源。</li><li>可在資料檢視中設定維度，以精確到單一公尺。</li><li>全新的選取工具可讓您從視覺效果中選取的任何區域建立區段、受眾、趨勢或劃分。</li></ul><p>如需詳細資訊，請參閱[地圖](/help/analysis-workspace/visualizations/map.md)。</p> | 2025年8月13日 | 2025 年 8 月 25 日 |
| **即時報告** | Customer Journey Analytics中的即時報表可即時顯示和更新Analysis Workspace中一個或多個面板內的資料和視覺效果。 | | 2025年8月15日 |
| **B2B範本** | 如果您授權Customer Journey Analytics B2B edition，下列其他B2B範本現在可從Adobe範本UI取得： <ul><li>B2B 帳戶參與概觀</li><li>B2B 機會參與概觀</li><li>B2B 購買群組活動</li></ul><p>(後續文件連結。)</p> |  | 2025年8月15日 |
| **以 PDF 格式下載的專案會下載至您的工作站** | 將專案下載為PDF時，PDF會下載至您工作站的下載資料夾。 <p>之前，將專案下載為PDF會在新的瀏覽器標籤中啟動PDF，並具有唯一的URL。</p><p>如需詳細資訊，請參閱[下載專案和資料](/help/analysis-workspace/export/download-send.md)。</p> |  | 2025 年 8 月 25 日 |
| **支援臨時結構描述** | [臨機結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/tutorials/ad-hoc)用於Experience Platform的各種資料擷取工作流程，包括擷取CSV檔案和建立特定型別的來源連線。 <p>此功能可支援在Customer Journey Analytics中使用臨時結構描述。 作為連線定義的一部分，您現在可以根據臨機操作結構描述選取資料集，並在資料檢視和工作區專案中使用資料。</p> <p>(後續文件連結。)</p> |  | 2025年8月28日 |
| **在連線中拼接** | 簡化Customer Journey Analytics銜接。 現在彙整是在將資料擷取到Customer Journey Analytics時完成，而不是複製資料集並在複製的資料集上套用拼接，這樣做就不需要重複的資料集和結構描述。 <p>此外，您現在可以從更新的連線UI開始自我彙整，而不必請求通過客戶支援進行彙整。</p><p>(後續文件連結。)</p> |  | 2025年8月29日 |
| **延伸查閱金鑰限制** | 根據您的Customer Journey Analytics套件，查詢資料集中現在最多可以有10億個唯一索引鍵。 <p>如需詳細資訊，請參閱Customer Journey Analytics [護欄](/help/technotes/guardrails.md#data-transfer-limits)檔案中的[資料傳輸限制](/help/technotes/guardrails.md)。</p> |  | 2025年8月29日 |
| **根據Platform結構描述中的使用者定義對應欄位，建立量度和維度** | 您在Experience Platform結構描述中定義的使用者定義對應欄位，現在可以在Customer Journey Analytics中使用。<p>在Customer Journey Analytics中建立量度和維度時，您可以使用下列對應欄位：</p><ul><li>字串至字串</li><li>字串至整數</li></ul><p>(後續文件連結。)</p><p>如需Experience Platform中對應欄位的詳細資訊，請參閱[在UI中定義對應欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/map)。</p> |  | 2025年8月底 |
| **刪除的專案無法透過URL立即使用，且會從排程傳遞中刪除** | 刪除的專案會立即從排程傳遞中刪除，且無法再透過其URL存取。<p>以往，專案會包含在已排程的傳送中，且在刪除後的60天內，都可使用其URL進行存取。</p><p>如需有關刪除專案的詳細資訊，請參閱[專案概述](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。</p> | | 2025年8月底 |
| **串流媒體：更新將串流媒體資料收集到Adobe Experience Platform的XDM欄位** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下顯示的 XDM 欄位路徑。反之，在2025年5月9日之前實作Analytics來源聯結器以收集串流媒體資料至Platform的客戶必須將其現有設定移轉至mediaReporting欄位路徑，如串流媒體引數檔案的「報告XDM欄位路徑」標題下所示。<p> 這些欄位路徑可在下列頁面上找到，並標示為「已棄用」： [音訊和視訊引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)以及[品質引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。 （在2025年5月9日之後實施Analytics來源聯結器，而且已經只使用mediaReporting XDM路徑的客戶不需要採取任何動作。）</p><p>淘汰XDM欄位路徑上的資料內嵌將持續到2025年10月底。 之後，已棄用的欄位路徑將完全移除，不再顯示於Adobe Experience Platform結構描述UI中，而且只會使用mediaReporting欄位路徑傳送資料。</p><p>如需詳細資訊，請參閱[將Analytics Source Connector實作移轉至更新的XDM串流媒體欄位](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>如需移轉支援，請聯絡您的Adobe Consulting服務或帳戶團隊。 </p> |  | 2025 年 10 月 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-389683、AN-389534、AN-389207、AN-389066、AN-388687、AN-388478、AN-387089、AN-384865、AN-384560、AN-383486、AN-365768、AN-351639
**元件**：
**Content Analytics**：
**引導式分析**： AN-384426
**平台**： AN-384410
**Report Builder**： AN-389336； AN-382775
**報告**：
**分段**：
**共用的量度和維度**：
**Other**： AN-388222； AN-384898； AN-387169


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
