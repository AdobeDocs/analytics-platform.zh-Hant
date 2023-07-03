---
title: 虛擬報告套裝、資料檢視、Adobe Experience Platform沙箱和Analytics來源聯結器
description: 了解關於虛擬報告環境和沙箱環境。
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: CJA Basics
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 62%

---

# 虛擬報告套裝、資料檢視、Adobe Experience Platform沙箱和Analytics來源聯結器

Adobe 提供多種方法來建立虛擬報告環境和沙箱環境。 了解以下功能之間的異同，以及這些功能與 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)的關係會很有用：

* Adobe Analytics 虛擬報告套裝
* Customer Journey Analytics資料檢視
* Adobe Experience Platform沙箱

## Adobe Analytics 虛擬報告套裝 (VRS)

如需詳細資訊，請參閱：[虛擬報告套裝總覽](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hant)。

虛擬報告套件：

* 可以以 Adobe Analytics 區段為基礎。
* 可以以非破壞性方式同時套用至歷史資料和新資料。
* 可讓您在 Adobe Analytics 報告套裝之上建立一個或多個虛擬檢視，以供不同的業務團隊使用。
* 可用於控制 Adobe Analytics 中不同使用者對不同資料類型的存取和管理。
* 為 Adobe Analytics 提供選用的[報告時間處理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant)功能。 在這種情況下，可以使用 VRS 為「造訪」建立自訂定義。
* 在報告執行階段套用，類似於區段評估。 這是在資料收集並儲存在 Adobe Analytics 中&#x200B;_之後_。
* 對於 Adobe Analytics 中的[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hant)是必要項目。
* 提供與標準 Analytics 報告套裝相同數量的變數 (250 個 eVar、250 個 prop、1000 個事件)，不過 VRS 組織可以限制向使用者公開哪些變數。
* 支援自訂行事曆選項。

虛擬報告套裝不是：

* 一種組合報告套裝的方法。
* 可用於 Adobe Analytics Data Warehouse。
* 可作為透過Analytics來源聯結器流入Adobe Experience Platform的資料流的來源。 只有完整 (非虛擬) 報告套裝可用於 Analytics 來源連接器。


## Customer Journey Analytics資料檢視

如需詳細資訊，請參閱[資料檢視總覽](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hant)。

資料檢視：

* 可以根據Customer Journey Analytics篩選器。
* 可以以非破壞性方式同時套用至歷史資料和新資料。
* 可讓您在Customer Journey Analytics連線之上建立一個或多個虛擬檢視，以供不同的業務團隊使用。
* 可用於控制Customer Journey Analytics中不同使用者對不同資料型別的存取和管理。
* 提供強大的非破壞性選項，用於轉換和增強透過Customer Journey Analytics連線進入Customer Journey Analytics的資料。
* 是根據Customer Journey Analytics的報告時間處理能力。
* 允許使用者為「工作階段」建立自訂定義。
* 在報告執行階段套用，類似於篩選器評估。 這是 _晚於_ 來源聯結器(Adobe Analytics或其他)已將資料寫入Adobe Experience Platform資料湖中的資料集，並且 _晚於_ 資料已透過Customer Journey Analytics連線擷取到Customer Journey Analytics。
* 允許無限數量的變數，不過組織可以限制向使用者公開哪些變數
* 允許自訂命名事件、工作階段和人員容器。
* 支援自訂行事曆選項。

資料檢視無法：

* 直接提供組合報告套裝或其他資料集的方法。 相反，資料集是在Customer Journey Analytics連線中與結合。 來自Customer Journey Analytics連線的組合資料可用於基於該連線的所有資料檢視。

## Adobe Experience Platform沙箱

如需詳細資訊，請參閱：[沙箱總覽](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。

Adobe Experience Platform沙箱：

* 提供將單一Adobe Experience Platform執行個體分割成個別虛擬環境（開發、測試、中繼、生產等）的方法 協助開發和發展數位體驗應用程式。
* 將其視為一個容器，其中包含特定環境的所有資料和應用程式。

Adobe Experience Platform沙箱不會：

* 提供類似虛擬報表套裝、Customer Journey Analytics連線或資料檢視的功能。
* 單獨組合具有或不具有其他資料集的報告套裝。 不過，沙箱中的資料集可以在Customer Journey Analytics連線中組合。

請注意：

* 來自不同沙箱的資料不能在Customer Journey Analytics中合併。
* Analytics 來源連接器會將報告套裝資料傳送&#x200B;_到_&#x200B;特定沙箱。 每個報告套裝都可以設定為單一沙箱的來源。 如需詳細資訊，請參閱 [Analytics 來源連接器文件](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。
