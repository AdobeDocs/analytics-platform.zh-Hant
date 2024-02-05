---
title: 如何在 Customer Journey Analytics 中管理連線
description: 說明如何在Customer Journey Analytics (Customer Journey Analytics)中管理與Experience Platform資料集的連線。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: a377c9bc4b58623e0b04da7f9ff1010572f7a610
workflow-type: tm+mt
source-wordcount: '2535'
ht-degree: 25%

---

# 管理連線

一旦您擁有 [已建立或編輯一或多個連線](/help/connections/create-connection.md)，您可在中管理這些變數 **[!UICONTROL 連線]**. 連線可讓您：

* 檢視您的所有連線總覽，包括擁有者、沙箱以及連線的建立和修改時間。
* 編輯連線。
* 刪除連線。
* 從連線建立資料檢視。
* 檢視連線中的所有資料集。
* 檢查連線資料集的狀態和擷取程式的狀態。 例如，您的資料何時可用，以便從Analysis Workspace的報告與分析開始。
* 識別因設定錯誤所導致的任何資料差異。 您是否有遺漏任何資料列？如果有的話，遺漏了哪些資料列以及為什麼遺漏？ 您是否將連線設定錯誤並導致Customer Journey Analytics中資料遺失？


表格會顯示所有可用的連線。 您可以使用搜尋快速搜尋連線 ![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 方塊。

表格中有以下欄/圖示。

| 欄/圖示 | 說明 |
| --- | --- |
| [!UICONTROL 名稱] | 連線的易記名稱。 若要檢視連線的詳細資訊，請選取超連結的名稱。 另請參閱 [連線詳細資料](#connection-details). |
| ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 若要檢視以下資訊： [!UICONTROL 包含的資料集]， [!UICONTROL Sandbox]， [!UICONTROL 所有者]，等等，選取 ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 連線名稱旁。<p>快顯視窗會顯示詳細資訊。 <p><img src="./assets/conn-info.png" alt="檢視連線資訊" width="50%" /> |
| ![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 至 [建立資料檢視](#create-a-data-view) 針對連線，選取 ![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) . 只有在尚未有任何資料檢視與連線相關聯時，此圖示才會顯示。 |
| ![更多內容](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 選取 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 至： <p>![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [編輯](#edit-a-connection) 連線。<p>![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [刪除](#delete-a-connection) 連線。<p>![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [建立新的資料檢視](#create-a-data-view). 使用這個專案來建立連線的其他資料檢視。 |
| [!UICONTROL 資料集] | 顯示連線中資料集的一或多個連結。 您可以選取資料集超連結來檢視連線中的資料集。 如果所選連線包含更多資料集，請選取 **[!UICONTROL +*x* 更多]** 以顯示 **[!UICONTROL 包含的資料集]** 面板。 此面板會顯示所有資料集的連結，以及搜尋屬於連線之特定資料集的選項。<p><img src="./assets/datasets-included.png" alt="包含的資料資產" width="50%" /><p>選取資料集名稱，即可在新索引標籤的Experience PlatformUI中開啟資料集。 |
| [!UICONTROL 沙箱] | 顯示 [Experience Platform沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 此連線從中提取其資料集的。 當您初次建立連線時，就會選取這個沙箱。 此沙箱無法變更。 |
| [!UICONTROL 所有者] | 建立連線的人。 |
| [!UICONTROL 匯入新資料] | 顯示匯入資料集新資料的狀態： <p><span style="color:green">●</span>   **[!UICONTROL _x _開啟]**關於有多少資料集已設定為匯入新資料，以及&lt;/<p><span style="color:gray">●</span>   **[!UICONTROL _x關閉_]** 針對已關閉多少資料集的新資料匯入。 |
| [!UICONTROL 建立日期] | 建立連線時的時間戳記。 |
| [!UICONTROL 上次修改日期] | 上次更新連線時的時間戳記。 |
| [!UICONTROL 回填資料] | 跨資料集顯示回填資料的狀態。<p><span style="color:red">●</span>   **[!UICONTROL _x _回填失敗]**如需資料集間失敗的回填數，<p><span style="color:orange">●</span>   **[!UICONTROL _x _正在處理回填]**如需跨資料集處理回填的次數，<p><span style="color:green">●</span>   **[!UICONTROL _x _回填已完成]**資料集的已完成回填數，以及<p><span style="color:grey">●</span>   **[!UICONTROL _關閉_]** 以防連線中的資料集未定義回填。 |

您可以使用來設定要顯示哪些欄 ![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). 這會顯示 **自訂表格** 對話方塊可讓您開啟/關閉表格中的欄。

## 編輯連線

可讓管理員編輯連線。

1. 選取 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 連線名稱旁
1. 選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]** 從內容功能表。

或者，您可以：

1. 選取連線列。

1. 選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]** 從藍色列。

編輯連線時，您可以：

* 開始和停止匯入新資料。
* 為連線重新命名。
* 重新整理資料集。
* 從連線移除資料集

另請參閱 [建立或編輯連線](create-connection.md) 以取得詳細資訊。


## 刪除連線 {#connections-delete}

允許管理員刪除連線。

1. 選取 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 連線名稱旁。
1. 選取 ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 刪除]**.

或者，您可以：

1. 選取連線列。

1. 選取 ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 刪除]** 從藍色列。

當您刪除連線時， **[!UICONTROL 刪除連線]** 面板會指出哪些資料檢視已刪除，以及哪些工作區專案會受到影響。

<img src="./assets/delete-connection.png" alt="刪除連線" width="50%" />

選取 **[!UICONTROL 繼續]** 以刪除連線。

另請參閱 [刪除關聯](/help/admin/cja-deletion.md) 有關刪除連線之影響的詳細資訊。


## 建立資料檢視

可讓管理員為連線建立資料檢視。

* 如果沒有資料檢視與連線相關聯：

   1. 選取 ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) 連線名稱旁。

* 如果已為連線建立一或多個資料檢視：

   1. 選取 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 連線名稱旁。
   1. 選取 ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立新的資料檢視]**.

或者，您可以：

1. 選取連線列。

1. 選取 ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立資料檢視]** 藍色按鈕列中的。

如需詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)。

## 連線詳細資料 {#connection-detail}

若要移至連線的詳細資訊，請在連線表格中選取連線名稱。

![顯示Widget和設定的所有資料集視窗](assets/conn-details.png)

連線詳細資訊介面提供連線狀態的詳細檢視。 您可以：

* 檢查連線的資料集及擷取程序的狀態。
* 識別可能導致略過或刪除記錄的設定問題。
* 了解資料何時可用來報告。

| 使用者介面 | 說明 |
| --- | --- |
| ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL 編輯連線] | 若要編輯連線的詳細資訊，請選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯連線]** . 另請參閱 [建立或編輯連線](create-connection.md) 以取得詳細資訊。 |
| 資料集選擇器 | 可讓您選擇連線中的一個或所有資料集。 您無法多重選取資料集。 預設為「[!UICONTROL 所有資料集]」。 |
| 日期範圍選擇器 | 編輯開始和/或結束日期或選取 ![行事曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 以開啟資料範圍選擇器。 在日期範圍選取器中，使用其中一個預先定義的期間來選取日期範圍(例如 **[!UICONTROL 過去6個月]**)或使用日曆來選取開始和結束日期。 選取 **[!UICONTROL 套用]** 以套用新的資料範圍。 |
| [!UICONTROL 可用的事件資料記錄] | 代表在&#x200B;**整個連線**&#x200B;中可用來報告的總事件資料集列數。 此計數與任何行事曆設定皆無關。 如果您從資料集選擇器選取資料集，或在表格中選取資料集，則計數會變更。 新增資料後，會延遲1-2小時讓資料出現在報告中。 |
| [!UICONTROL 量度] | 針對&#x200B;**資料集以及您選取的日期範圍**&#x200B;彙總已新增/略過/刪除的事件記錄，以及已新增的批次數量。<p>選取 **[!UICONTROL 檢查詳細資訊]** 以顯示 **[!UICONTROL 檢查略過的詳細資訊]** 快顯視窗，為所有事件資料集或選取的資料集列出略過的記錄數量和原因。<p><img src="./assets/skipped-records.png" width="70%"/><p>選取 ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 包含更多資訊的快顯視窗。 由於某些略過的原因，例如 [!UICONTROL 空的訪客ID]，快顯視窗會顯示您可在其中使用的EQS範例PSQL (查詢服務Experience Platform) [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) 以查詢資料集中略過的記錄。 選取 ![複製](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL 複製EQS的範例PSQL]** 複製SQL。 |
| [!UICONTROL 新增的記錄] | 指出在選取的時段內，針對您選取的資料集和日期範圍&#x200B;**新增了多少列。**&#x200B;每 10 分鐘更新一次。 <p>**注意**：資料 **[!UICONTROL 新增的記錄]** 目前僅包括事件資料，不包括設定檔或查詢資料。 |
| [!UICONTROL 略過的記錄] | 針對您選取的資料集和日期範圍&#x200B;**，指出在選取的時段內已略過多少列。**&#x200B;略過記錄的原因包括：遺漏時間戳記、遺漏或無效的個人ID等。 每 10 分鐘更新一次。 <p>人員 ID 無效 (例如「未定義」、「00000000」，或[!UICONTROL 人員 ID] 在指定月份中出現超過 100 萬次的事件) 無法歸因於任何特定使用者或人員。無法將擷取資料擷取至系統中，並導致容易出錯的擷取和報告。 若要修正無效的人員 ID，請選擇下列 3 種方法：<ul><li>使用 [拼接](/help/stitching/overview.md) 以使用有效的使用者ID填入未定義或全零的使用者ID。</li><li>將使用者ID留空，在擷取期間將略過該使用者ID （偏好使用無效或全零的使用者ID）。</li><li>在擷取資料之前，請先修正系統中任何無效的使用者 ID。</li></ul> <p>**注意**：資料 **[!UICONTROL 略過的記錄]** 目前僅包括事件資料，不包括設定檔或查詢資料。 |
| [!UICONTROL 記錄] 已刪除 | 針對&#x200B;**資料集以及您選取的日期範圍**&#x200B;指示在所選的時段內刪除了多少列。 例如，可能有人已刪除 Experience Platform 中的資料集。 每 10 分鐘更新一次。<p>**注意**：資料 **[!UICONTROL 刪除的記錄]** 目前僅包括事件資料，不包括設定檔或查詢資料。 |
| ![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _搜尋資料集名稱或識別碼_ | 資料集搜尋欄位。 您可以依資料集名稱或頁面名稱 [!UICONTROL 資料集ID]. |
| [!UICONTROL 資料集表格] | 顯示屬於連線之一部分的資料集。 |
| [!UICONTROL 資料集] | 顯示屬於連線之一部分的資料集名稱。 您可以選取超連結，在新標籤的Experience PlatformUI中開啟資料集。 您可以選取列或核取方塊，僅顯示所選資料集的詳細資訊。 |
| [!UICONTROL 資料集 ID] | 由Experience Platform自動產生。 |
| [!UICONTROL 新增的記錄] | 在選取的時間間隔內新增到連線的資料集記錄/列數。 |
| [!UICONTROL 略過的記錄] | 在選取的時間間隔內，針對連線在資料傳輸期間略過的資料集記錄/列數。 |
| [!UICONTROL 刪除的記錄] | 在選取的時間間隔內，從連線中移除的資料集記錄/列數。 |
| [!UICONTROL 批次已新增] | 已新增到連線的資料集批次數量。 |
| [!UICONTROL 上次新增時間] | 從資料集新增到連線的最新批次時間戳記。 |
| [!UICONTROL 資料來源類型] | 資料集的來源型別。 建立連線時，您可以定義來源型別。 |
| [!UICONTROL 資料集類型] | 此資料集的資料集型別。 型別可以是 [!UICONTROL 事件]， [!UICONTROL 查詢]，或 [!UICONTROL 個人資料]. [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| 結構描述 | 資料集所根據的Experience Platform結構描述。 |
| [!UICONTROL 匯入新資料] | 顯示匯入資料集新資料的狀態： <p><span style="color:green">●</span>   **[!UICONTROL _x _開啟]**如果資料集已設定為匯入新資料，以及<p><span style="color:gray">●</span>   **[!UICONTROL _x關閉_]** 如果資料集已設定為不匯入新的資料匯入。 |
| [!UICONTROL 回填資料] | 顯示資料集的回填資料狀態。<p><span style="color:red">●</span>   **[!UICONTROL _x _回填失敗]**回填失敗的數目，<p><span style="color:orange">●</span>   **[!UICONTROL _x _正在處理回填]**對於處理的回填數，<p><span style="color:green">●</span>   **[!UICONTROL _x _回填已完成]**已完成回填數，以及<p><span style="color:grey">●</span>   **[!UICONTROL _關閉_]** 以防未設定回填。 |

>[!IMPORTANT]
>
>2021年8月13日之前擷取的任何資料都不會反映在 [!UICONTROL 連線] 介面。

### 「連線」面板

在資料集表格中未選取資料集時，「連線」介面右側的面板會顯示連線選項和詳細資訊。

| 選項/詳細資訊 | 說明 |
| --- | --- |
| ![重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 重新整理] | 若要重新整理連線並允許反映最近新增的記錄，請選取 ![重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 重新整理]**. |
| ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 刪除]** | [刪除](#delete-a-connection) 此連線。 |
| ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立資料檢視]** | [建立資料檢視](#create-a-data-view) 根據此連線。 另請參閱 [資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html) 以取得詳細資訊。 |
| [!UICONTROL 連線名稱] | 顯示連線的易記名稱。 |
| [!UICONTROL 連線說明] | 顯示更詳細的說明，說明此連線的用途。 |
| [!UICONTROL 沙箱] | 此 [Experience Platform沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 此連線從中提取其資料集。當您初次建立連線時，就會選取這個沙箱。 此沙箱無法變更。 |
| [!UICONTROL 連線 ID] | 此ID會以Experience Platform產生。 您可以使用 ![複製](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) 以複製ID。 |
| [!UICONTROL 使用連線的資料檢視] | 列出所有使用此連線的資料檢視。 |
| [!UICONTROL 匯入新資料] | 顯示匯入資料集新資料的狀態： <p><span style="color:green">●</span>   **[!UICONTROL _x _開啟]**瞭解有多少資料集已設定為匯入新資料，以及<p><span style="color:gray">●</span>   **[!UICONTROL _x關閉_]** 針對已關閉多少資料集的新資料匯入。 |
| [!UICONTROL 回填資料] | 顯示資料集的回填資料狀態。<p><span style="color:red">●</span>   **[!UICONTROL _x _回填失敗]**如需資料集間失敗的回填數，<p><span style="color:orange">●</span>   **[!UICONTROL _x _正在處理回填]**如需跨資料集處理回填的次數，<p><span style="color:green">●</span>   **[!UICONTROL _x _回填已完成]**資料集的已完成回填數，以及<p><span style="color:grey">●</span>   **[!UICONTROL _關閉_]** 以防連線中的資料集未定義回填。 |
| [!UICONTROL 建立者] | 顯示建立連線的使用者名稱。 |
| [!UICONTROL 上次修改日期] | 顯示上次變更連線的時間戳記。 |
| [!UICONTROL 上次修改者] | 顯示上次修改連線的使用者。 |

### 資料集面板

在資料集表格中選取資料集時，「連線」介面右側的面板會顯示所選資料集的詳細資訊。

| 詳細資料 | 說明 |
| --- | --- |
| [!UICONTROL 人員 ID] | 顯示在 Experience Platform 的最新結構描述中所定義的身分識別。 這是您在建立連線時所選取的人員ID 。 如果您建立的連線包含具有不同ID的資料集，報表會反映這一點。 若要合併資料集，您需要在不同資料集中使用相同的人員ID。 |
| [!UICONTROL 索引鍵] | 顯示您已為查詢資料集指定的金鑰。 |
| [!UICONTROL 比對索引鍵] | 顯示您已為查詢資料集指定的相符索引鍵。 |
| [!UICONTROL 時間戳記] | 顯示為事件資料集定義的時間戳記。 |
| [!UICONTROL 可用記錄] | 代表在透過行事曆選取的特定時段中，為此資料集擷取的總列數。 在新增資料後，資料會立即出現在報告中，不需要等候。 不過，當您建立全新連線時， [延遲](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL 新增的記錄] | 表示在選取的時段內新增了多少列。 |
| [!UICONTROL 刪除的記錄] | 表示在選取的時段內刪除了多少記錄。 |
| [!UICONTROL 批次已新增] | 表示已將多少資料批次新增到這個資料集內。 |
| [!UICONTROL 略過的記錄] | 表示在選取的時段內擷取資料時，略過了多少列。<p>略過記錄的原因包括：遺漏時間戳記、遺漏或無效的個人ID等。 每 10 分鐘更新一次。<p>人員 ID 無效 (例如「未定義」、「00000000」，或[!UICONTROL 人員 ID] 在指定月份中出現超過 100 萬次的事件) 無法歸因於任何特定使用者或人員。無法將擷取資料擷取至系統中，並導致容易出錯的擷取和報告。 若要修正無效的人員 ID，請選擇下列 3 種方法：<ul><li>使用 [拼接](/help/stitching/overview.md) 以使用有效的使用者ID填入未定義或全零的使用者ID。</li><li>將使用者ID留空，在擷取期間會略過該使用者ID （偏好使用無效或全零的使用者ID）。</li><li>在擷取資料之前，請先修正系統中任何無效的使用者 ID。</li></ul> |
| [!UICONTROL 上次新增時間] | 表示上次新增批次的時間。 |
| [!UICONTROL 匯入新資料] | 顯示匯入資料集新資料的狀態： <p><span style="color:green">●</span>   **[!UICONTROL _x _開啟]**如果資料集已設定為匯入新資料，以及<p><span style="color:gray">●</span>   **[!UICONTROL _x關閉_]** 如果資料集已設定為不匯入新的資料匯入。 |
| [!UICONTROL 回填資料] | 顯示資料集的回填資料狀態。<p><span style="color:red">●</span>   **[!UICONTROL _x _回填失敗]**回填失敗的數目，<p><span style="color:orange">●</span>   **[!UICONTROL _x _正在處理回填]**對於處理的回填數，<p><span style="color:green">●</span>   **[!UICONTROL _x _回填已完成]**已完成回填數，以及<p><span style="color:grey">●</span>   **[!UICONTROL _關閉_]** 以防未設定回填。<p>若要顯示對話方塊以概覽資料集過去的回填，請選取「 」 <img src="./assets/pastbackfill.svg" alt="過去的回填" width="2%" /> **[!UICONTROL 過去的回填]**. |
| [!UICONTROL 資料來源類型] | 將資料集新增至連線時所定義的資料來源型別。 |
| [!UICONTROL 資料集類型] | 可能是[!UICONTROL 事件]、[!UICONTROL 查詢]或[!UICONTROL 描述檔]。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| [!UICONTROL 結構描述] | 顯示此資料集所根據的Experience Platform結構描述。 |
| [!UICONTROL 資料集 ID] | 此資料集ID會以Experience Platform產生。 |


>[!MORELIKETHIS]
>
>[檢視、疑難排解及修改連線設定](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html?lang=en) 教學課程。
