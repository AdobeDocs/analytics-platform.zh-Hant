---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e98a1abbab4b954df5f7759879203c1d355fd50
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 40%

---

# 最新Customer Journey Analytics發行說明（2026年2月）

**上次更新日期**：2026年2月11日

這些發行說明涵蓋2026年2月發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能和說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ------- | ---- |
| **標題覆寫** <p>您可以在Content Analytics中指定標頭名稱和密碼標頭值。 此[標頭覆寫設定](/help/content-analytics/config/guided.md#header-overrides)可確保Content Analytics傳送自訂HTTP標頭，以略過您已實作的機器人偵測或閘道流量技術。</p> |  | 2026年2月2 |
| **在自由格式表格中包含多個維度欄**<p>您現在可以在自由格式表格中包含最多 5 個維度欄，以便您並排檢視多個維度項目。每一列維度項目的行為都像是單一串連的維度項目。</p><p>您可以將篩選器、排序、劃分等項目套用至具有多個維度欄的自由格式表格，以建立更深入、更自訂的分析。</p><p>過去，您只能在自由格式表格中包含 1 個維度欄。</p><p>如需詳細資訊，請參閱[在自由格式表格中包含多個維度欄](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **依多個欄排序表格**<p>您現在可以在 Analysis Workspace 中依多個欄來排序自由格式表格的資料，無論其為維度或量度皆可。</p><p>當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序進行排序。優先順序編號會顯示在排序圖示旁邊。</p><p>如需詳細資訊，請參閱[篩選和排序自由表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **完整資料表匯出改善**<p>完整的表格匯出包含下列增強功能：</p><p>匯出建立和設定增強功能</p><ul><li>從「匯出」頁面建立匯出。 之前，您只能在表格上按一下右鍵，以從Analysis Workspace建立匯出。</li><li>建立匯出時新增帳戶或位置。</li><li>自動建立檔案名稱及放置匯出檔案的資料夾。 如此一來，檔案名稱便能以可預測的形式，並以邏輯的方式整理到資料夾中。 以前，檔案名稱無法預測且會分組到單一資料夾中。</li><li>支援將資料匯出為Parquet檔案，以改善Data Warehouse相容性。 之前，僅支援CSV和JSON。</li></ul><p>匯出管理增強功能</p><ul><li>從「匯出」頁面更新或取消一或多個匯出。</li><li>從「記錄」頁面重新傳送一或多個匯出。</li><li>當匯出失敗或即將到期時，以電子郵件傳送個別使用者或群組。</li><li>匯出失敗更精確的錯誤訊息。</li></ul><p>計算量度、區段和維度增強功能</p><ul><li>支援更多計算量度函式。 之前，僅支援簡單的數學函式。</li><li>建立匯出時套用區段。</li><li>支援雙資料型別維度，以提高精確度。</li></ul><p>管理增強功能</p><ul><li>管理員現在可以檢視所有匯出和記錄，無論其建立者為何。</li></ul><p>(文件連結待補充。)</p> | 2026 年 2 月 18 日 | 2026年3月4日 |
| **Content Analytics：散佈圖視覺效果縮圖和預覽** <p>在Content Analytics中檢視散佈圖視覺效果時，現在當您將滑鼠游標停留在圖表中的點上時，會顯示資產的縮圖。 此縮圖可讓您快速輕鬆地檢視圖表中表示的內容。</p><p>(文件連結待補充。)</p> | 2026年2月17日 | 2026年3月2日 |
| **Content Analytics：長條圖視覺效果縮圖和預覽** <p>在Content Analytics中檢視橫條圖視覺效果時，現在當您將滑鼠游標停留在圖表中的橫條圖上時，會顯示資產的縮圖。 此縮圖可讓您快速輕鬆地檢視圖表中表示的內容。</p><p>(文件連結待補充。)</p> | 2026年2月23日 | 2026年3月9日 |
| **更新至近似計數相異函式**<p>Approximate Count Distinct函式中使用的HLL機率演演算法即將更新。 使用此函式的數字之結果輸出可能會和歷史數字稍有不同，如下所示：<ul><li>計算極少量不重複值時，結果將改善為使用精確計數，而不是使用預估值。</li><li>計算任何較大的數字時，計數估計將保持本次更新之前的準確性（估計準確性在準確數字的5%以內，即時間的95%）。</li></ul><p>如需Approximate Count Distinct函式的詳細資訊，請參閱[進階函式](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | 2026 年 3 月 |
| **支援 Data Mirror**  <p>藉由支援 Experience Platform 中特定來源連接器的模型式結構描述和變更資料擷取 (CDC) 功能，Customer Journey Analytics 將能夠支援如 [!DNL Snowflake]、[!DNL Azure Databricks] 和 [!DNL Google BigQuery] 等資料倉儲解決方案的[資料鏡像](/help/data-mirror/data-mirror.md)功能。</p><p>若要存取 Beta 版，請聯絡您的 Adobe 帳戶團隊。</p> | Beta 版：2025 年 9 月 24 日 | 待定 |
| **串流媒體服務：支援排程資料** <p>您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤觀看率。</p><p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-421930、AN-424997、AN-424194、AN-425515、AN-425254、AN-423174、AN-428834、AN-306540、AN-426014、AN-427801
**元件**：
**Content Analytics**：
**引導式分析**：
**匯出**： AN-422041、AN-421599、AN-422112
**資料檢視**：
**實作**：
**Report Builder**： AN-391415、AN-425125
**報告**： AN-425817、AN-424362、AN-425752、AN-425278、AN-422249、AN-403446、AN-424727、AN-426791、AN-427985
**分段**： AN-428905、AN-428232
**排程報告**： AN-425484、AN-425137
**共用的量度和維度**：
**Other**： AN-428833、AN-425074


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
