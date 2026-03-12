---
title: 最新的 Customer Journey Analytics 發行說明
description: 檢視最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1cfb49bd02da6f35d124cdec8f2df71f451d0fe7
workflow-type: tm+mt
source-wordcount: '1616'
ht-degree: 23%

---

# 最新Customer Journey Analytics發行說明（2026年3月）

**上次更新日期**：2026年3月11日

以下發行說明涵蓋2026年3月發行期。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能和說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **標頭覆寫** <br/>您可以在Content Analytics中指定標頭名稱和密碼標頭值。 此[標頭覆寫設定](/help/content-analytics/config/guided.md#header-overrides)可確保Content Analytics傳送自訂HTTP標頭，以略過您已實作的機器人偵測或閘道流量技術。 |  | 2026年2月2 |
| **合併來自多個IMS組織的報告套裝**<br/>&#x200B;您可以使用Analytics Source Connector來合併來自多個IMS組織的報告套裝。 此[跨IMS資料對應](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md)功能可讓組織擁有其客戶資料的合併檢視，即使該客戶資料散佈在多個IMS組織中亦然。 <p>**注意：**&#x200B;此設定只能透過向 Adobe 客戶服務提交請求來取得。</p> |  | 2026年2月12日 |
| **在自由表格中包含多個維度欄**<br/>&#x200B;您現在可以在自由表格中最多包含5個維度欄，讓您並排檢視多個維度專案。 每一列維度項目的行為都像是單一串連的維度項目。<p>您可以將篩選器、排序、劃分等項目套用至具有多個維度欄的自由格式表格，以建立更深入、更自訂的分析。</p><p>過去，您只能在自由格式表格中包含 1 個維度欄。</p><p>如需詳細資訊，請參閱[在自由格式表格中包含多個維度欄](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)。</p> | 2026 年 1 月 28 日 | 2026年3月4日 <p>（原計畫於2026年2月18日推出）</p> |
| **依多欄排序表格**<br/>&#x200B;您現在可以在Analysis Workspace中依多欄排序自由表格的資料，不論是維度或量度皆然。<p>當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序進行排序。優先順序編號會顯示在排序圖示旁邊。</p><p>如需詳細資訊，請參閱[篩選和排序自由表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026年3月4日 <p>（原計畫於2026年2月18日推出）</p> |
| **Content Analytics：散佈視覺效果縮圖和預覽** <br/>[縮圖和預覽](/help/content-analytics/report/report.md)可用於Content Analytics散佈視覺效果中的資產和體驗。 | 2026年2月17日 | 2026年3月2日 |
| **Content Analytics：長條圖視覺效果縮圖和預覽** <br/>[縮圖和預覽](/help/content-analytics/report/report.md)適用於Content Analytics的長條圖（棧疊）和水準長條圖（棧疊）視覺效果的資產和體驗。 | 2026年2月23日 | 2026年3月9日 |
| **資料集在連線中預覽重新設計**<br/>&#x200B;當您在以人物為基礎的連線中[新增](/help/connections/create-connection.md#add-datasets)或[編輯](/help/connections/create-connection.md#edit-a-dataset)資料集時，預覽資料的體驗會有所改善。 對於拼接啟用的資料集，可以使用有關錯誤ID[的其他](/help/stitching/use-stitching-ui.md#stitching-metrics)拼接量度[和](/help/stitching/use-stitching-ui.md#bad-ids)資訊。 | 2026年3月6日 | 待定 |
| **Report Builder：管理員可看見所有已排程的活頁簿**<br/> Report Builder Excel增益集包含新的篩選選項，可讓管理員檢視指定組織的所有已排程活頁簿，無論排程對象為何。 此篩選選項僅適用於Analytics管理員。 檢視排程活頁簿時，「活頁簿」索引標籤和「舊版」索引標籤都會提供此功能。<p>在分散式團隊間移轉活頁簿時，檢視所有已排程活頁簿的功能特別實用，因為它可讓管理員在移轉活頁簿之前輕鬆找到所有舊版活頁簿。</p><p>以前，管理員只能看到他們排程的活頁簿，看不到其他使用者排程的活頁簿。</br>如需詳細資訊，請參閱[管理排程活頁簿](/help/report-builder/manage-schedules-reportbuilder.md)。</p> | | 2026年3月10日 |
| **更新至Approximate Count Distinct函式**<br/> Approximate Count Distinct函式中使用的HLL機率演演算法即將更新。 使用此函式的數字之結果輸出可能會和歷史數字稍有不同，如下所示：<ul><li>計算極少量不重複值時，結果將改善為使用精確計數，而不是使用預估值。</li><li>計算任何較大的數字時，計數估計將保持本次更新之前的準確性（估計準確性在準確數字的5%以內，即時間的95%）。</li></ul><p>如需Approximate Count Distinct函式的詳細資訊，請參閱[進階函式](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md)</p> | | 2026年3月10日 |
| **完整的表格匯出功能改善**<br/>&#x200B;完整的表格匯出功能包含下列增強功能：<p>匯出建立和設定增強功能</p><ul><li>從「匯出」頁面建立匯出。 之前，您只能在表格上按一下右鍵，以從Analysis Workspace建立匯出。</li><li>建立匯出時新增帳戶或位置。</li><li>自動建立檔案名稱及放置匯出檔案的資料夾。 如此一來，檔案名稱便能以可預測的形式，並以邏輯的方式整理到資料夾中。 以前，檔案名稱無法預測且會分組到單一資料夾中。</li><li>支援將資料匯出為Parquet檔案，以改善Data Warehouse相容性。 之前，僅支援CSV和JSON。</li></ul><p>匯出管理增強功能</p><ul><li>從「匯出」頁面更新或取消一或多個匯出。</li><li>從「記錄」頁面重新傳送一或多個匯出。</li><li>當匯出失敗或即將到期時，以電子郵件傳送個別使用者或群組。</li><li>匯出失敗更精確的錯誤訊息。</li></ul><p>計算量度、區段和維度增強功能</p><ul><li>支援更多計算量度函式。 之前，僅支援簡單的數學函式。</li><li>建立匯出時套用區段。</li><li>支援雙資料型別維度，以提高精確度。</li></ul><p>管理增強功能</p><ul><li>管理員現在可以檢視所有匯出和記錄，無論其建立者為何。</li></ul><p>如需詳細資訊，請參閱下列資源：<ul><li>[將完整表格匯出至雲端](/help/analysis-workspace/export/export-cloud.md)</li><li>[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)</li><li>[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)</li><li>[管理匯出](/help/components/exports/manage-exports.md)</li><li>[管理雲端匯出位置和帳戶](/help/components/exports/manage-export-locations.md)</li><li>[管理匯出記錄檔](/help/components/exports/manage-export-logs.md)</li></ul></p> | 2026年2月25日 | 2026年3月11日<p>（原計畫於2026年3月4日）</p> |
| **Analysis Workspace的實作教學課程**<br/>&#x200B;現在提供新的實作教學課程，引導新使用者瞭解在Analysis Workspace中使用面板、視覺效果和元件的基本知識。 <p>(文件連結待補充。)<!--For more information, see "Learning paths" in "Customer Journey Analytics landing page".--></p> | | 2026年3月18日 |
| **支援資料映象**<br/>&#x200B;透過Experience Platform中特定來源聯結器的模型架構和變更資料擷取(CDC)功能支援，Customer Journey Analytics將能支援[資料映象](/help/data-mirror/data-mirror.md)資料倉儲解決方案的功能，例如[!DNL Snowflake]、[!DNL Azure Databricks]和[!DNL Google BigQuery]。<p>若要存取 Beta 版，請聯絡您的 Adobe 帳戶團隊。</p> | Beta 版：2025 年 9 月 24 日 | 2026年3月25日 |
| **Data Insights Agent與Copilot整合** <br/> Data Insights Agent現在與Microsoft Copilot整合，可讓您直接在Microsoft工具（包括Teams、Powerpoint等）中，使用自然語言提示與Customer Journey Analytics資料互動。<p>(文件連結待補充。)</p> | | 2026 年 3 月 26 日 |
| **Adobe工程代理程式中的資料驗證** <br/>Data Engineering Agent中有新的資料驗證技能。 這些技能可協助團隊在Customer Journey Analytics中分析資料之前，直接在Adobe Experience Platform中快速評估資料品質。 <p>資料驗證技能可啟用隨選、欄位層級和資料集層級驗證，將統計摘要與無效或異常值的智慧型偵測結合在一起。 </p><p>使用資料驗證技能可減少手動QA工作量，並加快跨資料工程工作流程的可信資料上線和轉換。</p><p>(文件連結待補充。)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年3月31日 |
| **將劃分套用至面板**<br/>&#x200B;您現在可以將劃分套用至面板。 在面板層級套用劃分時，劃分會套用至面板內所有自由表格中的所有欄。 | 2026 年 3 月 | 2026 年 5 月 |
| **串流媒體服務：支援排程資料** <br/>您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤觀看率。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |
| **義大利語支援**<br/>&#x200B;義大利語言環境(it-IT)現在在Customer Journey Analytics的Analysis Workspace中受到支援。 <p>Customer Journey Analytics支援Experience Platform UI支援的所有語言，如[Experience Platform UI的瀏覽器和語言支援](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)中所述。</p><p>您可以在Experience Platform中[變更您的預設語言](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)。</p> | | 2026年4月8日 |

## Customer Journey Analytics 中的修正

**Analysis Workspace**： AN-440336、AN-440216、AN-438445、AN-438216、AN-437856、AN-437776、AN-437765、AN-437365、AN-432793、AN-432094、AN-431557、AN-431200、AN-429621、AN-429424、AN-427973、AN-426089、AN-425883 424359
**元件**：
**Content Analytics**：
**引導式分析**：
**匯出**： AN-432030
**資料檢視**： AN-440004、AN-437154、AN-431165
**實作**：
**Report Builder**： AN-437895、AN-437083、AN-434288、AN-434209、AN-433224、AN-430622
**報告**： AN-439482、AN-439545、AN-438708、AN-431206、AN-430079、AN-428302、AN-428257、AN-425779、AN-423330
**分段**：
**排程報告**：
**共用的量度和維度**：
**Other**： AN-439795、AN-434783、AN-434233、AN-434005、AN-433368、AN-431322、AN-431165、AN-431012、AN-429983、AN-429067、AN-423285


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
