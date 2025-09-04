---
title: 如何在 Customer Journey Analytics 中管理連線
description: 說明如何在 Customer Journey Analytics (Customer Journey Analytics) 中管理與 Experience Platform 資料集的連線。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: f09937e6babca5549b9b78e9c90462673750a4b3
workflow-type: tm+mt
source-wordcount: '4844'
ht-degree: 58%

---

# 管理連線 {#manage-connections}

>[!CONTEXTUALHELP]
>id="connections_use_ajo"
>title="使用 Journey Optimizer 連線"
>abstract="運用 Journey Optimizer 的進階 Customer Journey Analytics 報告功能。"

>[!CONTEXTUALHELP]
>id="connections_cancel_ajo"
>title="取消 Journey Optimizer 連線"
>abstract="取消 Journey Optimizer 的進階 Customer Journey Analytics 報告功能。"


[建立一或編輯多個連線](/help/connections/create-connection.md)後，您就可以在「**[!UICONTROL 連線]**」中管理這些連線。[!UICONTROL 連線]介面可讓您：

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

 **[!UICONTROL 清單]**&#x200B;介面是連線的預設介面。如果未選取，請選取「**[!UICONTROL 清單]**」標記以存取介面。

![清單檢視](assets/list-view.png)

[!UICONTROL List]介面會顯示所有可用連線的表格。

### 搜尋連線

您可以使用搜尋 ![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 框快速搜尋連線。

### 將篩選器套用至連線清單

若要將篩選套用至連線清單，請選取篩選圖示，然後從下列篩選選項中選取：

| 篩選條件選項 | 說明 |
|---------|----------|
| **[!UICONTROL 資料集]** | 只會顯示與您選取的資料集相關聯的連線。 |
| **[!UICONTROL 所有者]** | 只會顯示您所選取人員擁有的連線。 |
| **[!UICONTROL 沙箱]** | 系統只會顯示您選取的沙箱中可用的連線。 |
| 在CJA中&#x200B;**[!UICONTROL 使用]** | 選取&#x200B;**[!UICONTROL 開啟]**&#x200B;以僅顯示已啟用與Customer Journey Analytics搭配使用的連線。 選取&#x200B;**[!UICONTROL 關閉]**，只顯示尚未啟用Customer Journey Analytics的連線。 |

### 適用欄

表格中有以下欄或圖示。

| 欄或圖示 | 說明 |
| --- | --- |
| **[!UICONTROL _名稱_]** | 連線的易記名稱。 選取超連結名稱以檢視連線[的](#connection-details)詳細資料。 |
| ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 若要檢視有關[!UICONTROL 包含的資料集]、 [!UICONTROL 沙箱]、 [!UICONTROL 所有者]等資訊，請選取連線名稱旁邊的  ![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 。<p>快顯視窗會顯示資料集的詳細資訊。 <p>![連線資訊快顯功能表](assets/connection-info-popup.png) |
| ![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 若要為連線[建立資料檢視](#create-a-data-view) ，請選取「![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)」。只有在沒有資料檢視與連線有關聯時，此圖示才會顯示。 |
| ![更多內容](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 選取![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)以開啟內容功能表。 您可以選擇： <p>![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]**&#x200B;以[編輯](#edit-a-connection)連線。<p>![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 刪除]**&#x200B;以[刪除](#delete-a-connection)連線。<p>![資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立新的資料檢視]**&#x200B;以[為連線建立新的資料檢視](#create-a-data-view)。<p>![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 連線對應]**&#x200B;以檢視連線的[連線對應](#map-a-connection)。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 連線型別&#x200B;]** | 連線型別： **[!UICONTROL 人員]**&#x200B;或&#x200B;**[!UICONTROL 帳戶]**&#x200B;連線。 |
| **[!UICONTROL 資料集]** | 前往屬於連線一部分的資料集的一個或多個連結。您可以選取資料集超連結，即可檢視連線中的所有資料集。 如果選取的連線包含更多資料集，請選取 **[!UICONTROL +*x* 更多]**&#x200B;以顯示&#x200B;**[!UICONTROL 包含的資料集]**&#x200B;面板。此面板會顯示所有資料集的連結，以及![搜尋](/help/assets/icons/Search.svg)的選項，以搜尋屬於連線之一部分的特定資料集。<p>![資料集已包含](assets/datasets-included.png)<p>選取資料集名稱，在新索引標籤的Experience Platform介面中開啟資料集。 |
| **[!UICONTROL 沙箱]** | [Adobe Experience Platform 沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)，此連線會從這個沙箱提取其資料集 。 當您建立連線時，請選取此沙箱。 一旦儲存連線後，您就無法變更沙箱。 |
| **[!UICONTROL 所有者]** | 建立連線的人。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![狀態綠色](assets/status-green.svg)   設定為匯入新資料的資料集的&#x200B;**[!UICONTROL _x _On]**，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，表示資料集未設定為匯入新資料。 |
| **[!UICONTROL 建立日期]** | 建立連線時的時間戳記。 |
| **[!UICONTROL 上次修改日期]** | 上次更新連線的時間戳記。 |
| **[!UICONTROL 回填資料]** | 所有資料集回填資料的狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示所有資料集回填失敗的次數，<p>![橘色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示所有資料集處理回填的次數，<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _回填完成]**，表示資料集回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若連線中的資料集未定義回填。 |
| **[!UICONTROL 整合]** | 顯示透過連線啟用的任何Experience Platform應用程式。 |
| 在CJA中&#x200B;**[!UICONTROL 使用]** | 顯示連線是否已啟用以便與Customer Journey Analytics搭配使用。 |

若要設定要在表格中顯示哪些欄，請選取![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)。 在「自訂表格」對話方塊中，選取要顯示的欄。

### 編輯連線

若要編輯連線：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」
1. 從內容選單中選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 「編輯」]**。

或者，您可以：

1. 立即選取連線。

1. 從藍色動作列中選取![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]**。

如需詳細資訊，請參閱「[建立或編輯連線](create-connection.md)」。


### 刪除連線 {#connections-delete}

若要刪除連線：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」。
1. 選取 ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 「刪除」]**。

或者，您可以：

1. 立即選取連線。

1. 從藍色動作列中選取![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 刪除]**。

刪除連線時， **[!UICONTROL 刪除連線]**&#x200B;面板會指示哪些資料檢視被刪除以及哪些工作區專案受到影響。

* 在➊ **[!UICONTROL 資訊]**&#x200B;中，會顯示刪除連線的影響。

  ![刪除連線](assets/delete-connection.png)

  選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以確認刪除。

* 在➋ **[!UICONTROL 確認]**&#x200B;中，在&#x200B;**[!UICONTROL 輸入連線名稱]**&#x200B;中輸入連線名稱，然後選取&#x200B;**[!UICONTROL 刪除]**&#x200B;以刪除連線。 選取「**[!UICONTROL 取消]**」即可取消。

請參閱「[刪除影響](/help/technotes/deletion.md)」，了解有關刪除連線的詳細資訊。


### 建立連線的資料檢視

若要建立連線的資料檢視：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」。
1. 選取 ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 「建立新的資料檢視」]**。

或者，您可以：

1. 立即選取連線。

1. 從藍色動作列中選取![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立資料檢視]**。

如需詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)。

### Journey Optimizer連線

您可以在Customer Journey Analytics中使用Journey Optimizer連線，為連線帶來下列額外值：

* 在Customer Journey Analytics中執行Journey Optimizer資料的深入分析(使用Journey Optimizer中的&#x200B;**[!UICONTROL 在CJA中分析]**&#x200B;按鈕)。

  如需詳細資訊，請參閱Journey Optimizer檔案中的[在Customer Journey Analytics中分析](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/reporting/channel-report/report-cja-manage#cja-template)。

* 編輯Journey Optimizer連線和相關聯的資料檢視。

  如需有關編輯選項的詳細資訊，請參閱[編輯連線](#edit-a-connection)。


>[!IMPORTANT]
>
>當您啟用Journey Optimizer連線以與Customer Journey Analytics搭配使用時（如本節所述），連線中的每一列資料都會計入您每月的Customer Journey Analytics授權資料列，並顯示在連線使用UI中。 選取連線上的&#x200B;**[!UICONTROL 在CJA中使用]**&#x200B;選項，前提是您瞭解如何在Customer Journey Analytics中額外使用資料列。
>
>**如果您在2024年10月至2025年10月期間同時擁有Customer Journey Analytics和Journey Optimizer的許可權，請參閱下列有關[啟用AJO的連線](https://view.adobe.com/viewer/1ed94fc35c7860b260766c620889e7a0#1)**&#x200B;的檔案。

若要啟用此功能，您的組織需要存取Customer Journey Analytics。 如果您沒有存取權，請聯絡您的Adobe銷售代表。

#### 使用Journey Optimizer連線 {#use-connection-in-cja}

若要在Customer Journey Analytics中使用Journey Optimizer連線：

1. 找到您要與Customer Journey Analytics搭配使用的Journey Optimizer連線。

   1. 在![連線](/help/assets/icons/Filter.svg)索引標籤中選取&#x200B;**[!UICONTROL 篩選器]** **[!UICONTROL 篩選器]**。

   1. 在&#x200B;**[!UICONTROL 用於CJA]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 關閉]**。

      這會顯示目前未設定為可在Customer Journey Analytics中使用的所有Journey Optimizer連線。

      ![篩選以顯示未針對AJO啟用的連線](assets/remove-ajo-connection.png)

1. 選取Journey Optimizer連線的名稱。

1. 選取![使用者共用](/help/assets/icons/UseInCJA.svg) **[!UICONTROL 在CJA中使用]**。

   ![在CJA中使用按鈕](assets/connection-use-in-cja.png)

   **[!UICONTROL 在Customer Journey Analytics]**&#x200B;對話方塊中使用此連線。

1. 啟用切換，**[!UICONTROL 在CJA中使用連線]**。

1. 選取&#x200B;**[!UICONTROL 使用連線]**。<!-- double-check these dialog button names -->

#### 移除Journey Optimizer連線 {#remove-connection-in-cja}

您可以隨時從Customer Journey Analytics移除Journey Optimizer連線。 不過，在使用連線後從Customer Journey Analytics中移除連線會導致下列結果：

* Journey Optimizer連線和任何關聯的資料檢視都會重設為預設狀態，且無法再編輯

* 所有與連線相關聯的自訂衍生欄位都會被刪除。

* 您無法再在Customer Journey Analytics中對Journey Optimizer資料執行深入分析。

  這表示Journey Optimizer中的&#x200B;**[!UICONTROL 在CJA中分析]**&#x200B;按鈕已停用。

>[!IMPORTANT]
>
>Customer Journey Analytics中的連線計費包含移除連線的完整月份。


若要從Customer Journey Analytics移除連線：

1. 找到您要從Customer Journey Analytics移除的Journey Optimizer連線。

   1. 在![連線](/help/assets/icons/Filter.svg)索引標籤中選取&#x200B;**[!UICONTROL 篩選器]** **[!UICONTROL 篩選器]**。

   1. 在&#x200B;**[!UICONTROL 用於CJA]**&#x200B;區段中，選取&#x200B;**[!UICONTROL On]**。

      這會顯示目前設定為可在Customer Journey Analytics中使用的所有Journey Optimizer連線。

      ![篩選以顯示已啟用AJO的連線](assets/enabled-ajo-connection.png)

1. 若要檢視連線，請選取您要從Customer Journey Analytics移除的Journey Optimizer連線名稱。

1. 檢視Journey Optimizer連線時，請選取&#x200B;**[!UICONTROL 從CJA移除]**。

   **[!UICONTROL 從Customer Journey Analytics]**&#x200B;移除此連線對話方塊顯示：

   ![從CJA移除按鈕](assets/connection-remove-from-cja.png)

1. 停用選項&#x200B;**[!UICONTROL 從CJA移除連線]**。

1. 選取&#x200B;**[!UICONTROL 移除連線]**。

### 對應連線

若要檢視詳細說明連線中資料集間之關係的[連線圖](/help/connections/create-connection.md#connection-map)：

1. 選取連線名稱旁的「![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)」。
1. 選取「![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 連線圖]**」。

### 連線詳細資訊 {#connection-detail}

若要移至連線的詳細資訊，請在連線表格中選取超連結連線名稱。

![顯示小工具和設定的所有資料集視窗](assets/conn-details.png)

連線詳細資訊介面會提供連線狀態的詳細檢視。您可以：

* 檢查連線的資料集及攝取程序的狀態。
* 識別可以造成記錄被略過或被刪除的設定問題。
* 了解資料何時可用來報告。

| 使用者介面 | 說明 |
| --- | --- |
| ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯連線]**。 | 若要編輯連線的詳細資訊，請選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 「編輯連線」]**。如需詳細資訊，請參閱「[建立或編輯連線](create-connection.md)」。 |
| **[!UICONTROL *資料集選擇器&#x200B;*]** | 選取一個或多個資料集，以顯示連線中的詳細資料。 您無法多重選取資料集。 預設為「**[!UICONTROL 所有資料集]**」。 |
| **[!UICONTROL *日期範圍選擇器&#x200B;*]** | 選取要顯示連線中詳細資料的資料範圍。 編輯開始日期、結束日期，或選取「![行事曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)」，以開啟日期範圍選擇器。在日期範圍選擇器中，使用預先定義時間段之一 (例如&#x200B;**[!UICONTROL 過去 6 個月]**) 選取日期範圍，或使用行事曆來選取開始日期和結束日期。選取&#x200B;**[!UICONTROL 套用]**&#x200B;將新的日期範圍套用至連線詳細資料。 |
| **[!UICONTROL 有可用的事件資料記錄]** | 在&#x200B;**整個連線**&#x200B;中可用來報告的總事件資料集列數。 此計數與任何日期範圍或資料集選取範圍無關。 |
| [!UICONTROL **[!UICONTROL 量度]**] | 匯總新增、跳過和刪除的事件、查詢、設定檔和摘要資料集記錄以及新增的批次數。這些量度是根據&#x200B;**您選取的資料集和日期範圍**。<p>選取「**[!UICONTROL 檢查詳細資訊]**」，以顯示「**[!UICONTROL 查看略過的詳細資料]**」快顯視窗。快顯視窗列有所有事件資料集或選取資料集的略過記錄數和原因。<p>![略過的記錄](assets/skipped-records.png)<p>選取「![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」快顯視窗以取得更多資訊。由於某些略過的原因，例如[!UICONTROL 空白的訪客ID]，快顯視窗會顯示&#x200B;**[!UICONTROL EQS的範例PSQL]** (查詢服務的Experience Platform)，您可以在[查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home)中查詢資料集中略過的記錄。 選取 ![複製](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL 「複製 EQS 的範例 PSQL」]**&#x200B;以複製 SQL。 |
| **[!UICONTROL 新增的記錄]** | 此視覺效果可指出在選取的時段內新增了多少列，**代表您選取的資料集和日期範圍**。 每10分鐘更新一次。 |
| **[!UICONTROL 略過的記錄]** | 此視覺效果可指出在選取的時段內已略過多少列，**代表您選取的資料集和日期範圍**。 略過記錄的原因包括：遺漏時間戳記、遺漏或無效的個人ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}，等等。 每10分鐘更新一次。 <p>無效 ID (例如`undefined`、`00000000`，或[!UICONTROL 人員 ID] 在指定月份中出現超過 100 萬次的事件) 無法歸因於任何特定使用者或人員。這些資料列無法將攝取資料擷取至系統中，並導致容易出錯的攝取和報告。若要修正無效的人員ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}，您有3個選項：<ul><li>使用[拼接](/help/stitching/overview.md)以有效的使用者 ID 填入未定義或全零的使用者 ID。</li><li>將使用者ID留空，在擷取期間會略過這些ID （偏好使用無效或全零的使用者ID）。</li><li>在攝取資料之前，請先修正系統中任何無效的使用者 ID。</li></ul> |
| **[!UICONTROL 刪除的記錄]** | 此視覺效果可指出在選取的時段內刪除了多少列，**代表您選取的資料集和日期範圍**。 例如，可能有人已刪除 [!DNL Experience Platform] 中的資料集。 每10分鐘更新一次。<p>在某些情況下，該值還可以包括已取代的記錄，例如拼接或某些查詢資料集更新。考慮此範例：</p><ul><li>您將一筆記錄上傳到 XDM 設定檔資料集，Customer Journey Analytics 會將其設定為以設定檔查詢資料來攝取。在連線詳細資料中，該資料集將顯示已新增 1 筆記錄。</li><li>您將原始記錄的副本上傳到同一個 AEP 資料集，該資料集現在包含兩個記錄。Customer Journey Analytics 會從輪廓或帳戶 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 查詢資料集中攝取更多記錄。看到連線中已擷取該人員ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}的設定檔或帳戶記錄，Customer Journey Analytics會刪除其舊版，並新增設定檔資料。 在連線詳細資料中，此動作將代表1筆新增記錄和1筆刪除記錄，因為Customer Journey Analytics只會保留任何內嵌人員ID或帳戶ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}的最新設定檔查詢資料。</li><li>總體來說，AEP 資料集包含兩筆完全相同的記錄。另外，Customer Journey Analytics 連線詳細資料會顯示其攝取資料的狀態：此設定檔資料集新增了 2 筆記錄，刪除了 1 筆記錄。 </li></ul> |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | 資料集搜尋欄位。您可以依資料集名稱或資料集ID來搜尋資料集表格。 |
| [!UICONTROL 資料集表格] | 屬於連線之一部分的資料集。 請參閱下表以取得進一步說明。 選取![SelectBox](/help/assets/icons/SelectBox.svg)單一資料集以僅顯示所選資料集的連線詳細資料。 這等同於從&#x200B;**[!UICONTROL _資料集選取器_]**&#x200B;選取資料集。 |

資料集表格會顯示每個資料集的下列欄：

| 欄 | 說明 |
| --- | --- |
| **[!UICONTROL 資料集]** | 資料集的名稱。 您可以選取超連結，會在新分頁的 Experience Platform UI 中開啟資料集。您可以選取資料列或核取方塊，只顯示所選資料集的詳細資訊。 |
| **[!UICONTROL 資料集 ID]** | Experience Platform產生的資料集ID。 |
| **[!UICONTROL 新增的記錄]** | 在選取的日期範圍內新增到連線的資料集記錄（列）數。 |
| **[!UICONTROL 略過的記錄]** | 在選取的日期範圍內，針對連線在資料傳輸期間略過的資料集記錄（列）數。 |
| **[!UICONTROL 刪除的記錄]** | 在選取的日期範圍內，從連線中移除的資料集記錄（列）數。 |
| **[!UICONTROL 批次已新增]** | 在選取的日期範圍內已新增至連線的批次數量。 |
| **[!UICONTROL 上次新增時間]** | 已新增至連線的最新批次的時間戳記。 |
| **[!UICONTROL 資料來源類型]** | 來源型別。 當您將資料集新增到連線時，可以定義來源型別。 |
| **[!UICONTROL 資料集類型]** | [資料集型別](create-connection.md#dataset-types)。 型別可以是[!UICONTROL 事件]、[!UICONTROL 設定檔]、[!UICONTROL 查詢]或[!UICONTROL 摘要]。 |
| **[!UICONTROL 結構描述]** | 此資料集所根據的 Experience Platform 結構描述。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
| **[!UICONTROL 轉換資料]** | 適用 B2B 查詢資料集的轉換狀態。請參閱[轉換資料集以進行 B2B 查詢](transform-datasets-b2b-lookups.md)，了解更多資訊。<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，表示已啟用進行轉換的適用資料集， <p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，表示未啟用進行轉換的適用資料集，以及<p>**[!UICONTROL N/A]** 於所有其他資料集，不適用於轉換。 |
| **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _x _回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。 |

>[!IMPORTANT]
>
>2021 年 8 月 13 日之前攝取的任何資料，都不會反映在此[!UICONTROL 「連線」]介面中。
>

#### 連線面板

在資料集表格中未選取個別資料集時，右側面板會顯示連線選項和詳細資訊。

| 選項 | 說明 |
| --- | --- |
| ![重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 重新整理]** | 若要重新整理連線並允許反映最近新增的記錄，請選取 ![重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 「重新整理」]**。 |
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL 刪除]** | [刪除](#delete-a-connection)此連線。 |
| ![新增資料檢視](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 建立資料檢視]** | 根據此連線[建立資料檢視](#create-a-data-view)。請參閱「[資料檢視](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/data-views)」，了解更多資訊。 |
| 在CJA中&#x200B;**[!UICONTROL 使用]** | 在Customer Journey Analytics中使用Journey Optimizer連線，為您的Journey Optimizer連線帶來額外價值。 如需詳細資訊，請參閱[在Customer Journey Analytics中使用Journey Optimizer連線](#use-a-journey-optimizer-connection-in-customer-journey-analytics)。 |
| **[!UICONTROL 連線名稱]** | 連線的易記名稱。 |
| **[!UICONTROL 連線說明]** | 更詳細的說明，且可描述此連線的用途。 |
| **[!UICONTROL 沙箱]** | [Adobe Experience Platform 沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)，此連線會從這個沙箱提取其資料集 。 當您建立連線時，請選取此沙箱。 一旦儲存連線後，您就無法變更沙箱。 |
| **[!UICONTROL 連線 ID]** | 連線產生的識別碼。 您可以使用![複製](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)來複製值。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 主要ID型別&#x200B;]** | 連線的主要ID型別：以人員為基礎的連線為&#x200B;**[!UICONTROL 人員]**，以帳戶為基礎的連線為&#x200B;**[!UICONTROL 帳戶]**。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 容器&#x200B;]** | 連線的已設定容器。 |
| **[!UICONTROL 使用連線的資料檢視]** | 使用此連線的資料檢視。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，表示有多少資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，表示有多少個新資料集匯入已關閉。 |
| **[!UICONTROL 回填資料]** | 資料集回填資料的狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示所有資料集回填失敗的次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示所有資料集處理回填的次數，<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _回填完成]**，表示資料集回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若連線中的資料集未定義回填。 |
| **[!UICONTROL 轉換資料]** | 適用 B2B 查詢資料集的轉換狀態。請參閱[轉換資料集以進行 B2B 查詢](transform-datasets-b2b-lookups.md)，了解更多資訊。<p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，表示已啟用進行轉換的資料集數量。 |
| **[!UICONTROL 建立者]** | 建立連線的個人名稱。 |
| **[!UICONTROL 上次修改日期]** | 連接最後一次變更的時間戳。 |
| **[!UICONTROL 上次修改者]** | 上次修改連線的使用者名稱。 |

#### 資料集面板

在資料集表格中選取資料集列時，連線介面右側的面板會顯示所選取之資料集的詳細資訊。

| 詳細資料 | 說明 |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 全域帳戶 ID &#x200B;]** | 您指定為連線之全域帳戶ID的身分識別。 僅適用於已設定全域帳戶容器的帳戶型連線。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 帳戶 ID &#x200B;]** | 您指定為連線之帳戶ID的身分識別。 僅適用於未設定全域帳戶容器的帳戶型連線。 |
| **[!UICONTROL 人員 ID]** | 您指定為連線之人員ID的身分識別。 |
| **[!UICONTROL 索引鍵]** | 您為查詢資料集指定的索引鍵。 |
| **[!UICONTROL 比對索引鍵]** | 您為查詢資料集指定的比對索引鍵。 |
| **[!UICONTROL 時間戳記]** | 為事件資料集定義的時間戳記。 |
| **[!UICONTROL 可用記錄]** | 在透過行事曆選取的特定時段中，為此資料集攝取的資料列總數。 在新增資料後，資料會立即出現在報告中，不需要等候。 然而，當你建立全新連線時， 會有[延遲](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-faq)。 |
| **[!UICONTROL 新增的記錄]** | 在選取的日期範圍內新增到連線的資料集記錄（列）數。 |
| **[!UICONTROL 略過的記錄]** | 在選取的日期範圍內，針對連線在資料傳輸期間略過的資料集記錄（列）數。 |
| **[!UICONTROL 批次已新增]** | 已新增至連線的批次數量。 |
| **[!UICONTROL 刪除的記錄]** | 在選取的日期範圍內，從連線中移除的資料集記錄（列）數。 |
| **[!UICONTROL 上次新增時間]** | 已新增至連線的最新批次的時間戳記。 |
| **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
| **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _十&#x200B;_回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。<p>若要顯示含資料集過去回填概觀的對話框，請選取 <img src="./assets/pastbackfill.svg" alt="過去的回填" width="15"/> **[!UICONTROL 過去的回填]** |
| **[!UICONTROL 資料來源類型]** | 資料集新增至連線時所定義的資料來源型別。 |
| **[!UICONTROL 資料集類型]** | [資料集型別](create-connection.md#dataset-types)。 |
| **[!UICONTROL 結構描述]** | 此資料集所根據的 Adobe Experience Platform 結構描述。 |
| **[!UICONTROL 資料集 ID]** | Experience Platform中產生的資料集ID。 |


## 使用情況 {#connections-usage}

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="關鍵使用情況量度"
>abstract="提供核心和歷史可報告列數的每月資料和總資料。"

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="每月攝取列數"
>abstract="測量每月新增至系統的記錄總數，以提供對資料增長和攝取率的深入分析。"

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="每月可報告列數"
>abstract="追蹤可供報告的列數。可報告列數是指已攝取的列數減去攝取期間略過和刪除的列數。可報告列數是計費和資料使用情況的關鍵量度。"

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="詳細劃分"
>abstract="您可以依據連線、資料集、沙箱和標記來檢視詳細量度，並且可選擇下載資料的 CSV 檔案。"

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="其他資料集"
>abstract="2024 年 9 月之前的數月在資料集層級收集資料，且為了提高清晰度，該資料顯示為&#x200B;*其他資料集*。從 2024 年 9 月開始，會在精細資料集層級收集資料，*其他資料集*&#x200B;則不再顯示。"

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="未知的資料集或連線"
>abstract="未知的資料集或連線使用其 ID 顯示。"

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="資料無法使用"
>abstract="由於系統限制，無法取得 2024 年 9 月之前的歷史資料。從 2024 年 9 月起收集和顯示量度。此圖表會在時間軸上顯示過去 18 個月，且未來資料會在資料可用時顯示。"

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="核心可報告列數"
>abstract="當月過去13個月中可用的列總數，與上個月相比有百分比變更。  例如，在 2024 年 2 月 1 日，此數字顯示事件時間戳記從 2023 年 1 月到 2024 年 1 月的可用總列數。"

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="歷史可報告列數"
>abstract="當月超過13個月期間的可用列總數，與上個月相比有百分比變更。 例如，在 2024 年 2 月 1 日，此數字會顯示事件時間戳記早於 2023 年 1 月的可用總列數。"


>[!CONTEXTUALHELP]
>id="connections_averagerowsize"
>title="平均列大小"
>abstract="本月每個資料列擷取並儲存的平均儲存量（以kB為單位），與上個月相比有百分比變更。"


>[!CONTEXTUALHELP]
>id="connections_coredatavolume"
>title="核心資料量"
>abstract="儲存在磁碟上且附有當月時間戳記的資料總量 (以 TB 為單位)，以及相較於前一個月的變更百分比。"


>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="核心可報告列數"
>abstract="核心可報告列數是快照的值，而不是彙總總計。這些值會依所選日期範圍內的最後一個月進行動態更新。如果客戶選取 1 月至 3 月，則此值會反映 3 月的快照。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="歷史可報告列數"
>abstract="歷史可報告列數是快照的值，而不是彙總總計。這些值會依所選日期範圍內的最後一個月進行動態更新。如果客戶選取 1 月至 3 月，則此值會反映 3 月的快照。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="累計可報告列數"
>abstract="累計可報告列數是快照的值，而不是彙總總計。這些值會依所選日期範圍內的最後一個月進行動態更新。如果客戶選取 1 月至 3 月，則此值會反映 3 月的快照。"


[!UICONTROL 使用情況]介面是顯示所有連線中攝取和可報告的行的使用情況。如果未選取，請選取「**[!UICONTROL 使用情況]**」標記以存取介面。

此介面可幫助您確定 Customer Journey Analytics 使用情況是否與合約的協議相符。除了監控目的之外，您還可以使用「使用情況」介面來規劃 Customer Journey Analytics 許可證續約。

「使用情況」介面會使用下列量度：

| 量度名稱 | 說明 |
|---|---|
| **歷史可報告資料列** | 超過 13 個月的時間段的資料列計數。 |
| **核心可報告資料列** | 過去 13 個月的資料列計數。 |
| **核心資料磁碟區** | 儲存在磁碟上的資料總量。 |
| **平均資料列大小** | 擷取和儲存的每一列資料使用的平均儲存數量。 |
| **攝取的資料列數** | 特定時期內攝取多少資料列。 |
| **可報告的資料列數** | 在特定時期內，作為連線一部分會有多少資料列？ |
| **累計資料列** | 截至特定月份已攝取多少資料列。 |

>[!NOTE]
>
>從 2024 年 7 月開始，收集核心、歷史和總計記錄的資料。請聯絡您的客戶經理以取得早期的歷史資料。
>

「使用情況」介面由兩個面板組成：

* 顯示的&#x200B;**[!UICONTROL 金鑰使用量度]**&#x200B;面板：

   * 四個摘要視覺效果顯示上個月的總數和百分位數變化：

      * **[!UICONTROL 可報告的核心資料列]**。 當月過去13個月中可用的列總數，與上個月相比有百分比變更。 例如，在 2024 年 2 月 1 日，此數字顯示事件時間戳記從 2023 年 1 月到 2024 年 1 月的可用總列數。
      * **[!UICONTROL 歷史資料可報告資料列]**。 當月超過13個月期間的可用列總數，與上個月相比有百分比變更。 例如，在 2024 年 2 月 1 日，此數字會顯示事件時間戳記早於 2023 年 1 月的可用總列數。
      * **[!UICONTROL 核心資料磁碟區]**。 儲存在磁碟上且附有當月時間戳記的資料總量 (以 TB 為單位)，以及相較於前一個月的變更百分比。
      * **[!UICONTROL 平均資料列大小]**。 本月每個資料列擷取並儲存的平均儲存量（以kB為單位），與上個月相比有百分比變更。

   * 顯示過去13個月&#x200B;**[!UICONTROL 核心與歷史資料可報告列]**&#x200B;的棧疊垂直長條圖視覺效果。

     當您將滑鼠游標停留在視覺效果中的任何棧疊長條圖上時，快顯視窗會顯示該長條圖特定部分的列數。 在以下範例中，核心資料可報告列顯示為當月(2025年8月： 936M (936,347,325))。


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

  2024 年 9 月之前的數月在資料集層級收集資料，且為了提高清晰度，該資料顯示為「[!UICONTROL 其他資料集]」。從2024年9月開始，資料會在精細資料集層級收集，而[!UICONTROL 其他資料集]將不再出現。

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
>&#x200B;>[管理您的 Customer Journey Analytics 使用情況](/help/technotes/estimate-usage.md)
>
