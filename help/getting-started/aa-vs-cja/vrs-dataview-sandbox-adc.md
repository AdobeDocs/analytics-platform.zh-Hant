---
title: 虛擬報告套裝、資料檢視、Adobe Experience Platform 沙箱和 Analytics 來源連接器
description: 了解關於虛擬報告環境和沙箱環境。
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: Basics
role: User
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: ht
source-wordcount: '715'
ht-degree: 100%

---

# 虛擬報告套裝、資料檢視、Adobe Experience Platform 沙箱和 Analytics 來源連接器

Adobe 提供多種方法來建立虛擬報告環境和沙箱環境。了解以下功能之間的異同，以及這些功能與 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)的關係會很有用：

* Adobe Analytics 虛擬報告套裝
* Customer Journey Analytics 資料檢視
* Adobe Experience Platform 沙箱

## Adobe Analytics 虛擬報告套裝

如需詳細資訊，請參閱：[虛擬報告套裝概觀](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hant)。

虛擬報告套件：

* 可以以 Adobe Analytics 區段為基礎。
* 可以以非破壞性方式同時套用至歷史資料和新資料。
* 可讓您在 Adobe Analytics 報告套裝之上建立一個或多個虛擬檢視，以供不同的業務團隊使用。
* 可用於控制 Adobe Analytics 中不同使用者對不同資料類型的存取和管理。
* 為 Adobe Analytics 提供選用的[報告時間處理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant)功能。 在這種情況下，可以使用虛擬報告套裝為「造訪」建立自訂定義。
* 在報告執行階段套用，類似於區段評估。 這是在資料收集並儲存在 Adobe Analytics 中&#x200B;_之後_。
* 對於 Adobe Analytics 中的[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)是必要項目。
* 提供與標準 Analytics 報告套裝相同數量的變數 (250 個 eVar、250 個 prop、1000 個事件)，不過虛擬報告套裝組織可以限制向使用者公開哪些變數。
* 支援自訂行事曆選項。

虛擬報告套裝不是：

* 一種組合報告套裝的方法。
* 可用於 Adobe Analytics Data Warehouse。
* 可用作透過 Analytics 來源連接器進入 Adobe Experience Platform 之資料流的來源。只有完整 (非虛擬) 報告套裝可用於 Analytics 來源連接器。


## Customer Journey Analytics 資料檢視

如需詳細資訊，請參閱[資料檢視概觀](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html)。

資料檢視：

* 可以根據 Customer Journey Analytics 區段。
* 可以以非破壞性方式同時套用至歷史資料和新資料。
* 可讓您在 Customer Journey Analytics 連線之上建立一個或多個虛擬檢視，以供不同的業務團隊使用。
* 可用於控制 Customer Journey Analytics 中不同使用者對不同資料類型的存取和管理。
* 提供強大的非破壞性選項，用於轉換和增強透過 Customer Journey Analytics 連線進入 Customer Journey Analytics 的資料。
* 根據 Customer Journey Analytics 的報告時間處理功能。
* 讓使用者能夠為「工作階段」建立自訂定義。
* 在報告執行階段套用，類似於區段評估。這是在來源連接器 (Adobe Analytics 或其他) 將資料寫入 Adobe Experience Platform 資料湖中的資料集&#x200B;_後_，並且資料已透過 Customer Journey Analytics 連線擷取到 Customer Journey Analytics _後_&#x200B;發生的。
* 允許無限數量的變數，不過組織可以限制向使用者公開哪些變數
* 允許自訂命名事件、工作階段和人員容器。
* 支援自訂行事曆選項。

資料檢視無法：

* 直接提供組合報告套裝或其他資料集的方法。 資料集是在 Customer Journey Analytics 連線中組合。來自 Customer Journey Analytics 連線的組合資料可用於根據該連線的所有資料檢視。

## Adobe Experience Platform 沙箱

如需詳細資訊，請參閱：[沙箱概觀](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html)。

Adobe Experience Platform 沙箱：

* 能將單一 Adobe Experience Platform 執行個體分割成個別的虛擬環境 (開發、測試、中繼、生產等)，協助開發及改進數位體驗應用程式。
* 可視為一個容器，其中包含特定環境的所有資料和應用程式。

Adobe Experience Platform 沙箱無法：

* 提供類似於虛擬報告套裝、Customer Journey Analytics 連線或資料檢視的功能。
* 單獨組合具有或不具有其他資料集的報告套裝。不過，沙箱中的資料集可以在 Customer Journey Analytics 連線中組合。

請注意：

* 不同沙箱的資料無法在 Customer Journey Analytics 中組合。
* Analytics 來源連接器會將報告套裝資料傳送&#x200B;_到_&#x200B;特定沙箱。 每個報告套裝都可以設定為單一沙箱的來源。 如需詳細資訊，請參閱 [Analytics 來源連接器文件](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。
