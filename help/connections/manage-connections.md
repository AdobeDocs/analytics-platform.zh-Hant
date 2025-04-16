---
title: 如何在 Customer Journey Analytics 中管理連線
description: 說明如何在 Customer Journey Analytics (Customer Journey Analytics) 中管理與 Experience Platform 資料集的連線。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '4282'
ht-degree: 90%

---

# 管理連線

[建立一或編輯多個連線](/help/connections/create-connection.md)後，您就可以在「**[!UICONTROL 連線]**」中管理這些連線。透過連接您可以：

* 檢視您的所有連線總覽，包括所有者、沙箱以及建立和修改連線的時間。
* 編輯連線。
* 刪除連線。
* 從連線建立資料檢視。
* 檢視連線中的所有資料集。
* 查看連線資料集狀態和攝取過程的狀態。例如，您的資料何時可用，以便您可以開始在 Analysis Workspace 中進行報告和分析。
* 識別因設定錯誤所導致的任何資料差異。 您是否有遺漏任何資料列？如果有的話，遺漏了哪些資料列以及為什麼遺漏？您是否將連設定錯誤並導致 Customer Journey Analytics 中的資料遺失？
* 了解所有連線中已攝取和可報告資料行的使用情況。

[!UICONTROL 連線]有兩個介面： [[!UICONTROL 清單]](#list)和[[!UICONTROL 使用狀況]](#usage)。


## 清單

 [!UICONTROL 清單]介面是連線的預設介面。如果未選取，請選取「**[!UICONTROL 清單]**」標記以存取介面。

![清單檢視](assets/list-view.png)

 [!UICONTROL 清單]介面會顯示所有可用連線的表格。您可以使用搜尋 ![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 框快速搜尋連線。

表格中有以下欄或圖示。

| 欄或圖示 | 說明 |
| --- | --- |
| [!UICONTROL 名稱] | 連線的易記名稱。 若要查看連線的詳細資訊，請選取超連結的名稱。請參閱「[連線詳細資料](#connection-details)」。 |
| ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 若要檢視有關[!UICONTROL 包含的資料集]、 [!UICONTROL 沙箱]、 [!UICONTROL 所有者]等資訊，請選取連線名稱旁邊的  ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 。<p>快顯視窗會顯示詳細資訊。 <p><img src="./assets/conn-info.png" alt="檢視連線資訊" width="400"/> |
| ![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 若要為連線[建立資料檢視](#create-a-data-view) ，請選取「![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)」。只有在沒有資料檢視與連線有關聯時，此圖示才會顯示。 |
| ![更多內容](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 選取「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」： <p>![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [編輯](#edit-a-connection)連線。<p>![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [刪除](#delete-a-connection)連線。<p>![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [建立新的資料檢視](#create-a-data-view)。若為連線建立更多資料檢視。<p>![GraphPathing](/help/assets/icons/GraphPathing.svg)連線對應。 檢視連線的連線對應。 |
| **[!UICONTROL 資料集]** | 前往屬於連線一部分的資料集的一個或多個連結。您可以選取資料集超連結，即可檢視連線中的所有資料集。 如果選取的連線包含更多資料集，請選取 **[!UICONTROL +*x* 更多]**&#x200B;以顯示&#x200B;**[!UICONTROL 包含的資料集]**&#x200B;面板。此面板會顯示所有資料集的連結以及搜尋屬於連線的特定資料集選項。<p><img src="./assets/datasets-included.png" alt="包含的資料集" width="400"/><p>選取資料集名稱會在新分頁中的 Experience Platform UI 中開啟該資料集。 |
| **[!UICONTROL 沙箱]** | [Adobe Experience Platform 沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)，此連線會從這個沙箱提取其資料集 。 當您初次建立連線時，就會選取這個沙箱。 此沙箱無法變更。 |
| **[!UICONTROL 所有者]** | 建立連線的人。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![狀態綠色](assets/status-green.svg)    設定為匯入新資料的資料集的&#x200B;**[!UICONTROL _x _On]**，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，表示資料集未設定為匯入新資料。 |
| **[!UICONTROL 建立日期]** | 建立連線時的時間戳記。 |
| **[!UICONTROL 上次修改日期]** | 上次更新連線的時間戳記。 |
| **[!UICONTROL 回填資料]** | 所有資料集回填資料的狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示所有資料集回填失敗的次數，<p>![橘色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示所有資料集處理回填的次數，<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _回填完成]**，表示資料集回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若連線中的資料集未定義回填。 |

若要設定要顯示的資料欄，請選取「![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」；然後，會顯示&#x200B;**自訂表格**&#x200B;對話框，可讓您開啟或關閉表格中的資料欄。

### 編輯連線

若要編輯連線：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」
1. 從內容選單中選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 「編輯」]**。

或者，您可以：

1. 立即選取連線。

1. 從藍色列選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 「編輯」]**。

編輯連線時，您可以：

* 開始及停止匯入新資料。
* 為連線重新命名。
* 重新整理資料集。
* 從連線移除資料集

如需詳細資訊，請參閱「[建立或編輯連線](create-connection.md)」。


### 刪除連線 {#connections-delete}

若要刪除連線：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」。
1. 選取 ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 「刪除」]**。

或者，您可以：

1. 立即選取連線。

1. 選取藍色列中的 ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 「刪除」]**。

刪除連線時， **[!UICONTROL 刪除連線]**&#x200B;面板會指示哪些資料檢視被刪除以及哪些工作區專案受到影響。

![刪除連線](assets/delete-connection.png)

選取「**[!UICONTROL 繼續]**」以刪除連線。

請參閱「[刪除影響](/help/technotes/deletion.md)」，了解有關刪除連線的詳細資訊。


### 建立連線的資料檢視

為連線建立新的資料檢視的方式

* 如果沒有資料檢視與連線相關聯：

   1. 選取連接名稱旁邊的「![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)」。

* 如果已經為連線建立一個或多個資料檢視：

   1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」。
   1. 選取 ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 「建立新的資料檢視」]**。

或者，您可以：

1. 立即選取連線。

1. 選取藍色按鈕列的 ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 「建立資料視圖」]**。

如需詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)。


### 對應連線

若要檢視[連線對應](/help/connections/create-connection.md#connection-map)，以詳細描述屬於連線之一部份的資料集之間的關係：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」。
1. 選取![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 連線對應]**。

### 連線詳細資訊 {#connection-detail}

若要了解連線的詳細資訊，請在連線表格中選取連線名稱。

![顯示小工具和設定的所有資料集視窗](assets/conn-details.png)

連線詳細資訊介面會提供連線狀態的詳細檢視。您可以：

* 檢查連線的資料集及攝取程序的狀態。
* 識別可以造成記錄被略過或被刪除的設定問題。
* 了解資料何時可用來報告。

| 使用者介面 | 說明 |
| --- | --- |
| ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯連線]**。 | 若要編輯連線的詳細資訊，請選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 「編輯連線」]**。如需詳細資訊，請參閱「[建立或編輯連線](create-connection.md)」。 |
| **[!UICONTROL *資料集選擇器&#x200B;*]** | 可讓您選擇連線中的一個或所有資料集。 您無法多重選取資料集。 預設為「**[!UICONTROL 所有資料集]**」。 |
| **[!UICONTROL *日期範圍選擇器&#x200B;*]** | 編輯開始日期、結束日期，或選取「![行事曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)」，以開啟日期範圍選擇器。在日期範圍選擇器中，使用預先定義時間段之一 (例如&#x200B;**[!UICONTROL 過去 6 個月]**) 選取日期範圍，或使用行事曆來選取開始日期和結束日期。選取「**[!UICONTROL 套用]**」以套用新的日期範圍。 |
| **[!UICONTROL 有可用的事件資料記錄]** | 在&#x200B;**整個連線**&#x200B;中可用來報告的總事件資料集列數。 此計數與任何行事曆設定皆無關。 如果您從資料集選擇器選取資料集，或是選取表格中的資料集，此計數就會改變。 在新增資料後，可能要等候 1-2 個小時，資料才會出現在報告中。 |
| [!UICONTROL **[!UICONTROL 量度]**] | 匯總新增、跳過和刪除的事件、查詢、設定檔和摘要資料集記錄以及新增的批次數。這些量度是根據&#x200B;**您選取的資料集和日期範圍**&#x200B;來決定。<p>選取「**[!UICONTROL 檢查詳細資訊]**」，以顯示「**[!UICONTROL 查看略過的詳細資料]**」快顯視窗。快顯視窗列有所有事件資料集或選取資料集的略過記錄數和原因。<p><img src="./assets/skipped-records.png" width="500"/><p>選取「![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」快顯視窗以取得更多資訊。對於某些略過的原因 (例如[!UICONTROL 訪客 ID 為空])，快顯視窗會顯示 EQS (查詢服務 Experience Platform) 的範例 PSQL，您可以在[查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home) 中用來查詢資料集中的記錄。選取 ![複製](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL 「複製 EQS 的範例 PSQL」]**&#x200B;以複製 SQL。 |
| **[!UICONTROL 新增的記錄]** | 指出在選取的時段內，針對您選取的資料集和日期範圍&#x200B;**新增了多少列。**&#x200B;每 10 分鐘更新一次。 |
| **[!UICONTROL 略過的記錄]** | 針對您選取的資料集和日期範圍&#x200B;**，指出在選取的時段內已略過多少列。**&#x200B;略過記錄的原因包括：遺漏時間戳記、遺漏或無效，或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}等。 每 10 分鐘更新一次。 <p>無效的ID （例如`undefined`或`00000000`，或[!UICONTROL 人員ID]中任何數字與字母的組合，在指定月份中在事件中出現超過100萬次）是無法歸因於任何特定使用者或人員的ID。 這些資料列無法將攝取資料擷取至系統中，並導致容易出錯的攝取和報告。 若要修正無效的人員ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，您有3個選項：<ul><li>使用[拼接](/help/stitching/overview.md)以有效的使用者 ID 填入未定義或全零的使用者 ID。</li><li>將使用者 ID 留空，然後在攝取期間略過 (偏好使用無效或完全零的使用者 ID)。</li><li>在攝取資料之前，請先修正系統中任何無效的使用者 ID。</li></ul> |
| **[!UICONTROL 刪除的記錄]** | 針對&#x200B;**資料集以及您選取的日期範圍**&#x200B;指示在所選的時段內刪除了多少列。 例如，可能有人已刪除 [!DNL Experience Platform] 中的資料集。 每 10 分鐘更新一次。<p>在某些情況下，該值還可以包括已取代的記錄，例如拼接或某些查詢資料集更新。考慮此範例：</p><ul><li>您將一筆記錄上傳到 XDM 設定檔資料集，Customer Journey Analytics 會將其設定為以設定檔查詢資料來攝取。在連線詳細資料中，該資料集將顯示已新增 1 筆記錄。</li><li>您將原始記錄的副本上傳到同一個 AEP 資料集，該資料集現在包含兩個記錄。Customer Journey Analytics會從設定檔或帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}查詢資料集中擷取其他記錄。 看到連線中已擷取該人員ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}的設定檔或帳戶記錄，Customer Journey Analytics會刪除其舊版，並新增設定檔資料。 在連線詳細資料中，此動作將代表1筆新增記錄和1筆刪除記錄，因為Customer Journey Analytics只會保留任何內嵌人員ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}的最新設定檔查詢資料。</li><li>總體來說，AEP 資料集包含兩筆完全相同的記錄。另外，Customer Journey Analytics 連線詳細資料會顯示其攝取資料的狀態：此設定檔資料集新增了 2 筆記錄，刪除了 1 筆記錄。 </li></ul> |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | 資料集搜尋欄位。您可以依據資料集名稱或[!UICONTROL 資料集 ID] 來搜尋資料集表格。 |
| [!UICONTROL 資料集表格] | 顯示屬於連線之一部分的資料集。 請參閱下方的Tabke以取得進一步說明。 |

資料集表格會顯示下列資料欄：

| 欄 | 說明 |
| --- | --- |
| **[!UICONTROL 資料集]** | 屬於連線一部分的資料集名稱。您可以選取超連結，會在新分頁的 Experience Platform UI 中開啟資料集。您可以選取資料列或核取方塊，只顯示所選資料集的詳細資訊。 |
| **[!UICONTROL 資料集 ID]** | 由 Experience Platform 自動產生。 |
| **[!UICONTROL 新增的記錄]** | 在所選的時間間隔期間，新增至連線的資料集記錄 (列) 數。 |
| **[!UICONTROL 略過的記錄]** | 針對所選時間間隔期間的連線，在資料傳輸期間略過的資料集記錄 (列) 數。 |
| **[!UICONTROL 刪除的記錄]** | 在所選的時間間隔期間，從連線中移除的資料集記錄 (列) 數 |
| **[!UICONTROL 批次已新增]** | 已將資料集批次量新增至連線。 |
| **[!UICONTROL 上次新增時間]** | 從新增至連線的任何資料集中的最後批次時間戳記。 |
| **[!UICONTROL 資料來源類型]** | 資料集的來源類型。您在建立連線時定義來源類型。 |
| **[!UICONTROL 資料集類型]** | 此資料集的資料集類型。類型可以是[!UICONTROL 事件]、 [!UICONTROL 設定檔]、 [!UICONTROL 查詢]或[!UICONTROL 摘要]。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL 結構描述]** | 此資料集所根據的 Experience Platform 結構描述。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
| **[!UICONTROL 轉換資料]** | 適用 B2B 查詢資料集的轉換狀態。請參閱[轉換資料集以進行 B2B 查詢](transform-datasets-b2b-lookups.md)，了解更多資訊。<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，表示已啟用進行轉換的適用資料集， <p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，表示未啟用進行轉換的適用資料集，以及<p>**[!UICONTROL N/A]** 於所有其他資料集，不適用於轉換。 |
| **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _x _回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
| **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _十&#x200B;_回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。 |

>[!IMPORTANT]
>
>2021 年 8 月 13 日之前攝取的任何資料，都不會反映在此[!UICONTROL 「連線」]介面中。

#### 連線面板

當資料集表格中未選取任何資料集時，連線介面右側的面板會顯示連線選項和詳細資訊。

| 選項 | 說明 |
| --- | --- |
| ![重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 重新整理] | 若要重新整理連線並允許反映最近新增的記錄，請選取 ![重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 「重新整理」]**。 |
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL 刪除]** | [刪除](#delete-a-connection)此連線。 |
| ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立資料檢視]** | 根據此連線[建立資料檢視](#create-a-data-view)。請參閱「[資料檢視](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/data-views)」，了解更多資訊。 |
| **[!UICONTROL 連線名稱]** | 連線的易記名稱。 |
| **[!UICONTROL 連線說明]** | 更詳細的說明，且可描述此連線的用途。 |
| **[!UICONTROL 沙箱]** | 此連線從中提取其資料集的 [Experience Platform 沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)。當您初次建立連線時會選取這個沙箱。 此沙箱無法變更。 |
| **[!UICONTROL 連線 ID]** | 此 ID 會在 Experience Platform 中產生。您可以使用「![複製](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)來複製此 ID。 |
| **[!UICONTROL 使用連線的資料檢視]** | 列出所有使用此連線的資料檢視。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，表示有多少資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，表示有多少個新資料集匯入已關閉。 |
| **[!UICONTROL 回填資料]** | 資料集回填資料的狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示所有資料集回填失敗的次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示所有資料集處理回填的次數，<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _回填完成]**，表示資料集回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若連線中的資料集未定義回填。 |
| **[!UICONTROL 轉換資料]** | 適用 B2B 查詢資料集的轉換狀態。請參閱[轉換資料集以進行 B2B 查詢](transform-datasets-b2b-lookups.md)，了解更多資訊。<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，表示已啟用進行轉換的資料集數量。 |
| **[!UICONTROL 建立者]** | 建立連線的個人名稱。 |
| **[!UICONTROL 上次修改日期]** | 連接最後一次變更的時間戳。 |
| **[!UICONTROL 上次修改者]** | 上次修改連線的個人。 |

#### 資料集面板

在資料集表格中選取資料集列時，「連線」介面右側的面板會顯示所選資料集的詳細資訊。

| 詳細資料 | 說明 |
| --- | --- |
| **[!UICONTROL 個人 ID]** | 在 Experience Platform 的最新結構描述中所定義的身分識別。 這是您在建立連線期間所選使個人 ID 的身分識別。 如果您建立的連線包含有不同 ID 的資料集，則報告會反映這個情況。 若要合併資料集，您需要在不同資料集中使用相同的使用者 ID。  |
| **[!UICONTROL 索引鍵]** | 您為查詢資料集指定的索引鍵。 |
| **[!UICONTROL 比對索引鍵]** | 您為查詢資料集指定的比對索引鍵。 |
| **[!UICONTROL 時間戳記]** | 為事件資料集定義的時間戳記。 |
| **[!UICONTROL 可用記錄]** | 在透過行事曆選取的特定時段中，為此資料集攝取的資料列總數。 在新增資料後，資料會立即出現在報告中，不需要等候。 然而，當你建立全新連線時， 會有[延遲](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-faq)。 |
| **[!UICONTROL 新增的記錄]** | 在選取的時段內新增了多少列。 |
| **[!UICONTROL 刪除的記錄]** | 在選取的時段內刪除了多少記錄。 |
| **[!UICONTROL 批次已新增]** | 已將多少資料批次新增到這個資料集內。 |
| **[!UICONTROL 略過的記錄]** | 在選取的時段內擷取資料時，略過了多少列。<p>略過記錄的原因包括：遺漏時間戳記、遺漏或無效的個人ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，等等。 每 10 分鐘更新一次。<p>無效的ID （例如`undefined`或`00000000`，或[!UICONTROL 人員ID]中任何數字與字母的組合，在指定月份中出現的次數超過100萬次）是無法歸因於任何特定使用者或人員的ID。 這些資料列無法將攝取資料擷取至系統中，並導致容易出錯的攝取和報告。 若要修正無效的人員ID或帳戶ID，您有3個選項：<ul><li>使用[拼接](/help/stitching/overview.md)以有效的使用者 ID 填入未定義或全零的使用者 ID。</li><li>將使用者 ID 留空，然後在攝取期間略過 (偏好使用無效或完全零的使用者 ID)。</li><li>在攝取資料之前，請先修正系統中任何無效的使用者 ID。</li></ul> |
| **[!UICONTROL 上次新增時間]** | 最後批次新增的時間戳記。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
| **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _十&#x200B;_回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。<p>若要顯示含資料集過去回填概觀的對話框，請選取 <img src="./assets/pastbackfill.svg" alt="過去的回填" width="15"/> **[!UICONTROL 過去的回填]** |
| **[!UICONTROL 資料來源類型]** | 將資料集新增至連線時定義的資料來源類型。 |
| **[!UICONTROL 資料集類型]** | 可能是[!UICONTROL 事件]、[!UICONTROL 設定檔], [!UICONTROL 查詢]或[!UICONTROL 摘要]。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection) |
| **[!UICONTROL 結構描述]** | 此資料集所根據的 Adobe Experience Platform 結構描述。 |
| **[!UICONTROL 資料集 ID]** | 此資料集 ID 會在 Experience Platform 中產生。 |


## 使用情況 {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="關鍵使用情況量度"
>abstract="提供核心和歷史可報告列數的每月資料和總資料。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="每月攝取列數"
>abstract="測量每月新增至系統的記錄總數，以提供對資料增長和攝取率的深入分析。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="每月可報告列數"
>abstract="追蹤可供報告的列數。可報告列數是指已攝取的列數減去攝取期間略過和刪除的列數。可報告列數是計費和資料使用情況的關鍵量度。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="詳細劃分"
>abstract="您可以依據連線、資料集、沙箱和標記來檢視詳細量度，並且可選擇下載資料的 CSV 檔案。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="其他資料集"
>abstract="2024 年 9 月之前的數月在資料集層級收集資料，且為了提高清晰度，該資料顯示為「*其他資料集*」。從 2024 年 9 月開始在詳細程度資料集層級收集資料，*其他資料集*&#x200B;將不再顯示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="未知的資料集或連線"
>abstract="未知的資料集或連線使用其 ID 顯示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="資料無法使用"
>abstract="由於系統限制，無法取得 2024 年 9 月之前的歷史資料。從 2024 年 9 月起收集和顯示量度。此圖表在時間軸上顯示過去 18 個月，而取得可用資料之後將會顯示未來的資料。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="核心可報告列數"
>abstract="顯示過去 13 個月的可用總列數。例如，在 2024 年 2 月 1 日，此數字顯示事件時間戳記從 2023 年 1 月到 2024 年 1 月的可用總列數。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="歷史可報告列數"
>abstract="顯示超過 13 個月以前可用的總列數。例如，在 2024 年 2 月 1 日，此數字顯示事件時間戳記早於 2023 年 1 月的可用總列數。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="關鍵使用情況量度"
>abstract="提供核心和歷史可報告列數的每月資料和總資料。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="每月攝取列數"
>abstract="測量每月新增至系統的記錄總數，以提供對資料增長和攝取率的深入分析。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="每月可報告列數"
>abstract="追蹤可供報告的列數。可報告列數是指已攝取的列數減去攝取期間略過和刪除的列數。可報告列數是計費和資料使用情況的關鍵量度。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="詳細劃分"
>abstract="您可以依據連線、資料集、沙箱和標記來檢視詳細量度，並且可選擇下載資料的 CSV 檔案。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="其他資料集"
>abstract="2024 年 9 月之前的數月在資料集層級收集資料，且為了提高清晰度，該資料顯示為「*其他資料集*」。從 2024 年 9 月開始在詳細程度資料集層級收集資料，*其他資料集*&#x200B;將不再顯示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="未知的資料集或連線"
>abstract="未知的資料集或連線使用其 ID 顯示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="資料無法使用"
>abstract="由於系統限制，無法取得 2024 年 9 月之前的歷史資料。從 2024 年 9 月起收集和顯示量度。此圖表在時間軸上顯示過去 18 個月，而取得可用資料之後將會顯示未來的資料。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="核心可報告列數"
>abstract="顯示過去 13 個月的可用總列數。例如，在 2024 年 2 月 1 日，此數字顯示事件時間戳記從 2023 年 1 月到 2024 年 1 月的可用總列數。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="歷史可報告列數"
>abstract="顯示超過 13 個月以前可用的總列數。例如，在 2024 年 2 月 1 日，此數字顯示事件時間戳記早於 2023 年 1 月的可用總列數。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="核心可報告列數"
>abstract="核心可報告列數是快照的值，而不是彙總總計。這些值會依所選日期範圍內的最後一個月進行動態更新。如果客戶選取 1 月至 3 月，該值將會反映 3 月的快照。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="歷史可報告列數"
>abstract="歷史可報告列數是快照的值，而不是彙總總計。這些值會依所選日期範圍內的最後一個月進行動態更新。如果客戶選取 1 月至 3 月，該值將會反映 3 月的快照。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="累計可報告列數"
>abstract="累計可報告列數是快照的值，而不是彙總總計。這些值會依所選日期範圍內的最後一個月進行動態更新。如果客戶選取 1 月至 3 月，該值將會反映 3 月的快照。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL 使用情況]介面是顯示所有連線中攝取和可報告的行的使用情況。如果未選取，請選取「**[!UICONTROL 使用情況]**」標記以存取介面。

此介面可幫助您確定 Customer Journey Analytics 使用情況是否與合約的協議相符。除了監控目的之外，您還可以使用「使用情況」介面來規劃 Customer Journey Analytics 許可證續約。

「使用情況」介面是使用以下量度

| 量度名稱 | 說明 |
|---|---|
| 歷史可報告列數 | 超過 13 個月的時間段的資料列計數。 |
| 核心可報告列數 | 過去 13 個月的資料列計數。 |
| 攝取的資料列數 | 特定時期內攝取多少資料列。 |
| 可報告的列 | 在特定時期內，作為連線一部分會有多少資料列？ |
| 累計的資料列數 | 截至特定月份已攝取多少資料列。 |

>[!NOTE]
>
>從 2024 年 7 月開始，收集核心、歷史和總計記錄的資料。請聯絡您的客戶經理以取得早期的歷史資料。
>



「使用情況」介面由兩個面板組成：

* **[!UICONTROL 關鍵使用情況量度]**&#x200B;面板：提供核心和歷史資料可報告的資料列。該面板還追蹤核心資料列和歷史資料列與上個月資料比較的百分比變化。

  面板會以視覺效果形式顯示：

   * **[!UICONTROL 核心資料可報告資料列數]**

     過去 13 個月您有多少可報告的資料列？摘要數字是上個月 (例如 2024 年 12 月) 的核心可報告資料列數 (例如 7410 萬)。

   * **[!UICONTROL 歷史資料可報告資料列數]**。

     在超過 13 個月時段內，您有多少可報告的資料列數？摘要數字是上個月 (例如 2024 年 12 月) 的歷史可報告資料列數 (例如 1270 萬)。

  當您將滑鼠暫停在視覺效果中的任何堆積長條圖上時，會有一個快顯視窗顯示該條形圖特定部分的資料列數 (例如)。


  ![關鍵使用量度](assets/usage-key-usage-metrics.png)

* 合併面板，顯示三個子面板：

+++ 攝取的資料列數

  **[!UICONTROL 攝取的資料列數]**&#x200B;子面板會測量每月新增至系統的記錄總數，提供對資料增長和攝取率的深入分析。子面板提供了本月總攝取資料列數以及與上個月相比變化的摘要。

  ![攝取的資料列數](assets/usage-ingested-rows.png)

  您可以將滑鼠停留在視覺效果中的資料點上，以顯示包含更多詳細資料的快顯視窗。

+++

+++ 可報告的資料列數

  **[!UICONTROL 可報告的資料列數]**&#x200B;視覺效果可透過從攝取的資料列數中減去略過和刪除的列數來追蹤可用於報告的資料列數，作為計費和資料使用的關鍵量度。此子面板會提供兩個摘要：

   * **[!UICONTROL 上月總計]**：截至本月的可報告資料列總數摘要。
   * **[!UICONTROL 本月]**：本月可報告資料列總數及與上月相比變化的摘要。

  ![可報告的資料列數](assets/usage-reportable-rows.png)

  您可以將滑鼠停留在視覺效果中的資料點上，以顯示包含更多詳細資料的快顯視窗。

+++

+++ 詳細劃分

  您可以使用&#x200B;**[!UICONTROL 詳細劃分]**&#x200B;表格，按連線、資料集、沙箱和標記來檢視詳細的量度。資料集的報告是使用 ID 而非名稱，因為可在報告期間修改資料集名稱。不明資料集或連線的報告是使用 ID 來進行。

  2024 年 9 月之前的數月在資料集層級收集資料，且為了提高清晰度，該資料顯示為「[!UICONTROL 其他資料集]」。從 2024 年 9 月開始在詳細程度資料集層級收集資料，[!UICONTROL 其他資料集]不會再顯示。

   * 若要變更劃分，請選取一個&#x200B;**[!UICONTROL 檢視方式]**&#x200B;和&#x200B;**[!UICONTROL 劃分方式]**&#x200B;的組合。

     | **[!UICONTROL 「檢視方式」]**&#x200B;選項 | **[!UICONTROL 「劃分」]**&#x200B;選項 |
     |---|---|
     | **[!UICONTROL 連線]** | **[!UICONTROL -]** 和&#x200B;**[!UICONTROL 資料集]** |
     | **[!UICONTROL 資料集]** | **[!UICONTROL -]** |
     | **[!UICONTROL 沙箱]** | **[!UICONTROL 連線]** |
     | **[!UICONTROL 標記]** | **[!UICONTROL 連線]** |

  ![詳細劃分](assets/usage-detail-breakdown.png)

+++

  您可以定義在幾個月後進行報告的&#x200B;**[!UICONTROL 時間範圍]**。使用![行事曆](/help/assets/icons/Calendar.svg)來選取時間範圍。

>[!MORELIKETHIS]
>
>[檢視、疑難排解和修改連線設定](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja)教學課程。
