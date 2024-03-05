---
title: Customer Journey Analytics護欄
description: 瞭解Customer Journey Analytics的護欄
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: b945ae10d9107a760e32f5d111e5c14724898646
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 8%

---

# Customer Journey Analytics護欄

本檔案提供Customer Journey Analytics各種元件的限制。 如需護欄、範圍引數和權益，請參閱 [Customer Journey Analytics的產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/customer-journey-analytics.html) 或 [Adobe Analytics附加元件的產品說明：Customer Journey Analytics](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## 限制型別

本檔案有兩種預設限制：

| 護欄型別 | 說明 |
|----------|---------|
| **效能護欄（軟性限制）** | 效能護欄是與使用案例範圍相關的使用限制。 超過效能護欄時，您可能會遇到效能降低和延遲的狀況。 Adobe對這類效能降級概不負責。 持續超過效能護欄的客戶可選擇授權額外的容量，以避免效能降低。 |
| **系統強制的護欄（硬限制）** | 系統強制的護欄由Customer Journey Analytics UI或API強制執行。 這些限制不得超過，因為UI和API會封鎖您這樣做或傳回錯誤。 |

{style="table-layout:auto"}

限制的某些功能及其關聯值取決於您有權使用的Customer Journey Analytics套件。

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
| 每個專案的面板 | 15 | 系統強制的護欄 | 最大數量 [面板](../analysis-workspace/home.md#panels) 每個專案。 |
| 每個面板的視覺效果 | 25 | 系統強制的護欄 | 最大數量 [視覺效果](../analysis-workspace/home.md#visualizations) 每個面板。 |
| 每個自由表格的衍生欄位 | 5 | 系統強制的護欄 | 單一自由表格中不同衍生欄位的最大數量。 |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## 對象

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 對象篩選器 | 20 | 系統強制的護欄 | 最大數量 [篩選器](../components/filters/filters-overview.md) 每個對象。 |
| 對象身分的數量 | 2000萬 | 系統強制的護欄 | 每個對象的最大身分數量。 |
| 對象重新整理頻率 | 4 | 系統強制的護欄 | 最大頻率（小時an） [對象](../components/audiences/audiences-overview.md) 可能會重新整理。 |
| 對象重新整理回顧期間 | 90 | 系統強制的護欄 | 重新整理回顧期間的最大天數。 |
| 重新整理對象到期日 | 13 | 系統強制的護欄 | 對象從建立日期起停止重新整理的最大月數。 客戶可再延長13個月。 |
| 重新整理對象的數量 | 75， 100 | 系統強制的護欄 | 重新整理對象的最大數量，值會依封裝而異（請參閱產品說明）。 |

{style="table-layout:auto"}

另請參閱Experience Platform [Real-time Customer Data Platform護欄](https://experienceleague.adobe.com/docs/experience-platform/profile/Guardrails.html?lang=en).


## 自動化資料集有效期

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|:---:|
| 工單 | 20 | 系統強制的護欄 | 每月自動資料集到期工作單的最大數量。 |

{style="table-layout:auto"}



## 連線、資料檢視、專案

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 專案 | 2,000 | 系統強制的護欄 | 組織的最大專案數量。 |
| 資料檢視 | 2,000 | 系統強制的護欄 | 最大數量 [資料檢視](../data-views/data-views.md) 適用於組織。 |
| 資料檢視 | 50 | 系統強制的護欄 | 連線的最大資料檢視數量 |
| 資料集 | 100 | 系統強制的護欄 | 最大數量 [資料集](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) 每個連線。 |
| 連線 | 1000 | 系統強制的護欄 | 最大數量 [連線](../connections/overview.md) 適用於組織。 |
| 連線標題 | 500 | 系統強制的護欄 | 連線標題的最大字元數。 |
| 量度 | 5,000 | 系統強制的護欄 | 資料檢視中的最大量度數量。 |
| 維度 | 5,000 | 系統強制的護欄 | 資料檢視中的最大維度數量。 |
| 附註標題 | 100 | 系統強制的護欄 | 附註標題的最大字元數。 |
| 附註說明 | 250 | 系統強制的護欄 | 附註說明的最大字元數。 |
| 結構描述欄位 | 10 | 系統強制的護欄 | 為定義規則時結構描述欄位的最大數量（不包括標準欄位） [衍生欄位](../data-views/derived-fields/derived-fields.md). |
| 查詢/設定檔欄位 | 3 | 系統強制的護欄 | 為衍生欄位定義規則時，結構描述欄位（不包括標準欄位）數量上限內的查閱或設定檔結構描述欄位數量上限。 |
| 衍生的欄位 | 100 | 系統強制的護欄 | 每個連線的最大衍生欄位數。 |

{style="table-layout:auto"}


## 資料傳輸限制

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 欄位 | 10,000 | 系統強制的護欄 | 資料集中每列的屬性或欄位數上限。 |
| 唯一字串 | 1000萬 | 系統強制的護欄 | 每個查詢資料集的最大唯一索引鍵數。 |
| 「行」 | 100萬 | 系統強制的護欄 | 連線中每個不重複人員ID的最大列數。 |
| 列大小 | 2 | 效能護欄/系統強制的護欄 | 擷取到Customer Journey Analytics的每列資料的平均大小(KB) （軟性限制）。 資料列大小的靜態限制由Experience Platform中資料擷取的護欄決定。 |

{style="table-layout:auto"}

另請參閱Experience Platform [資料擷取的護欄](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en).


## 資料登陸區域

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每個沙箱的資料登陸區域 | 1 | 系統強制的護欄 | 每個沙箱的最大資料登陸區域數量。 |
| 資料儲存 | 7 | 系統強制的護欄 | 資料在刪除前會先儲存在資料登陸區域的最大天數。 |

{style="table-layout:auto"}


## 欄位式拚接

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 拼接資料集 | 10 | 系統強制的護欄 | 每位客戶的最大拼接資料集數，值依適用的Customer Journey Analytics套件而異（請參閱適用的產品說明）。 |
| 回填資料 | 60 | 系統強制的護欄 | 回填資料的最大天數。 |

{style="table-layout:auto"}


## 篩選器和計算量度

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每個篩選器的容器 | 50 | 系統強制的護欄 | 每個篩選器的最大容器數。 |
| 每個計算量度的量度 | 25 | 系統強制的護欄 | 每個計算量度的最大量度數。 |
| 每個篩選器的量度和Dimension | 25 | 系統強制的護欄 | 每個篩選器的不重複量度和維度最大數量。 |
| 每個篩選器的巢狀容器 | 10 | 系統強制的護欄 | 每個篩選器的巢狀容器數上限。 |
| 每個篩選器的規則 | 100 | 系統強制的護欄 | 每個篩選器的最大規則數。 |
| 每個篩選器每個Dimension的字串比較數 | 100 | 系統強制的護欄 | 每個篩選器每個維度的最大字串比較數量。 |
| 計算量度 | 6,000 | 系統強制的護欄 | 組織的計算量度數上限。 |
| 篩選器 | 50,000 | 系統強制的護欄 | 可為組織定義的最大篩選器數。 |
| API 呼叫 | 120 | 系統強制的護欄 | 每分鐘API要求數（每6秒12個要求）。 |

{style="table-layout:auto"}


## 行動應用程式

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 圖磚 | 16 | 系統強制的護欄 | 每個計分卡的最大圖磚數。 |
| 篩選器 | 10 | 系統強制的護欄 | 每個計分卡的最大篩選器數。 |
| 維度 | 10 | 系統強制的護欄 | 每個計分卡的最大維度數量。 |

{style="table-layout:auto"}

## Report Builder

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 活頁簿檔案大小 | 5 | 系統強制的護欄 | 排程活頁簿的檔案大小上限（以MB為單位）。 |
| 資料區塊 | 1000 | 系統強制的護欄 | 最大數量 [個資料區塊](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) 每個活頁簿。 |
| 量度 | 20 | 系統強制的護欄 | 每個資料區塊的最大量度數。 |
| 日期範圍範圍 | 13 | 系統強制的護欄 | 每個資料區塊可跨越之日期範圍的最大月數。 |
| 「行」 | 50,000 | 系統強制的護欄 | 每個資料區塊的最大列數。 |

{style="table-layout:auto"}


## 完整表格匯出

| 名稱 | 值 | 限制型別 | 說明 |
|---|--:|---|---|
| 每份報告的列數 | 300萬 — 3億 | 系統強制的護欄 | 每份報表的最大報表列數；值因適用的Customer Journey Analytics套件而異（請參閱適用的產品說明）。 |
| 每個表格的劃分 | 5 | 系統強制的護欄 | 每個表格的最大劃分數。 |
| 每個表格的量度 | 5 | 系統強制的護欄 | 每個資料表的量度數上限。 |
| 排程頻率 | 1 | 系統強制的護欄 | 匯出作業可以每天排程一次(1)，或以較長的排程進行（例如：每2天或每週排程一次）。 |

{style="table-layout:auto"}

## 延遲

>[!NOTE]
>
>以下處理時間為護欄，而非合約服務等級協定(SLA)。 延遲會依客戶組態、資料磁碟區和消費者應用程式而有所不同。 實際的處理速度通常更快。 請參閱您的Customer Journey Analytics合約，瞭解您的特定合約條款和SLA。 請參閱Experience Platform [資料擷取的護欄](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en) 以取得詳細資訊。

| 資料流程 | 預期延遲 |
|---|---|
| Adobe Analytics至Adobe Analytics來源聯結器（啟用A4T） | &lt; 30分鐘 |
| Adobe Analytics來源聯結器到即時客戶個人檔案（A4T未啟用） | &lt; 2分鐘 |
| Adobe Analytics來源聯結器到即時客戶個人檔案（A4T已啟用） | &lt; 30分鐘 |
| 資料從Edge Network擷取至Data Lake或串流擷取 | &lt; 60分鐘 |
| 資料從Adobe Analytics來源聯結器擷取至資料湖 | &lt; 2.25小時 |
| 從資料湖將資料擷取至Customer Journey Analytics | &lt; 90分鐘 |
| 拼接(選擇性功能；請參閱 [拼接概述](../stitching/overview.md) 以取得詳細資訊) | &lt; 3.25小時 |
| 少於100億個事件的Adobe Analytics來源聯結器回填（最多13個月的歷史資料） | &lt; 4週 |
| 將對象發佈到即時客戶個人檔案，包括自動建立串流區段，並允許區段準備好接收資料。 | ≈ 60分鐘 |
| 重新整理對象的頻率 | 一次性重新整理：延遲少於5分鐘。<br/>每4小時、每日、每週、每月重新整理一次（延遲與重新整理頻率同時發生）。 |

{style="table-layout:auto"}
