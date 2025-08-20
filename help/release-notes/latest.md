---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc22f2c83340bacb99fd08095c48585be9e5f1fe
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 81%

---

# 最新的 Adobe Customer Journey Analytics 發行說明 (2025 年 8 月)

**上次更新日期**：2025年8月14日


這些發行說明涵蓋 2025 年 8 月 13 日至 2025 年 9 月 16 日的發行期間。Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **地圖視覺化呈現** | 地圖視覺化呈現是 Analysis Workspace 中的視覺化呈現功能，讓您建置任何量度 (包括計算量度) 的視覺化地圖。此視覺化呈現有助於辨識和比較不同地理區域之間的量度資料。<p>過去，唯有 Adobe Analytics 才提供地圖視覺化呈現功能。</p><p>Customer Journey Analytics 中的地圖視覺化呈現也針對下列 Adobe Analytics 地圖視覺化呈現進行改良：</p><ul><li>使用資料釋圖中的任何區段作為資料來源。</li><li>透過在資料釋圖中設定維度，準確度可達一公尺。</li><li>透過新的選取工具，您可以選取視覺化呈現中任何區域，並從中建立細分、客群、趨勢或劃分。</li></ul><p>如需更多詳細資訊，請參閱[地圖](/help/analysis-workspace/visualizations/map.md)。</p> | 2025 年 8 月 13 日 | 2025 年 8 月 25 日 |
| **B2B 範本** | 如果您擁有 Customer Journey Analytics B2B Edition 授權，則現在可以從 Adobe 範本 UI 使用下列其他 B2B 範本： <ul><li>B2B 帳戶參與度概觀</li><li>B2B 機會參與度概觀</li><li>B2B 購買群組活動</li></ul><p>如需詳細資訊，請參閱[使用範本](/help/analysis-workspace/templates/use-templates.md#b2b-templates)中的[B2B範本](/help/analysis-workspace/templates/use-templates.md)。</p> |  | 2025 年 8 月 15 日 |
| **以 PDF 格式下載的專案會下載至您的工作站** | 若以 PDF 格式下載專案，此 PDF 檔案會下載至工作站中的下載資料夾。 <p>過去，以 PDF 格式下載專案時，會在具有唯一 URL 的新瀏覽器索引標籤中啟動該 PDF。</p><p>如需更多詳細資訊，請參閱[下載專案和資料](/help/analysis-workspace/export/download-send.md)。</p> |  | 2025 年 8 月 25 日 |
| **支援臨時結構描述** | [臨時結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/tutorials/ad-hoc)可用於 Experience Platform 的各種資料攝取工作流程，包括攝取 CSV 檔案和建立特定類型的來源連線。 <p>此功能可支援在 Customer Journey Analytics 中使用臨時結構描述。作為連線定義的一部分，您現在可以根據臨時結構描述選取資料集，並在資料釋圖和 Workspace 專案中使用此資料。</p> <p>(文件連結待補充。)</p> |  | 2025 年 8 月 28 日 |
| **擴展查閱鍵限制** | 根據您的 Customer Journey Analytics 封裝，在查閱資料集中現在最多可擁有 10 億個唯一關鍵值。 <p>如需更多詳細資訊，請參閱 Customer Journey Analytics [護欄](/help/technotes/guardrails.md)文件中的[資料傳輸限制](/help/technotes/guardrails.md#data-transfer-limits)。</p> |  | 2025 年 8 月 29 日 |
| **根據 Platform 結構描述中使用者定義的對應欄位建立量度和維度** | 您在 Experience Platform 結構描述中定義的使用者定義對應欄位，現在可於 Customer Journey Analytics 中使用。<p>在 Customer Journey Analytics 中建立量度和維度時，您可以使用下列對應欄位：</p><ul><li>字串對應字串</li><li>字串對應整數</li></ul><p>(文件連結待補充。)</p><p>如需更多有關 Experience Platform 中對應欄位的詳細資訊，請參閱[在 UI 中定義對應欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/map)。</p> |  | 2025 年 8 月底 |
| **已刪除的專案立即無法再使用 URL 存取，並且會從已排程的傳送中刪除** | 已刪除的專案將立即從已排程的傳送中刪除，並且無法再透過其 URL 存取。<p>過去，專案包含在已排程的傳送中，並且在刪除後 60 天內仍可透過其 URL 進行存取。</p><p>如需更多有關刪除專案的詳細資訊，請參閱[專案概觀](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。</p> | | 2025 年 8 月底 |
| **即時報告** | Customer Journey Analytics 中的即時報告會即時顯示並更新 Analysis Workspace 中一個或多個面板內的資料和視覺化呈現內容。 | | 2025年9月17日（原計畫於2025年8月15日發行） |
| **串流媒體：XDM 欄位已更新，可將串流媒體資料收集至 Adobe Experience Platform** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下顯示的 XDM 欄位路徑。反之，在2025年5月9日之前實作Analytics來源聯結器以收集串流媒體資料至Platform的客戶必須將其現有設定移轉至mediaReporting欄位路徑，如串流媒體引數檔案的「報告XDM欄位路徑」標題下所示。<p> 這些欄位路徑可在下列頁面上找到，並標示為「已棄用」： [音訊和視訊引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)以及[品質引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。 (在 2025 年 5 月 9 日之後實作 Analytics 來源連接器，且僅使用 mediaReporting XDM 路徑的客戶，則無需採取任何行動。) </p><p>已棄用的 XDM 欄位路徑上的資料攝取將持續至 2025 年 10 月底。之後，已棄用的欄位路徑將完全移除，不再顯示於Adobe Experience Platform結構描述UI中，而且只會使用mediaReporting欄位路徑傳送資料。</p><p>如需詳細資訊，請參閱[將Analytics Source Connector實作移轉至更新的XDM串流媒體欄位](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>如需移轉支援，請聯絡您的 Adobe Consulting 服務或帳戶團隊。 </p> |  | 2025 年 10 月 |
| **在連線中進行拼接** | 簡化 Customer Journey Analytics 拼接。現在只需將資料攝取至 Customer Journey Analytics 中即可完成拼接，而不是複製資料集並在重複的資料集上套用拼接，因此不需要使用重複的資料集和結構描述。 <p>此外，您現在可以從更新的 Connections UI 自行啟用拼接，而無需透過客戶支援要求拼接。</p><p> *由於需要額外的努力，會推送先前通訊的發行日期。 新發行日期與假期季節重疊，這會引入其他發行限制。 現在計劃分階段推出，以確保穩定性並將假期期間的干擾降至最低。*</p> | 2025年10月底 | 2026年1月底 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**：AN-389683、AN-389534、AN-389207、AN-389066、AN-388687、AN-388478、AN-387089、AN-384865、AN-384560、AN-383486、AN-365768、AN-351639
**元件**：
**Content Analytics**：
**引導式分析**：AN-384426
**Platform**：AN-384410
**Report Builder**：AN-389336、AN-382775
**報告**：
**細分**：
**共用的量度和維度**：
**其他**：AN-388222、AN-384898、AN-387169


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
