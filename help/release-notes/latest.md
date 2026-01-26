---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fa6178831923d1bb256fa03fa2945a61541d65f7
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 47%

---

# 目前的Customer Journey Analytics發行說明（2026年1月）

**上次更新日期**：2026年1月14日

以下發行說明涵蓋2026年1月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在Customer Journey Analytics中從Experience Platform設定檔資料集分析對象** | 您現在可以將Experience Platform設定檔資料集中的對象會籍資料擷取到Customer Journey Analytics連線。 對象會成為新的維度，以便在Analysis Workspace中使用。<p>透過Customer Journey Analytics中的新功能可擷取XDM物件對應，以便擷取設定檔AudienceID。</p><p>之前，只有簡單的XDM對應可以擷取到Customer Journey Analytics。</p><p>除了可以在Analysis Workspace中將受眾資料新增為維度至任何專案外，以下新的Workspace範本也可供使用：</p><ul><li>Audience Analytics概觀</li><li>同意原則概觀</li></ul><p><!-- For more information, see [Audience analysis overview](https://experienceleague.corp.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html). -->(文件連結待補充。)</p> | 2025 年 10 月 22 日 | 2026 年 1 月底 <p> （原計畫於2026年1月22日推出）</p> |
| **述說資料的故事：從 Workspace 報告產生投影片簡報** | 您現在可以根據 Analysis Workspace 報告自動產生投影片簡報 (採用 .pptx 格式)。Workspace 會偵測報告中的關鍵洞察，並將其轉換為適合利害關係人使用的投影片。<p>此功能可減少呈現分析結果、建立利於管理層理解的報告敘事及傳達分析對業務之影響所需的時間和精力。</p><p>如需詳細資訊，請參閱[述說資料的故事：從 Workspace 報告產生投影片簡報](/help/analysis-workspace/curate-share/generate-slides.md)。</p> | 2025 年 10 月 22 日 | 2026年1月28日 |
| **在自由格式表格中包含多個維度資料行** | 您現在可以在自由表格中包含最多5個維度欄，讓您並排檢視多個維度專案。 每一列維度專案的行為類似於單一串連維度專案。<p>您可以將篩選器、排序、劃分等套用至具有多個維度欄的自由格式表格，以建立更深入、更自訂的分析。</p><p>過去，自由表格中只能包含1個維度欄。</p><p><!-- For more information, see [Include multiple dimension columns in a freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).--> (文件連結待補充。)</p> | 2026年1月28日 | 2026年2月18日 |
| **依多個資料行排序資料表** | 您現在可以在Analysis Workspace中依多個欄排序自由表格的資料，無論其為維度或量度皆然。<p>當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序排序。 優先順序編號會顯示在排序圖示旁。</p><p>(文件連結待補充。)<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | 2026年1月28日 | 2026年2月18日 |
| **合併來自多個IMS組織的資料來源** | 您現在可以使用Analytics Source Connector來合併來自多個IMS組織的多個資料來源。 這可讓組織擁有其客戶資料的合併檢視，即使該客戶資料散佈在多個IMS組織中亦然。 <p>**注意：**&#x200B;此設定只能透過向Adobe客戶服務提交請求來使用。</p>  <p>(文件連結待補充。)</p> |  | 2026 年 1 月 30 日 |
| **在連線中進行拼接** | Customer Journey Analytics中的拚接程式現在更簡單。 現在只需將資料攝取至 Customer Journey Analytics 中即可完成拼接，而不是複製資料集並在重複的資料集上套用拼接，因此不需要使用重複的資料集和結構描述。 <p>此外，您現在可以[透過更新的連線介面](/help/stitching/use-stitching-ui.md)自行開始彙整，而不必透過Adobe客戶服務請求彙整。</p><p> *先前公告的發行日期已延遲，因為需要額外的努力和節日季節。 目前規劃分階段推出，以確保穩定性，並盡量減少假期期間的干擾。*</p> | 2025 年 10 月 28 日 | 2026 年 1 月 30 日 |
| **支援 Data Mirror** | 藉由支援 Experience Platform 中特定來源連接器的模型式結構描述和變更資料擷取 (CDC) 功能，Customer Journey Analytics 將能夠支援如 [!DNL Snowflake]、[!DNL Azure Databricks] 和 [!DNL Google BigQuery] 等資料倉儲解決方案的[資料鏡像](/help/data-mirror/data-mirror.md)功能。<p>若要存取 Beta 版，請聯絡您的 Adobe 帳戶團隊。</p> | Beta 版：2025 年 9 月 24 日 | 待定 |
| **串流媒體服務：支援排程資料** | 您現在可以上傳過往串流媒體直播內容的排程資料，以便更輕鬆且更準確地追蹤觀看人數。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-423389、AN-423316、AN-422636、AN-422482、AN-422121、AN-422116、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352、AN-404048 an-403241、AN-402523、AN-400795、AN-396149、AN-390990、AN-390646、AN-383484、AN-376980 371729 347570 404835
**元件**：
**Content Analytics**：
**引導式分析**： AN-421274
**匯出**：
**資料檢視**： AN-421891、AN-404627
**實作**：
**Report Builder**： AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**報告**：
**分段**：
**排程報告**： AN-423087、AN-422686
**共用的量度和維度**：
**Other**： AN-422946、AN-422775、AN-422273、AN-422100、AN-420045、AN-404891、AN-390912


## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 |  |  |

## 相關資源

* [2025 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2025.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
