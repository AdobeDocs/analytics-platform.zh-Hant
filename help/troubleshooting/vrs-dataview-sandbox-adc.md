---
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 9%

---
# 虛擬報告套件、資料視圖、AEP沙箱和分析源連接器

Adobe提供了建立虛擬報告環境和沙盒環境的多種方法。 瞭解以下特徵之間的相似性和差異，以及這些特徵與 [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant):

* Adobe Analytics虛擬報告套件
* CJA資料視圖
* AEP沙箱

## Adobe Analytics虛擬報告套件(VRS)

有關詳細資訊，請參閱： [虛擬報告套件概述](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hant)。

VRS:

* 可以基於Adobe Analytics段。
* 可以以非破壞性方式應用於歷史資料和新資料。
* 允許您在Adobe Analytics報告套件的頂部建立一個或多個虛擬視圖，供不同業務團隊使用。
* 可用於控制對Adobe Analytics不同用戶的不同類型資料的訪問和管理。
* 提供可選 [報告時處理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hant) Adobe Analytics。 在這種情況下，VRS可用於為「訪問」建立自定義定義。
* 在報表運行時應用，類似於段評估。 這是 _後_ 資料已經收集並儲存在Adobe Analytics。
* 是 [跨設備分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hant) 在Adobe Analytics。
* 可用的變數數與標準分析報告套件（250個eVars、250個道具、1000個事件）相同，但VRS建立可以限制向用戶暴露的變數。
* 支援自定義日曆選項。

虛擬報告套件不是：

* 提供將報告套件組合在一起的方法。
* 可在Adobe AnalyticsData Warehouse購買。
* 可作為通過分析源連接器將資料流導入AEP的源。 只有完整（非虛擬）報告套件可用於分析源連接器。


## CJA資料視圖

有關詳細資訊，請參閱： [資料視圖概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hant)。

資料視圖：

* 可以基於CJA篩選器。
* 可以以非破壞性方式應用於歷史資料和新資料。
* 允許您在CJA連接頂部建立一個或多個虛擬視圖，供不同業務團隊使用。
* CJA中可以用於控制對不同用戶的不同類型資料的訪問和管理。
* 為通過CJA連接傳入CJA的資料提供了強大的非破壞性選項。
* 基於CJA的報告時間處理能力。
* 允許用戶為「會話」建立自定義定義。
* 在報表運行時應用，與篩選器評估類似。 這是 _後_ 源連接器(Adobe Analytics或其他)已將資料寫入AEP資料湖中的資料集， _後_ 資料已通過CJA連接被接收到CJA。
* 允許無限數量的變數，儘管建立可以限制向用戶顯示的變數
* 允許自定義命名「事件」、「會話」和「人員」容器。
* 支援自定義日曆選項。

資料視圖不：

* 直接提供一種組合報表套件或其他資料集的方法。 而是在CJA連接中與資料集組合。 來自CJA連接的組合資料可用於基於該連接的所有資料視圖中。

## AEP沙箱

有關詳細資訊，請參閱： [沙箱概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。

AEP沙箱：

* 提供一種將單個AEP實例分區為獨立虛擬環境(開發、test、階段、生產等)的方法 幫助開發和發展數字型驗應用。
* 可以將其視為一個容器，它保存給定環境的所有資料和應用程式。

AEP沙箱不：

* 提供類似於虛擬報告套件、CJA連接或資料視圖的功能。
* 它自己將報表套件與其他資料集組合在一起。 但是，沙盒中的資料集可以在CJA連接中組合。

進一步：

* 來自不同沙箱的資料不能在CJA中組合。
* 分析源連接器發送報告套件資料 _入_ 一個特定的沙盒。 每個報告套件都可配置為單個沙箱的源。 查看 [分析源連接器文檔](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) 的子菜單。