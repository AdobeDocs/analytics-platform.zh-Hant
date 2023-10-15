---
title: 在報告活動管理器中檢視報告活動
description: 了解如何使用報告活動管理器在尖峰報告期間診斷和修正容量問題。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '1731'
ht-degree: 16%

---

# 在報告活動管理器中檢視報告活動

{{release-limited-testing}}

此 [!UICONTROL 報告活動管理器] 可讓管理員在尖峰報告期間快速診斷和修正報告容量問題。

如需報告活動管理員的詳細資訊，包括主要權益和許可權要求，請參閱 [報告活動管理器總覽](/help/reporting-activity-manager/reporting-activity-overview.md).

## 檢視所有連線的報告活動 {#view-all-report-suites}

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

   此時會顯示已啟用基本連線的清單。

   ![報告佇列](assets/reporting-activity1.png)

1. （選擇性）您可以搜尋或篩選連線清單：

   * 使用搜尋欄位來搜尋特定連線。 開始輸入連線名稱或ID，並在您輸入時輸入連線更新清單。

   * 選取 [!UICONTROL **篩選**] 圖示 ![篩選圖示](assets/filter-icon.png) 以展開篩選選項清單。 篩選依據 [!UICONTROL **我的最愛**] 或 [!UICONTROL **狀態**].

     若要將連線標示為我的最愛，請選取連線名稱左側的星形圖示。

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. 檢視每個連線的使用率資訊。 您可以選取欄標題，依該欄排序表格。

   可使用下列欄:

   | UI 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 連線]** | 您正在監控其報告活動的連線。 |
   | **[!UICONTROL 資料檢視]** | 顯示饋入連線的所有資料檢視。 由於套用了額外層級的篩選和細分，資料檢視增加了報告請求的複雜性。 來自資料檢視的所有請求都會合併到連線中。<p>例如，如果您有來自5個資料檢視的10個請求，則連線中有50個請求。 如此一來，您很快就會達到容量。 |
   | **[!UICONTROL 容量使用情況]** | 連線的即時報告容量使用百分比。 <p>**注意** 使用容量為100%並不一定表示您應立即開始取消報告請求。 如果平均等待時間合理，則100%使用容量可能狀況良好。 另一方面，如果排入佇列的請求數量也在增加，則100%的使用容量可能會造成問題。</p> |
   | **[!UICONTROL 已佇列的請求]** | 等待處理的要求數目。 <!-- ??? --> |
   | **[!UICONTROL 佇列等待時間]** | 開始處理要求前的平均等待時間。 <!-- ???? --> |
   | **[!UICONTROL 狀態]** | 可能的狀態包括： <ul><li>[!UICONTROL **作用中**] （藍色）：已在連線上執行報告，且正在監視其活動。</li><li>[!UICONTROL **非使用中**] （灰色）：連線未曾執行任何報告。 只有在首次建立連線時，才會顯示此狀態。</li></ul> |

   {style="table-layout:auto"}

## 檢視單一連線的報告活動

1. 在Customer Journey Analytics中選取 [!UICONTROL **工具**] > [!UICONTROL **報告活動管理器**].

1. 選取您要檢視其詳細資訊之連線的連結標題。

   系統會顯示您所選連線的報告活動資料。

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. 使用可用的圖表和表格來瞭解連線中的報告活動。

   * [檢檢視表](#view-graphs)

   * [檢視表格](#view-table)

### 檢檢視表

下列圖表可協助您更清楚瞭解連線中發生的活動。

如果圖形不可見，請選取 [!UICONTROL **顯示圖表**] 按鈕。

#### 使用率圖表 {#utilization}

「使用率」圖表顯示所選連線在過去2小時內的報告使用率。

暫留在圖表上可檢視該分鐘使用容量百分比最高的時間點。

* **X軸**：過去2小時內的報告使用容量。
* **Y軸**：以分鐘為單位的報表使用容量百分比。

  ![使用率圖表](assets/utilization-graph.png)

#### 不同使用者圖表

「不同使用者」圖表顯示所選連線在過去2小時內的報告活動。

將滑鼠指標暫留在圖表上可檢視該分鐘最大使用者數最高的時間點。

* **X軸**：過去2小時時間範圍內的報告活動。
* **Y軸**：提出報表請求的使用者人數（以分鐘計）。

  ![不同使用者圖表](assets/distinct-users-graph.png)

#### 請求圖表

「要求」圖表顯示過去2小時內所選連線的已處理及完成要求數目。

將游標暫留在圖表上可檢視該分鐘最大請求數最高的時間點。

* **X軸**：過去2小時時段內已處理和已完成的請求數。
* **Y軸**：以分鐘計算的已處理要求（紫色）和已完成要求（綠色）數目。

  ![不同使用者圖表](assets/requests-graph.png)

#### 佇列圖表

「佇列」圖表顯示所選連線在過去2小時內報告要求的平均佇列等待時間（以秒為單位）。

將游標停留在圖表上可檢視該分鐘最大平均等待時間最高的時間點。

* **X軸**：過去2小時時段內報表要求的平均佇列等待時間。
* **Y軸**：平均等待時間（以秒為單位）。

  ![不同使用者圖表](assets/queueing-graph.png)

### 檢視表格 {#view-table}

您可以選擇資料表格頂端的下列任一標籤來檢視資料： [!UICONTROL **請求**]， [!UICONTROL **使用者**]， [!UICONTROL **專案**]，或 [!UICONTROL **應用**].

>[!TIP]
>
>您可以選取 [!UICONTROL **隱藏圖表**] 以僅顯示表格。

![表格索引標籤](assets/indiv-report-ste-table-tabs.png)

#### 依請求檢視資料

當您選取 [!UICONTROL **請求**] 標籤中，表格中有以下欄：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **請求ID**] | 可用於疑難排解。 |
| [!UICONTROL **執行時間**] | 要求已執行多久。 |
| [!UICONTROL **開始時間**] | 要求開始處理的時間（根據管理員的當地時間）。 |
| [!UICONTROL **等待時間**] | 請求在處理之前已等待多長時間。 當有足夠的容量時，此值通常為「0」。 |
| [!UICONTROL **應用程式**] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：區段、計算量度、註解、對象等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>智慧型警報</li></ul> |
| [!UICONTROL **使用者**] | 起始請求的使用者。 <p>**注意：** 如果此欄的值為 [!UICONTROL **無法辨識**]，這表示使用者是在您沒有管理許可權的登入公司。</p> |
| [!UICONTROL **專案**] | 儲存的 Workspace 專案名稱、API 報告 ID 等。(中繼資料可能因各種應用程式而異。) |
| [!UICONTROL **狀態**] | 狀態指示器： <ul><li>**執行中**：請求目前正處理中。</li><li>**擱置中**：請求正等待處理中。</li></ul> |
| [!UICONTROL **複雜性**] | 並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。 <p>可能的值包括：</p> <ul><li>[!UICONTROL **低**]</li><li>[!UICONTROL **媒體**]</li><li>[!UICONTROL **高**]</li></ul>此值會受下列欄中的值影響：<ul><li>[!UICONTROL **月邊界**]</li><li>[!UICONTROL **欄**]</li><li>[!UICONTROL **區段**]</li></ul> |
| [!UICONTROL **月邊界**] | 請求中包含的月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **欄**] | 請求中的量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **區段**] | 套用至請求的區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

#### 依使用者檢視資料

當您選取 [!UICONTROL **使用者**] 標籤中，表格中有以下欄：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **使用者**] | 起始請求的使用者。 如果此欄的值為 [!UICONTROL **無法辨識**]，這表示使用者是在您沒有管理許可權的登入公司。 |
| [!UICONTROL **請求數量**] | 使用者起始的請求數。 |
| [!UICONTROL **專案數量**] | 與使用者相關聯的專案數。 <!-- ??? --> |
| [!UICONTROL **應用程式**] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：區段、計算量度、註解、對象等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>智慧型警報</li></ul> |
| [!UICONTROL **平均複雜度**] | 使用者起始的要求的平均複雜性。 <p>並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。</p><p>此欄中的值以分數為基礎，分數由下列欄中的值決定：</p><ul><li>[!UICONTROL **平均月邊界**]</li><li>[!UICONTROL **平均欄數**]</li><li>[!UICONTROL **平均區段數**]</li></ul> |
| [!UICONTROL **平均月邊界**] | 包含在要求中的平均月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **平均欄數**] | 包含的請求中的平均量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **平均區段數**] | 套用至所包含要求的平均區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

#### 依專案檢視資料

當您選取 [!UICONTROL **專案**] 標籤中，表格中有以下欄：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **專案**] | 起始查詢的專案。 |
| [!UICONTROL **請求數量**] | 與專案相關聯的請求數。 |
| [!UICONTROL **使用者人數**] | 與專案相關聯的使用者人數。 <!-- ??? --> |
| [!UICONTROL **應用程式**] | [!UICONTROL 報告活動管理器]支援的應用程式有： <ul><li>Analysis Workspace UI</li><li>Workspace 排程專案</li><li>Report Builder</li><li>產生器 UI：區段、計算量度、註解、對象等。</li><li>1.4 或 2.0 API 的 API 呼叫</li><li>智慧型警報</li></ul> |
| [!UICONTROL **平均複雜度**] | 專案中包含之要求的平均複雜性。 <p>並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。</p><p>此欄中的值以分數為基礎，分數由下列欄中的值決定：</p><ul><li>[!UICONTROL **平均月邊界**]</li><li>[!UICONTROL **平均欄數**]</li><li>[!UICONTROL **平均區段數**]</li></ul> |
| [!UICONTROL **平均月邊界**] | 包含在要求中的平均月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **平均欄數**] | 包含的請求中的平均量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **平均區段數**] | 套用至所包含要求的平均區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

#### 依應用程式檢視資料

當您選取 [!UICONTROL **應用**] 標籤中，表格中有以下欄：

| 欄 | 說明 |
| --- | --- |
| [!UICONTROL **應用程式**] | 起始查詢的應用程式。 |
| [!UICONTROL **請求數量**] | 與應用程式相關聯的要求數目。 |
| [!UICONTROL **使用者人數**] | 與應用程式相關聯的使用者數目。 <!--???--> |
| [!UICONTROL **專案數量**] | 與應用程式相關聯的專案數目。 <!--???--> |
| [!UICONTROL **平均複雜度**] | 與應用程式相關之要求的平均複雜性。 <p>並非所有請求都需要相同的時間處理。 要求複雜性有助於提供處理要求所需時間的一般概念。</p><p>此欄中的值以分數為基礎，分數由下列欄中的值決定：</p>此欄中的值以分數為基礎，分數由下列欄中的值決定：<ul><li>[!UICONTROL **平均月邊界**]</li><li>[!UICONTROL **平均欄數**]</li><li>[!UICONTROL **平均區段數**]</li></ul> |
| [!UICONTROL **平均月邊界**] | 包含在要求中的平均月數。 月邊界越多，請求就越複雜。 |
| [!UICONTROL **平均欄數**] | 包含的請求中的平均量度和劃分數。 更多欄會增加請求的複雜性。 |
| [!UICONTROL **平均區段數**] | 套用至所包含要求的平均區段數。 更多區段會增加請求的複雜性。 |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this connection. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this connection. |

{style="table-layout:auto"}

-->
