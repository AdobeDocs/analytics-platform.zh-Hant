---
title: Customer Journey Analytics護欄
description: 瞭解Customer Journey Analytics的護欄
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: 17cd5170e62b410ebf6118c6ac562d20b81b4e21
workflow-type: tm+mt
source-wordcount: '2012'
ht-degree: 9%

---

# Customer Journey Analytics護欄

本檔案提供Customer Journey Analytics各種元件的限制。 如需護欄、範圍設定引數和權益，請參閱[Customer Journey Analytics的產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/customer-journey-analytics.html)或Adobe Analytics附加元件的[產品說明： Customer Journey Analytics](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html)。

## 限制型別

本檔案有兩種預設限制：

| 護欄型別 | 說明 |
|----------|---------|
| **效能護欄（軟性限制）** | 效能護欄是與使用案例範圍相關的使用限制。 超過效能護欄時，您可能會遇到效能降低和延遲的狀況。 Adobe對這類效能降低不負任何責任。 持續超過效能護欄的客戶可選擇授權額外的容量，以避免效能降低。 |
| **系統強制的護欄（硬限制）** | Customer Journey Analytics UI或API會強制執行系統強制的護欄。 這些限制不得超過，因為UI和API會封鎖您這樣做或傳回錯誤。 |

{style="table-layout:auto"}

限制的某些功能及其相關值取決於您有權使用的Customer Journey Analytics套件。

>[!NOTE]
>
>本檔案概述的值可能會因產品持續改善而有所變更。 請定期回訪以取得更新消息。 如果您有興趣瞭解自訂限制，請聯絡客戶服務代表。

## 臨機SQL查詢

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 重試逾時 | 90 | 系統強制的護欄 | 報告引擎回應要求需要太長時間才能傳回結果（可能是因為其他同時進行的請求）前的秒數上限，可以再次要求。 |
| 請勿重試逾時 | 600 | 系統強制的護欄 | 臨機SQL查詢逾時前的秒數上限。 若無其他規定，報告引擎報告請求傳回結果所花時間過長，且不應重試之前的最大秒數。 此請求極有可能因為背景處理序中的問題而無法傳回結果。 |
| 量度 | 150 | 系統強制的護欄 | 請求中的最大量度數。 |
| 互動式查詢輸出列 | 50,000 | 系統強制的護欄 | 除非另有指定，否則傳回的預設列數。 |

{style="table-layout:auto"}

## Analysis Workspace專案

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每個表格的可見列數 | 400 | 系統強制的護欄 | Analysis Workspace專案中任何自由表格的可見列數上限。 |
| 每個資料表的可匯出資料列 | 50,000 | 系統強制的護欄 | 每個單一維度可匯出的最大列數。 |
| 每個專案的面板 | 15 | 系統強制的護欄 | 每個專案最多[個面板](../analysis-workspace/home.md#panels)個。 |
| 每個面板的視覺效果 | 25 | 系統強制的護欄 | 每個面板最多[個視覺效果](../analysis-workspace/home.md#visualizations)個。 |
| 每個自由表格的衍生欄位 | 5 | 系統強制的護欄 | 單一自由表格中不同衍生欄位的最大數量。 |
| 每個專案的註解 <p>**注意：**&#x200B;對專案發表評論的功能處於發行的「有限測試」階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。</p> | 1,000 | 系統強制的護欄 | 每個專案的最大評論數量。 |
| 每個評論的回覆 <p>**注意：**&#x200B;對專案發表評論的功能處於發行的「有限測試」階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。</p> | 100 | 系統強制的護欄 | 每個評論的最大回複數。 |
| 每個註解的影像 <p>**注意：**&#x200B;對專案發表評論的功能處於發行的「有限測試」階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。</p> | 5 | 系統強制的護欄 | 每個註解的最大影像數量。 |
| 影像大小 <p>**注意：**&#x200B;對專案發表評論的功能處於發行的「有限測試」階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。</p> | 2 | 系統強制的護欄 | 專案中評論的最大每個影像上傳大小（以MB為單位） |

{style="table-layout:auto"}


<!--

Add this to the table above, change - for pipe : (End of April, 2025 when project commenting is GA)

Comments per project - 1,000 - System-enforced Guardrail - Maximum number of comments per project. 
Replies per comment - 100 - System-enforced Guardrail - Maximum number of replies per comment. 
Images per comment - 5 - System-enforced Guardrail - Maximum number of images per comment. 
Image size - 2 - System-enforced Guardrail - Maximim upload size per image in MB 

-->

<!--

## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

-->

## 客群

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 對象區段 | 20 | 系統強制的護欄 | 每個對象最多[個區段](../components/filters/filters-overview.md)個。 |
| 對象身分的數量 | 2000萬 | 系統強制的護欄 | 每個對象的最大身分數量。 |
| 對象重新整理頻率 | 4 | 系統強制的護欄 | 可以重新整理[對象](../components/audiences/audiences-overview.md)的頻率上限（小時）。 |
| 對象重新整理回顧期間 | 90 | 系統強制的護欄 | 重新整理回顧期間的最大天數。 |
| 重新整理對象到期日 | 13 | 系統強制的護欄 | 對象從建立日期起停止重新整理的最大月數。 客戶可再延長13個月。 |
| 重新整理對象的數量 | 75， 150 | 系統強制的護欄 | 重新整理對象的最大數量。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |

{style="table-layout:auto"}

另請參閱Experience Platform [ Real-time Customer Data Platform護欄](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=zh-Hant)。


## 自動化資料集有效期

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|:---:|
| 工單 | 20 | 系統強制的護欄 | 每月自動資料集到期工作單的最大數量。 |

{style="table-layout:auto"}



## 連線、資料檢視、專案

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 專案 | 50,000 | 系統強制的護欄 | 組織的最大專案數量。 |
| 資料檢視 | 2,000 | 系統強制的護欄 | 組織最多[個資料檢視](../data-views/data-views.md)個。 |
| 資料檢視 | 500-1000 | 系統強制的護欄 | 連線的最大資料檢視數量。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |
| 資料集 | 100 | 系統強制的護欄 | 每個連線最多[個資料集](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=zh-Hant)個。 |
| 連線 | 1000 | 系統強制的護欄 | 組織的[連線](../connections/overview.md)數目上限。 |
| 連線標題 | 500 | 系統強制的護欄 | 連線標題的最大字元數。 |
| 量度 | 5,000 | 系統強制的護欄 | 資料檢視中的最大量度數量。 |
| 維度 | 5,000 | 系統強制的護欄 | 資料檢視中的最大維度數量。 |
| 附註標題 | 100 | 系統強制的護欄 | 附註標題的最大字元數。 |
| 附註說明 | 250 | 系統強制的護欄 | 附註說明的最大字元數。 |
| 結構描述欄位 | 10 | 系統強制的護欄 | 定義[衍生欄位](../data-views/derived-fields/derived-fields.md)的規則時，結構描述欄位的最大數量（不包括標準欄位）。 |
| 查詢/設定檔欄位 | 3 | 系統強制的護欄 | 為衍生欄位定義規則時，結構描述欄位（不包括標準欄位）數量上限內的查閱或設定檔結構描述欄位數量上限。 |
| 衍生欄位 | 100 - 500 | 系統強制的護欄 | 每個連線的最大衍生欄位數。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |

{style="table-layout:auto"}


## 資料傳輸限制

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 欄位 | 10,000 | 系統強制的護欄 | 資料集中每列的屬性或欄位數上限。 |
| 唯一字串 | 1000萬 | 系統強制的護欄 | 每個查詢資料集的最大唯一索引鍵數。 |
| 資料列 | 100萬 | 系統強制的護欄 | 連線中指定月份每個不重複人員ID的最大列數。 |
| 列大小 | 2 | 效能護欄/系統強制的護欄 | 擷取到Customer Journey Analytics的每列資料的平均大小(KB) （軟性限制）。 列大小的靜態限制由Experience Platform中資料擷取的護欄決定。 |

{style="table-layout:auto"}

另請參閱Experience Platform [資料擷取的護欄](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=zh-Hant)。


## 目的地資料匯出

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 資料匯出 | 授權的資料湖儲存空間總數 | 效能護欄 | 客戶可使用目的地資料集匯出，將資料湖中的客戶資料匯出至授權的資料湖儲存空間總數。 |
| 可用的資料集 | 設定檔和事件 | 系統強制的護欄 | 透過來源、Web SDK、Mobile SDK、Analytics Data Connector和Audience Manager擷取或收集資料後，在Experience Platform UI中建立事件、設定檔或查詢資料集。 |

{style="table-layout:auto"}

另請參閱Experience Platform [資料集匯出護欄](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/guardrails#dataset-exports)


## 資料登陸區域

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每個沙箱的資料登陸區域 | 1 | 系統強制的護欄 | 每個沙箱的最大資料登陸區域數量。 |
| 資料儲存 | 7 | 系統強制的護欄 | 資料在刪除前會先儲存在資料登陸區域的最大天數。 |

{style="table-layout:auto"}


## 欄位式拚接

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 拼接資料集 | 5 - 50 | 系統強制的護欄 | 每個客戶的最大拼接資料集數量。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |
| 回填長度 | 6 - 25 | 系統強制的護欄 | 回填資料的最大月數。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |
| 回顧期間/重播頻率 | 1/1 - 30/7 | 系統強制的護欄 | 最大回顧期間（以天為單位）/重播頻率。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |

{style="table-layout:auto"}


## 圖表式彙整

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 拼接資料集 | 10 - 50 | 系統強制的護欄 | 每個客戶的最大拼接資料集數量。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |
| 回填長度 | 13 - 25 | 系統強制的護欄 | 回填資料的最大月數。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |
| 回顧期間/重播頻率 | 1/1 - 30/7 | 系統強制的護欄 | 最大回顧期間（以天為單位）/重播頻率。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |


## 區段和計算量度

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每個區段的容器 | 50 | 系統強制的護欄 | 每個區段的容器數上限。 |
| 每個計算量度的量度 | 25 | 系統強制的護欄 | 每個計算量度的最大量度數。 |
| 每個區段的量度和維度 | 25 | 系統強制的護欄 | 每個區段的最大不重複量度和維度數量。 |
| 每個區段的巢狀容器 | 10 | 系統強制的護欄 | 每個區段的巢狀容器數上限。 |
| 每個區段的規則 | 100 | 系統強制的護欄 | 每個區段的最大規則數。 |
| 每個區段每個Dimension的字串比較 | 100 | 系統強制的護欄 | 每個區段每個維度的最大字串比較數量。 |
| 計算的量度 | 6,000 | 系統強制的護欄 | 組織的計算量度數上限。 |
| 區段 | 50,000 | 系統強制的護欄 | 可為組織定義的最大區段數。 |
| API 呼叫 | 120 | 系統強制的護欄 | 每分鐘API要求數（每6秒12個要求）。 |

{style="table-layout:auto"}


## 行動應用程式

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 圖磚 | 16 | 系統強制的護欄 | 每個計分卡的最大圖磚數。 |
| 區段 | 10 | 系統強制的護欄 | 每個計分卡的最大區段數。 |
| 維度 | 10 | 系統強制的護欄 | 每個計分卡的最大維度數量。 |

{style="table-layout:auto"}

## Report Builder

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 活頁簿檔案大小 | 5 | 系統強制的護欄 | 排程活頁簿的檔案大小上限（以MB為單位）。 |
| 資料區塊 | 1000 | 系統強制的護欄 | 每個活頁簿最多[個資料區塊](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=zh-Hant)個。 |
| 量度 | 20 | 系統強制的護欄 | 每個資料區塊的最大量度數。 |
| 日期範圍範圍 | 13 | 系統強制的護欄 | 每個資料區塊可跨越之日期範圍的最大月數。 |
| 資料列 | 50,000 | 系統強制的護欄 | 每個資料區塊的最大列數。 |

{style="table-layout:auto"}


## 完整表格匯出

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每份報告的列數 | 300萬 — 3億 | 系統強制的護欄 | 每個報表的最大報表列數。 值會因Customer Journey Analytics套件而異（請參閱產品說明）。 |
| 每個表格的劃分 | 5 | 系統強制的護欄 | 每個表格的最大劃分數。 |
| 每個表格的量度 | 5 | 系統強制的護欄 | 每個資料表的量度數上限。 |
| 排程頻率 | 1 | 系統強制的護欄 | 匯出作業可以每天排程一次(1)，或以較長的排程進行（例如：每2天或每週排程一次）。 |

{style="table-layout:auto"}

## 延遲

>[!NOTE]
>
>以下處理時間為護欄，而非合約服務等級協定(SLA)。 延遲會依客戶組態、資料磁碟區和消費者應用程式而有所不同。 實際的處理速度通常更快。 請參閱您的Customer Journey Analytics合約，以瞭解特定合約條款及SLA。 如需詳細資訊，請參閱Experience Platform [資料擷取的護欄](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=zh-Hant)。

| 資料流程 | 預期延遲 |
|---|---|
| Adobe Analytics到Adobe Analytics Source聯結器（啟用A4T） | &lt; 30分鐘 |
| Adobe Analytics Source Connector到即時客戶個人檔案（A4T未啟用） | &lt; 2分鐘 |
| Adobe Analytics Source Connector到即時客戶個人檔案（A4T已啟用） | &lt; 30分鐘 |
| 資料從Edge Network擷取至Data Lake或串流擷取 | &lt; 60分鐘 |
| 資料從Adobe Analytics Source Connector擷取至Data Lake | &lt; 2.25小時 |
| 將資料從資料湖擷取至Customer Journey Analytics | &lt; 90分鐘 |
| 彙整（選擇性功能；如需詳細資訊，請參閱[彙整概觀](../stitching/overview.md)） | &lt; 4小時 |
| Adobe Analytics Source Connector回填少於100億個事件（最多13個月的歷史資料） | &lt; 4週 |
| 將對象發佈到即時客戶個人檔案，包括自動建立串流區段，並允許區段準備好接收資料。 | ≈ 60分鐘 |
| 重新整理對象的頻率 | 一次性重新整理：延遲少於5分鐘。<br/>每4小時、每天、每週、每月重新整理一次（延遲與重新整理頻率同步進行）。 |

{style="table-layout:auto"}
