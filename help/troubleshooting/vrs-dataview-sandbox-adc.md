---
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 96%

---
# 虛擬報告套裝、資料檢視、AEP 沙箱和 Analytics 來源連接器

Adobe 提供多種方法來建立虛擬報告環境和沙箱環境。 了解以下功能之間的異同，以及這些功能與 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)的關係會很有用：

* Adobe Analytics 虛擬報告套裝
* CJA 資料檢視
* AEP 沙箱

## Adobe Analytics 虛擬報告套裝 (VRS)

如需詳細資訊，請參閱：[虛擬報告套裝總覽](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hant)。

VRS：

* 可以以 Adobe Analytics 區段為基礎。
* 可以以非破壞性方式同時套用至歷史資料和新資料。
* 允許您在Adobe Analytics報告套件的頂部建立一個或多個虛擬視圖，供不同業務團隊使用。
* 可用於控制 Adobe Analytics 中不同使用者對不同資料類型的存取和管理。
* 為 Adobe Analytics 提供選用的[報告時間處理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant)功能。 在這種情況下，可以使用 VRS 為「造訪」建立自訂定義。
* 在報告執行階段套用，類似於區段評估。 這是在資料收集並儲存在 Adobe Analytics 中&#x200B;_之後_。
* 對於 Adobe Analytics 中的[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hant)是必要項目。
* 提供與標準 Analytics 報告套裝相同數量的變數 (250 個 eVar、250 個 prop、1000 個事件)，不過 VRS 組織可以限制向使用者公開哪些變數。
* 支援自訂行事曆選項。

虛擬報告套裝不是 (會)：

* 提供組合報告套裝的方法。
* 可用於 Adobe Analytics Data Warehouse。
* 可用作透過 Analytics 來源連接器進入 AEP 之資料流的來源。 只有完整 (非虛擬) 報告套裝可用於 Analytics 來源連接器。


## CJA 資料檢視

如需詳細資訊，請參閱[資料檢視總覽](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hant)。

資料檢視：

* 可以以 CJA 篩選器為基礎。
* 可以以非破壞性方式同時套用至歷史資料和新資料。
* 可讓您在 CJA 連線之上建立一個或多個虛擬檢視，以供不同的業務團隊使用。
* 可用於控制 CJA 中不同使用者對不同資料類型的存取和管理。
* 提供強大的非破壞性選項，用於轉換和增強透過 CJA 連線進入 CJA 的資料。
* 是根據 CJA 的報告時間處理能力。
* 允許使用者為「工作階段」建立自訂定義。
* 在報告執行階段套用，類似於篩選器評估。 這是在來源連接器 (Adobe Analytics 或其他) 將資料寫入 AEP 資料湖的資料集&#x200B;_之後_，以及在透過 CJA 連線將資料擷取到 CJA _之後_。
* 允許無限數量的變數，不過組織可以限制向使用者公開哪些變數
* 允許自訂命名事件、工作階段和人員容器。
* 支援自訂行事曆選項。

資料檢視無法：

* 直接提供組合報告套裝或其他資料集的方法。 相反，資料集是在 CJA 連線中組合在一起的。 來自 CJA 連線的組合資料可用於根據該連線的所有資料檢視。

## AEP 沙箱

如需詳細資訊，請參閱：[沙箱總覽](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。

AEP 沙箱：

* 提供將單一 AEP 執行個體劃分為單獨虛擬環境 (開發、測試、暫存、生產等) 的方法 協助開發和發展數位體驗應用程式。
* 將其視為一個容器，其中包含特定環境的所有資料和應用程式。

AEP 沙箱無法：

* 提供類似於虛擬報告套裝、CJA 連線或資料檢視的功能。
* 單獨組合具有或不具有其他資料集的報告套裝。 不過，沙箱中的資料集可以在 CJA 連線中組合。

延伸閱讀：

* 來自不同沙箱的資料不能在 CJA 中組合。
* Analytics 來源連接器會將報告套裝資料傳送&#x200B;_到_&#x200B;特定沙箱。 每個報告套裝都可以設定為單一沙箱的來源。 如需詳細資訊，請參閱 [Analytics 來源連接器文件](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en)。