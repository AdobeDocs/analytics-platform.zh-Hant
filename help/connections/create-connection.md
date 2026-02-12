---
title: 建立或編輯連線
description: 瞭解如何在Customer Journey Analytics中建立或編輯與Experience Platform資料集的連線。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 96cbb15193c67a700f1373a3cfa75e711fa070b8
workflow-type: tm+mt
source-wordcount: '8781'
ht-degree: 98%

---

# 建立或編輯連線 {#create-or-edit-a-connection}

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="新增的記錄"
>abstract="所選資料集在所選的時間間隔中新增至連線的記錄 (列) 數。"

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="略過的記錄"
>abstract="所選資料集在所選的時間間隔中於連線的資料傳輸期間略過的記錄 (列) 數。"

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="刪除的記錄"
>abstract="選取的資料集在選取的時間間隔內從連線中移除的記錄 (列) 數。"

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="上次新增時間"
>abstract="從任何資料集中傳輸至連線的最後批次的時間戳記。"

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="啟用滾動式資料時間範圍"
>abstract="在連線層級將資料保留定義為以月為單位的滾動時間範圍。"

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="平均每日使用數"
>abstract="選取整個連線的預期每日事件數範圍。"

>[!CONTEXTUALHELP]
>id="connections_recordsadded"
>title="新增的記錄"
>abstract="所選資料集在所選的時間間隔中新增至連線的記錄 (列) 數。"

>[!CONTEXTUALHELP]
>id="connections_recordsskipped"
>title="略過的記錄"
>abstract="所選資料集在所選的時間間隔中於連線的資料傳輸期間略過的記錄 (列) 數。"

>[!CONTEXTUALHELP]
>id="connections_recordsdeleted"
>title="刪除的記錄"
>abstract="所選資料集在所選的時間間隔內從連線中移除的記錄 (列) 數"

>[!CONTEXTUALHELP]
>id="connection_lastadded"
>title="上次新增時間"
>abstract="從任何資料集中傳輸至連線的最後批次的時間戳記。"

>[!CONTEXTUALHELP]
>id="connection_enablerollingdatawindow"
>title="啟用滾動式資料時間範圍"
>abstract="在連線層級將資料保留定義為以月為單位的滾動時間範圍。"

>[!CONTEXTUALHELP]
>id="connection_averagenumberofdailyuses"
>title="平均每日使用數"
>abstract="選取整個連線的預期每日事件數範圍。"

>[!CONTEXTUALHELP]
>id="connection_change_personid"
>title="變更身分設定 "
>abstract="一旦您在「連線」介面中儲存修改專案，身分設定的變更將會刪除此資料集的連線資料。 您必須根據新設定，從資料集中重新內嵌資料。<br/><br/>在刪除程式完成之前，報告可能會延遲。"

>[!CONTEXTUALHELP]
>id="connection_change_accountid"
>title="變更帳戶 ID"
>abstract="變更帳戶 ID 會刪除連線中所有現有資料，並根據新的帳戶 ID 重新收錄資料集中所有資料。這個動作可能會產生成本支出。<br/><br/>當您選擇「**[!UICONTROL 繼續]**」時，報告可能會延遲，直到該程序完成為止。"

>[!CONTEXTUALHELP]
>id="connection_change_globalaccountid"
>title="變更全域帳戶 ID"
>abstract="變更全域帳戶 ID 會刪除連線中所有現有資料，並根據新的全域帳戶 ID 重新收錄資料集中所有資料。這個動作可能會產生成本支出。<br/><br/>當您選擇「**[!UICONTROL 繼續]**」時，報告可能會延遲，直到該程序完成為止。"

>[!CONTEXTUALHELP]
>id="connection_change_opportunityid"
>title="變更機會 ID"
>abstract="變更機會 ID 會刪除連線中所有現有資料，並根據新的機會 ID 重新收錄資料集中所有資料。這個動作可能會產生成本支出。<br/><br/>當您選擇「**[!UICONTROL 繼續]**」時，報告可能會延遲，直到該程序完成為止。"

>[!CONTEXTUALHELP]
>id="connection_change_buyinggroupid"
>title="變更購買群組 ID"
>abstract="變更購買群組 ID 會刪除連線中所有現有資料，並根據新的購買群組 ID 重新收錄資料集中所有資料。這個動作可能會產生成本支出。<br/><br/>當您選擇「**[!UICONTROL 繼續]**」時，報告可能會延遲，直到該程序完成為止。"

>[!CONTEXTUALHELP]
>id="connection_change_persistentid"
>title="變更永久 ID"
>abstract="變更永久 ID 會刪除連線中所有現有資料，並根據新的永久 ID 重新收錄資料集中所有資料。這個動作可能會產生成本支出。<br/><br/>當您選擇「**[!UICONTROL 繼續]**」時，報告可能會延遲，直到該程序完成為止。"


<!-- Start of contextual help entries for CJA connection dialogs -->

>[!CONTEXTUALHELP]
>id="connections_useincja_exl_ajo"
>title="在 Customer Journey Analytics 中使用此連線"
>abstract="此選項可讓您搭配 Journey Optimizer 連線利用 Customer Journey Analytics 的進階報告功能。這些功能可以：<ul><li>在 Customer Journey Analytics 中執行 Journey Optimizer 資料的深入分析。</li><li>編輯 Journey Optimizer 連線和相關的資料視圖。</li><li>分析歷程事件、對話路徑和行銷活動績效。</li></ul>**啟用此選項後，連線中的每一列資料都會計入您每個月的 Customer Journey Analytics 授權資料列，並出現在「連線使用情況」使用者介面中。**<br><br/>&#x200B;只有在您熟悉 Customer Journey Analytics 中資料列的其他使用方式時，才能探索此選項。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/integrations/ajo){target="_blank"}。"

>[!CONTEXTUALHELP]
>id="connections_disableuseincja_exl_ajo"
>title="從 Customer Journey Analytics 中移除此連線"
>abstract="此 Journey Optimizer 連線目前正在 Customer Journey Analytics 中使用。您可以透過連線進行以下作業：<ul><li>在 Customer Journey Analytics 中執行 Journey Optimizer 資料的深入分析。</li><li>編輯 Journey Optimizer 連線和相關的資料視圖。</li><li>分析歷程事件、對話路徑和行銷活動績效。</li></ul>**如果您移除連線，就無法再於 Customer Journey Analytics 中進行深入分析。連線和任何關聯的資料視圖都會重設為預設狀態，且無法再編輯。**<br/><br/>**Customer Journey Analytics 中此連線的計費包括移除連線的整個月份。**<br/><br/>&#x200B;連線在 Journey Optimizer 中保持啟用狀態。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/integrations/ajo){target="_blank"}。"

>[!CONTEXTUALHELP]
>id="connections_useincja_exl_brand_concierge"
>title="在 Customer Journey Analytics 中使用此連線"
>abstract="透過此選項，您可以搭配 Brand Concierge 連線使用 Customer Journey Analytics 的進階報告功能。這些功能可讓您：<ul><li>在 Customer Journey Analytics 中執行 Brand Concierge 資料的深入分析。</li><li>編輯 Brand Concierge 連線及相關資料視圖。</li><li>分析對話式參與度、情緒和轉換量度。</li></ul>**啟用此選項後，連線中的每一列資料都會計入您每個月的 Customer Journey Analytics 授權資料列，並出現在「連線使用情況」使用者介面中。**<br><br/>&#x200B;只有在您熟悉 Customer Journey Analytics 中資料列的其他使用方式時，才能探索此選項。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/templates/use-templates#brand-concierge-templates){target="_blank"}。"

>[!CONTEXTUALHELP]
>id="connections_disableuseincja_exl_brand_concierge"
>title="從 Customer Journey Analytics 中移除此連線"
>abstract="此 Brand Concierge 連線目前用於 Customer Journey Analytics。您可以透過連線進行以下作業：<ul><li>在 Customer Journey Analytics 中執行 Brand Concierge 資料的深入分析。</li><li>編輯 Brand Concierge 連線及相關資料視圖。</li><li>分析對話式參與度、情緒和轉換量度。</li></ul>**如果您移除連線，就無法再於 Customer Journey Analytics 中進行深入分析。連線和任何關聯的資料視圖都會重設為預設狀態，且無法再編輯。**<br/><br/>**Customer Journey Analytics 中此連線的計費包括移除連線的整個月份。**<br/><br/>&#x200B;連線在 Brand Concierge 中保持啟用狀態。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/templates/use-templates#brand-concierge-templates){target="_blank"}。"

>[!CONTEXTUALHELP]
>id="connections_useincja_exl_product_usage"
>title="在 Customer Journey Analytics 中使用此連線"
>abstract="透過此選項，您可以搭配產品使用情況連線使用 Customer Journey Analytics 的進階報告功能。這些功能可讓您：<ul><li>在 Customer Journey Analytics 中執行產品使用情況資料的深入分析。</li><li>編輯產品使用情況連線和相關的資料視圖。</li></ul>**啟用此選項後，連線中的每一列資料都會計入您每個月的 Customer Journey Analytics 授權資料列，並出現在「連線使用情況」使用者介面中。**<br><br/>&#x200B;只有在您熟悉 Customer Journey Analytics 中資料列的其他使用方式時，才能探索此選項。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/tools/product-usage/usage-overview){target="_blank"}。"

>[!CONTEXTUALHELP]
>id="connections_disableuseincja_exl_product_usage"
>title="從 Customer Journey Analytics 中移除此連線"
>abstract="此產品使用情況連線目前用於 Customer Journey Analytics。您可以透過連線進行以下作業：<ul><li>在 Customer Journey Analytics 中執行產品使用情況資料的深入分析。</li><li>編輯產品使用情況連線和相關的資料視圖。</li></ul>**如果您移除連線，就無法再於 Customer Journey Analytics 中進行深入分析。連線和任何關聯的資料視圖都會重設為預設狀態，且無法再編輯。**<br/><br/>**Customer Journey Analytics 中此連線的計費包括移除連線的整個月份。**<br/><br/>&#x200B;產品使用情況的連線保持啟用狀態。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/tools/product-usage/usage-overview){target="_blank"}。"

>[!CONTEXTUALHELP]
>id="connections_useincja_legal_section_section"
>title="法律影響"
>abstract="使用 Customer Journey Analytics 可能會產生依整合資料量計算的額外費用。請參閱[關於 Customer Journey Analytics 計費和使用情況的詳細資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage)"


>[!CONTEXTUALHELP]
>id="connections_useincja_exl_ajo_learn_more"
>title="了解更多"
>abstract="[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage)。"

>[!CONTEXTUALHELP]
>id="connections_useincja_exl_brand_concierge_learn_more"
>title="了解更多"
>abstract="[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/templates/use-templates#brand-concierge-templates)。"

>[!CONTEXTUALHELP]
>id="connections_useincja_exl_product_usage_learn_more"
>title="了解更多"
>abstract="[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/tools/product-usage/usage-overview)。"

<!-- End of contextual help entries for CJA connection dialogs -->


透過輔助工作流程，建立連線和編輯工作流程體驗可將所有資料集和連線組態設定彙整到畫面中央處。它提供詳細的資料集選擇、設定和審閱體驗。可讓您指定[資料集類型](#dataset-types)、大小、結構描述、資料集 ID、批次狀態、回填狀態、身分識別等重要資訊，以降低連線設定錯誤的風險。以下是功能概觀：

* 當您建立連線時，可以啟用滾動資料保留時間窗口。
* 您可以在連線中新增及移除資料集。 (移除資料集會將其從連線中移除，並影響任何關聯的資料檢視及基礎 Analysis Workspace 專案。)
* 您可以為每個資料集啟用及請求回填資料。
* 例如，您可以編輯資料集來請求另一次回填。
* 您可以為每個資料集匯入現有的資料。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [建立並編輯連線](https://video.tv.adobe.com/v/343044/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


## 先決條件

您可以新增至連線的最大資料集數量上限為 100。該組合取決於您公司購買的 Customer Journey Analytics 套件。

如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

| **選取**&#x200B;套件 | **基礎**&#x200B;套件 |
| --- | --- |
| 事件、設定檔、查詢或摘要資料集的任何組合，總計最多 100 個 | 每個連線一個事件資料集 |
|  | 每個連線最多 99 個輪廓、查詢或摘要資料集 |

{style="table-layout:auto"}

## 建立連線 {#create-connection}

若要建立連線：

1. 在 Customer Journey Analytics 的頂部選單中選取「**[!UICONTROL 連線]**」，也可以自「**[!UICONTROL 資料管理]**」選取。
1. 選取「**[!UICONTROL 建立新連線]**」。

您現在可以[編輯連線的詳細資料](#edit-a-connection)。

## 編輯連線 {#edit-connection}

編輯連線的方式取決於您已授權的 Customer Journey Analytics 封裝：

* [Customer Journey Analytics](#customer-journey-analytics)
* [Customer Journey Analytics B2B Edition](#customer-journey-analytics-b2b-edition)

### Customer Journey Analytics

在「**[!UICONTROL 連線]**」>「**[!UICONTROL *連線名稱&#x200B;*]**」畫面中：

![無標題連線設定](assets/create-conn1.png)

1. 進行連線設定。

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 連線名稱]** | 為連線輸入唯一名稱。 |
   | **[!UICONTROL 連線說明]** | 說明此連線的用途。 |
   | **[!UICONTROL 標記]** | 指定標記，將標記新增至您的連線，讓您稍後可以使用這些標記來搜尋連線。 |
   | **[!UICONTROL 啟用滾動式資料時間範圍]** | 勾選這個核取方塊可讓您在連線層級將 Customer Journey Analytics 資料保留定義為以月為單位的滾動時段 (1 個月、3 個月、6 個月等)。<p>資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此輪廓或查詢資料集不存在滾動資料時間窗口設定。不過，如果您的連線在一個或多個事件資料集之外還包含任何輪廓或查詢資料集，則會為相同時段保留該資料。<p> 主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。<p><ul><li>如果您保留預設值 (未勾選)，Adobe Experience Platform 資料保留設定將取代保留期間。如果您在 Experience Platform 中有 25 個月的資料，Customer Journey Analytics 會透過回填取得 25 個月的資料。如果您在 Experience Platform 中刪除其中 10 個月的資料，Customer Journey Analytics 則會保留剩餘 15 個月的資料。</li><li>如果您啟用滾動式資料時間範圍，請在「**[!UICONTROL 選取月份數量]**」中指定您啟用滾動式資料時間範圍的月份數量。 |
   | **[!UICONTROL 沙箱]** | 在 Experience Platform 中，選擇包含您要建立連線的資料集的沙箱。<p>Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)可將單一 Platform 實例分割成不同的虛擬環境，以利開發及改進數位體驗應用程式。您可將沙箱視為內含資料集的「資料獨立單位」。沙箱可用於控制資料集的存取權限。<p>當您選取沙箱後，左側邊欄會顯示您可以從該沙箱提取的所有資料集。 |
   | **[!UICONTROL 新增資料集]** | 選取「![資料新增](/help/assets/icons/DataAdd.svg)**[!UICONTROL 新增資料集]**」以新增資料集。如果連線尚未有資料集，您也可以在資料集表格中選取「**[!UICONTROL 新增資料集]**」。 |


   對於您已設定過的資料集，資料集表格會顯示以下欄位：

   | 欄 | 說明 |
   |---|---|
   | **[!UICONTROL 資料集名稱]** | 選取一個或多個要拉進 Customer Journey Analytics 中的資料集，然後選取「**[!UICONTROL 新增]**」。<p>(如果有很多資料集可選擇，可使用資料集清單上方的「搜尋資料集」搜尋列，搜尋合適的資料集)。 |
   | ![更多](/help/assets/icons/More.svg) | 選取「![更多](/help/assets/icons/More.svg)」開啟所選資料集的內容功能表。根據資料集 (的類型)，您可以選取：<ul><li>「![交叉大小75](/help/assets/icons/CrossSize400.svg) **[!UICONTROL 刪除資料集]**」以[刪除資料集](#delete-a-dataset)。</li><li>「![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料集]**」以[編輯資料集](#edit-a-dataset)。</li><li>「![歷史記錄](/help/assets/icons/History.svg) **[!UICONTROL 過去的回填]**」以顯示資料集[過去回填的資料](#past-backfills)。 |
   | **[!UICONTROL 上次更新時間]** | 僅適用於事件資料集，系統會自動將此設定設為 Experience Platform 中以事件為基礎的結構描述中的預設時間戳記欄位。 「不適用」代表此資料集不含任何資料。 |
   | **[!UICONTROL 記錄數量]** | Experience Platform 中資料集的上個月記錄總數。 |
   | **[!UICONTROL 結構描述]** | 在 Adobe Experience Platform 中建立資料集所根據的[結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition)。 |
   | **[!UICONTROL 資料集類型]** | Customer Journey Analytics 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定[資料集類型](#dataset-types)。有 3 種不同的資料集類型：事件資料、輪廓資料和查詢資料。 請參閱下表提供的資料集類型說明。 |
   | **[!UICONTROL 拼接]** | 如果資料集[在「連線」使用者介面中啟用了拼接功能](/help/stitching/use-stitching-ui.md)，則該值為&#x200B;**[!UICONTROL 真]**；否則，該值為&#x200B;**[!UICONTROL 假]**。透過[請求拼接程序](/help/stitching//use-stitching.md)所產生的拼接資料集不會在此表格中被識別為已拼接，且其值預設為&#x200B;**[!UICONTROL 假]**。 |
   | **[!UICONTROL 顆粒度]** | 資料集中資料的顆粒度；僅適用於摘要資料集。 |
   | **[!UICONTROL 資料來源類型]** | 資料集的資料來源類型。不適用於摘要資料集。 |
   | **[!UICONTROL 個人 ID]** | 用於支援資料集人員式報告的個人 ID。 |
   | **[!UICONTROL 索引鍵]** | 用於查詢資料集的索引鍵。 |
   | **[!UICONTROL 比對索引鍵]** | 用於查詢資料集的比對索引鍵。 |
   | **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
   | **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _十&#x200B;_回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。 |

   您可以使用「![搜尋](/help/assets/icons/Search.svg)」欄位搜尋特定資料集。

### Customer Journey Analytics B2B Edition

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

在「**[!UICONTROL 連線]**」>「**[!UICONTROL *連線名稱&#x200B;*]**」畫面中：

![無標題連線設定](assets/create-conn1-b2b.png)

1. 進行連線設定。

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 連線名稱]** | 為連線輸入唯一名稱。 |
   | **[!UICONTROL 連線說明]** | 說明此連線的用途。 |
   | **[!UICONTROL 標記]** | 指定標記，將標記新增至您的連線，讓您稍後可以使用這些標記來搜尋連線。 |
   | **[!UICONTROL 主要 ID]** | 為您的連線選取正確的主要 ID： <ul><li>「![使用者](/help/assets/icons/User.svg) **[!UICONTROL 個人]**」，適用於您通常在 B2C 情境中使用的個人型連線。</li><li> 「![建築物](/help/assets/icons/Building.svg) **[!UICONTROL 帳戶]**」，適用於您通常在 B2B 情境中使用的帳戶型連線。</li></ul>新增一個或多個資料集至連線後，您就無法再變更主要 ID。<br/>選取的主要 ID 會定義連線是個人型或帳戶型。特定資料集類型可用的[設定](#dataset-settings)取決於連線基礎。 |
   | **[!UICONTROL 選用容器]** | 如果您已選取「![建築物](/help/assets/icons/Building.svg) **[!UICONTROL 帳戶]**」做為「**[!UICONTROL 主要 ID]**」，請選取其他容器。<ul><li>**[!UICONTROL 全域帳戶]**：可以設定在連線中的全域帳戶。</li><li>**[!UICONTROL 機會]**：可以設定在連線中的機會。</li><li>**[!UICONTROL 購買群組]**：可以設定在連線中的購買群組。</li><ul> |
   | **[!UICONTROL 沙箱]** | 在 Experience Platform 中，選擇包含您要建立連線的資料集的沙箱。<p>Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)可將單一 Platform 實例分割成不同的虛擬環境，以利開發及改進數位體驗應用程式。您可將沙箱視為內含資料集的「資料獨立單位」。沙箱可用於控制資料集的存取權限。<p>當您選取沙箱後，左側邊欄會顯示您可以從該沙箱提取的所有資料集。 |
   | **[!UICONTROL 啟用滾動式資料時間範圍]** | 勾選這個核取方塊可讓您在連線層級將 Customer Journey Analytics 資料保留定義為以月為單位的滾動時段 (1 個月、3 個月、6 個月等)。<p>資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此輪廓或查詢資料集不存在滾動資料時間窗口設定。不過，如果您的連線在一個或多個事件資料集之外還包含任何輪廓或查詢資料集，則會為相同時段保留該資料。<p> 主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。<p><ul><li>如果您保留預設值 (未勾選)，Adobe Experience Platform 資料保留設定將取代保留期間。如果您在 Experience Platform 中有 25 個月的資料，Customer Journey Analytics 會透過回填取得 25 個月的資料。如果您在 Platform 中刪除其中 10 個月的資料，Customer Journey Analytics 則會保留剩餘 15 個月的資料。</li><li>如果您啟用滾動式資料時間範圍，請在「**[!UICONTROL 選取月份數量]**」中指定您啟用滾動式資料時間範圍的月份數量。 |
   | **[!UICONTROL 新增資料集]** | 選取「![資料新增](/help/assets/icons/DataAdd.svg) **[!UICONTROL 新增資料集]**」以[新增資料集](#add-datasets)。如果連線尚未有資料集，您也可以在資料集表格中選取「**[!UICONTROL 新增資料集]**」。 |


   對於您已設定過的資料集，資料集表格會顯示以下欄位：

   | 欄 | 說明 |
   |---|---|
   | **[!UICONTROL 資料集名稱]** | 選取一個或多個要拉進 Customer Journey Analytics 中的資料集，然後選取「**[!UICONTROL 新增]**」。<p>(如果有很多資料集可選擇，可使用資料集清單上方的「搜尋資料集」搜尋列，搜尋合適的資料集)。 |
   | ![更多](/help/assets/icons/More.svg) | 選取「![更多](/help/assets/icons/More.svg)」開啟所選資料集的內容功能表。根據資料集 (的類型)，您可以選取：<ul><li>「![交叉大小75](/help/assets/icons/CrossSize400.svg) **[!UICONTROL 刪除資料集]**」以[刪除資料集](#delete-a-dataset)。</li><li>「![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料集]**」以[編輯資料集](#edit-a-dataset)。</li><li>「![歷史記錄](/help/assets/icons/History.svg) **[!UICONTROL 過去的回填]**」以顯示資料集[過去回填的資料](#past-backfills)。 |
   | **[!UICONTROL 上次更新時間]** | 僅適用於事件資料集，系統會自動將此設定設為 Experience Platform 中以事件為基礎的結構描述中的預設時間戳記欄位。 「不適用」代表此資料集不含任何資料。 |
   | **[!UICONTROL 記錄數量]** | Experience Platform 中資料集的上個月記錄總數。 |
   | **[!UICONTROL 結構描述]** | 在 Adobe Experience Platform 中建立資料集所根據的[結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition)。 |
   | **[!UICONTROL 資料集類型]** | Customer Journey Analytics 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定[資料集類型](#dataset-types)。 |
   | **[!UICONTROL 顆粒度]** | 資料集中資料的顆粒度；僅適用於摘要資料集。 |
   | **[!UICONTROL 資料來源類型]** | 資料集的資料來源類型。不適用於摘要資料集。 |
   | **[!UICONTROL 帳戶 ID]** | (僅於帳戶型連線顯示) 用於支援資料集之帳戶型報告的帳戶 ID。 |
   | **[!UICONTROL 全域帳戶 ID]** | (僅於帳戶型連線顯示) 用於支援資料集之帳戶型報告的全域帳戶 ID。 |
   | **[!UICONTROL 購買群組 ID]** | (僅於帳戶型連線顯示) 用於尋找購買群組資料的購買群組 ID。 |
   | **[!UICONTROL 機會 ID]** | (僅於帳戶型連線顯示) 用於查詢機會資料的機會 ID。 |
   | **[!UICONTROL 個人 ID]** | 用於支援資料集人員式報告的個人 ID。 |
   | **[!UICONTROL 索引鍵]** | 用於查詢資料集的索引鍵。 |
   | **[!UICONTROL 比對索引鍵]** | 用於查詢資料集的比對索引鍵。 |
   | **[!UICONTROL 匯入新資料]** | 資料集匯入新資料的狀態： <p>![綠色狀態](assets/status-green.svg)   **[!UICONTROL _x _開啟]**，若資料集設定為匯入新資料，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _x 關閉_]**，若資料集設定為不匯入新資料。 |
   | **[!UICONTROL 回填資料]** | 資料集的回填資料狀態。<p>![紅色狀態](assets/status-red.svg)   **[!UICONTROL _x _回填失敗]**，表示回填失敗次數，<p>![紅色狀態](assets/status-orange.svg)   **[!UICONTROL _x _回填處理]**，表示處理回填的數量，<p>![狀態綠色](assets/status-green.svg)   **[!UICONTROL _十&#x200B;_回填完成]**，表示回填已完成的數量，以及<p>![灰色狀態](assets/status-gray.svg)   **[!UICONTROL _關閉_]**，若未設定為回填。 |

   您可以使用「![搜尋](/help/assets/icons/Search.svg)」欄位搜尋特定資料集。

## 資料集 {#datasets}

您在連線工作流程中會[新增一個或多個資料集](#add-datasets)或[編輯現有的資料集](#edit-a-dataset)。

>[!NOTE]
>
>在任何資料集類型的資料列中，日期與日期時間欄位為 1900 年之前的值，會在攝取資料列之前取代為值 `null`。<br/>在事件或摘要資料集中的列，若其時間戳記值是在 1900 年之前，則不會攝取這些列。


{{relational-model-based}}


>[!CONTEXTUALHELP]
>id="cja_connection_primaryid"
>title="主要 ID"
>abstract="為您的連線選取正確的主要 ID：B2C 情境的人員。B2B 情境適用的帳戶。"

>[!CONTEXTUALHELP]
>id="cja_connection_optionalcontainers"
>title="選用容器"
>abstract="選取其他容器。<br/><br/>**[!UICONTROL 全域帳戶&#x200B;]**：可以設定在連線中的全域帳戶。<br/>**[!UICONTROL 機會]**：可以設定在連線中的機會。<br/>**[!UICONTROL 購買群組&#x200B;]**：可以設定在連線中的購買群組。"

>[!CONTEXTUALHELP]
>id="cja_connection_accountid"
>title="帳戶 ID"
>abstract="從 Experience Platform 資料集結構描述中已定義之可用身分識別當中，選取一個帳戶 ID (帳戶的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="cja_connection_accountfield"
>title="帳戶欄位"
>abstract="選取代表帳戶 ID (帳戶的唯一識別碼) 的欄位。"

>[!CONTEXTUALHELP]
>id="cja_connection_globalaccountid"
>title="全域帳戶 ID"
>abstract="從您在 Experience Platform 的資料集結構描述中定義的可用身分識別中，選取全域帳戶 ID (全域帳戶的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityid"
>title="機會 ID"
>abstract="從您在 Experience Platform 的資料集結構描述中定義的可用身分識別中，選取機會 ID (機會的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="cja_connection_buyinggroupid"
>title="購買群組 ID"
>abstract="從您在 Experience Platform 的資料集結構描述中定義的可用身分識別中，選取購買群組 ID (購買群組的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="cja_connection_personid"
>title="個人 ID"
>abstract="從您在 Experience Platform 資料集結構描述中所定義的可用身分識別中，選取一個個人 ID (人員的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="比對索引鍵"
>abstract="選取要加入其中一個事件資料集的欄位。若此清單空白，您可能尚未新增或設定事件資料集。"

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="匯入新資料"
>abstract="在 Experience Platform 資料集中新增的任何新批次均會自動新增至此連線中，而且可供分析使用。"

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="資料集回填"
>abstract="此選項會從此連線中資料集的 Experience Platform 回填現有 (歷史) 資料。"

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="轉換資料集"
>abstract="此選項將轉換資料集，使其可用於在 B2B 情境中進行人員型查詢。一旦開啟，資料集的轉換便無法復原。"

>[!CONTEXTUALHELP]
>id="cja_connection_connectionmap"
>title="連接圖"
>abstract="連接圖會以視覺化方式顯示事件、人員、帳戶和相關查詢資料集 (如機會、行銷活動成員等) 之間的關係。"

>[!CONTEXTUALHELP]
>id="connection_primaryid"
>title="主要 ID"
>abstract="為您的連線選取正確的主要 ID：B2C 情境的人員。B2B 情境適用的帳戶。"

>[!CONTEXTUALHELP]
>id="connection_optionalcontainers"
>title="選用容器"
>abstract="選取其他容器。<br/><br/>**[!UICONTROL 全域帳戶&#x200B;]**：可以設定在連線中的全域帳戶。<br/>**[!UICONTROL 機會]**：可以設定在連線中的機會。<br/>**[!UICONTROL 購買群組&#x200B;]**：可以設定在連線中的購買群組。"

>[!CONTEXTUALHELP]
>id="connection_personid"
>title="個人 ID"
>abstract="在 Experience Platform 中，從資料集結構描述中所定義的可用身分識別中選取個人 ID。"

>[!CONTEXTUALHELP]
>id="connection_accountid"
>title="帳戶 ID"
>abstract="從 Experience Platform 資料集結構描述中已定義之可用身分識別當中，選取一個帳戶 ID (帳戶的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="connection_accountfield"
>title="帳戶欄位"
>abstract="選取代表帳戶 ID (帳戶的唯一識別碼) 的欄位。"

>[!CONTEXTUALHELP]
>id="connection_globalaccountid"
>title="全域帳戶 ID"
>abstract="從您在 Experience Platform 的資料集結構描述中定義的可用身分識別中，選取全域帳戶 ID (全域帳戶的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="connection_opportunityid"
>title="機會 ID"
>abstract="從您在 Experience Platform 的資料集結構描述中定義的可用身分識別中，選取機會 ID (機會的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="connection_buyinggroupid"
>title="購買群組 ID"
>abstract="從您在 Experience Platform 的資料集結構描述中定義的可用身分識別中，選取購買群組 ID (購買群組的唯一識別碼)。"

>[!CONTEXTUALHELP]
>id="connection_matchingkey"
>title="比對索引鍵"
>abstract="選取要加入其中一個事件資料集的欄位。若此清單空白，您可能尚未新增或設定事件資料集。"

>[!CONTEXTUALHELP]
>id="connection_matchingkeytype"
>title="比對索引鍵類型"
>abstract="選取連結方式：根據依欄位比對或依容器比對。<br/><br/>**[!UICONTROL 依欄位比對&#x200B;]**：選取一個欄位，與其中一個事件資料集進行連結。若此清單空白，您可能尚未新增或設定事件資料集。<br/>**[!UICONTROL 依容器比對]**：選取要與其中一個事件資料集連結的容器。"

>[!CONTEXTUALHELP]
>id="connection_importnewdata"
>title="匯入新資料"
>abstract="在 Experience Platform 資料集中新增的任何新批次均會自動新增至此連線中，而且可供分析使用。"

>[!CONTEXTUALHELP]
>id="connection_datasetbackfill"
>title="資料集回填"
>abstract="此選項會從此連線中資料集的 Experience Platform 回填現有 (歷史) 資料。"

>[!CONTEXTUALHELP]
>id="connection_transformdataset"
>title="轉換資料集"
>abstract="此選項將轉換資料集，使其可用於在 B2B 情境中進行人員型查詢。一旦開啟，資料集的轉換便無法復原。"

>[!CONTEXTUALHELP]
>id="connection_connectionmap"
>title="連接圖"
>abstract="連接圖會以視覺化方式顯示事件、人員、帳戶和相關查詢資料集 (如機會、行銷活動成員等) 之間的關係。"

>[!CONTEXTUALHELP]
>id="connection_stitching_enable"
>title="啟用身分識別拼接"
>abstract="啟用身分識別拼接來提升此事件資料集，以利進行跨管道分析。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview" text="拼接概觀"

>[!CONTEXTUALHELP]
>id="connection_stitching_dialog"
>title="啟用身分識別拼接"
>abstract="啟用身分拼接會從資料集或身分圖表衍生拼接的ID。 此過程可能包括合併來自已驗證和未驗證工作階段的使用者資料。<br/><br/>您有責任遵守適用的法律和規定。此法規遵循包括您在資料集上啟用拼接之前獲得必要的一般使用者許可權。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview" text="拼接概觀"

>[!CONTEXTUALHELP]
>id="connection_persistentid"
>title="永久 ID"
>abstract="從可用的身分識別中選取一個永久 ID。永久 ID 是事件資料集中所有事件皆可使用的識別碼。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview" text="拼接概觀"

>[!CONTEXTUALHELP]
>id="connection_lookbackwindow"
>title="重播時段"
>abstract="選取重新執行視窗在銜接時使用的適當時段。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview" text="拼接概觀"

>[!CONTEXTUALHELP]
>id="connection_namespace_map"
>title="命名空間身分識別圖"
>abstract="選取要從身分識別圖中挑選識別碼時使用的命名空間。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview" text="拼接概觀"

>[!CONTEXTUALHELP]
>id="connection_namespace_graph"
>title="命名空間身分識別圖"
>abstract="選取要從身分識別圖中挑選識別碼時使用的命名空間。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview" text="拼接概觀"


### 資料集類型 {#dataset-types}

[!UICONTROL Customer Journey Analytics] 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定資料集類型。

>[!IMPORTANT]
>
>為您的連線新增至少一個事件或摘要資料集 (標準或是臨時或關聯類型)。

有不同的資料集類型：[!UICONTROL 事件]資料、[!UICONTROL 輪廓]資料、[!UICONTROL 查詢]資料和[!UICONTROL 摘要]資料，每一種資料都根據其對應的 XDM 型結構描述。

| 資料集類型 | 說明 | 時間戳記 | 結構描述 | 個人 ID <br/> 帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} |
|---|---|---|---|---|
| **[!UICONTROL 事件]** | 代表及時事件的資料。例如網站造訪、互動、交易、POS 資料、調查資料、廣告印象資料等。該資料可能是典型的點按資料流資料，包含客戶 ID 或 Cookie ID 以及時間戳記。若使用事件資料，您可以靈活地選取要將哪個 ID 當做個人 ID 使用。 | 設定為 [!UICONTROL Experience Platform] 中事件型結構描述之預設時間戳記欄位。 | 以具有&#x200B;*時間序列*&#x200B;行為之 XDM 類別為基礎的任何內建或自訂的結構描述。例如 *XDM 體驗事件*&#x200B;或 *XDM 決策事件*。 | 您可以選擇想要包含的個人 ID 或帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}。在 Experience Platform 中定義的每個資料集結構描述，都可以各自擁有一組已定義且與身分識別命名空間相互關聯的一個或多個身分識別。這些身分識別中的任何一個都可以用作個人 ID 或帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}。範例包括 Cookie ID、拼接後的 ID、使用者 ID、追蹤程式碼、帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 等。 |
| **[!UICONTROL 查詢]** | 您可以新增資料集做為所有資料集類型中的查詢欄位：輪廓、查詢和事件資料集 (始終支援後者)。這項附加功能擴展了 Customer Journey Analytics 的功能，以支援複雜的資料模型，包括 B2B。此資料用於尋找在事件、輪廓或查詢資料中找到的值或索引鍵。您最多可以新增三個查詢層級。(請注意，[衍生欄位](/help/data-views/derived-fields/derived-fields.md)無法用作連線內查詢的比對索引鍵。) 例如，您可能會上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。有關範例，請參閱「[B2B 範例](/help/use-cases/b2b/example.md)」。 | 不適用 | 除 *XDM 個體輪廓*&#x200B;類別外，以具有&#x200B;*記錄*&#x200B;行為的 XDM 類別為基礎的任何內建或自訂的結構描述。 | 不適用 |
| **[!UICONTROL 輪廓]** | [!UICONTROL 事件]資料中，套用至您帳戶、人員、使用者或客戶的資料。例如，您可上傳有關客戶的 CRM 資料。 | 不適用 | 以 *XDM 個體輪廓*&#x200B;類別為基礎的任何內建或自訂的結構描述。 | 您可以選擇想要包含的個人 ID / 帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}。[!DNL Experience Platform] 中定義的每個資料集，除了摘要資料集以外，皆各自擁有一組已定義的一個或多個個人 ID 或帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}。例如 Cookie ID、拼接後的 ID、使用者 ID、追蹤程式碼、帳戶 ID 等。<br>![個人 ID &#x200B;](assets/person-id.png)**請注意**：如果您建立的連線包含具有不同 ID 的資料集，報告會反映出這一點。若要合併資料集，您需要使用相同的個人 ID 或帳戶 ID [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}。 |
| **摘要** | 與單獨個人 ID 無關聯的時間序列資料。摘要資料代表不同彙總等級的彙總資料，例如行銷活動。您可以在 Customer Journey Analytics 中使用此資料來支援各種使用案例。如需詳細資訊，請參閱[摘要資料](/help/data-views/summary-data.md)。 | 自動設定為 Experience Platform 中事件型摘要量度結構描述之預設時間戳記欄位。僅支援每小時或每日顆粒度。 | 以 *XDM 摘要量度*&#x200B;類別為基礎的任何內建或自訂的結構描述。 | 不適用 |

或者，上面列出的資料集類型可以基於臨時或關聯式結構描述，而非一般 XDM 型結構描述。

| 資料集類型 | 說明 | 時間戳記 | 結構描述 | 個人 ID |
|---|---|---|---|---|
| **[!UICONTROL 臨時]** | 以[臨時結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/api/ad-hoc)為基礎的臨時資料，包含已定義命名空間且僅供單一資料集使用的欄位。 | 取決於您為臨時資料集選取的資料集類型。 | 基於&#x200B;*臨時*&#x200B;行為的任何臨時結構描述 | 取決於您為臨時資料集選取的資料集類型。 |
| **[!UICONTROL 模型]** | 以關聯式結構描述為基礎的關聯式資料。 | 取決於您為關聯式資料集選取的資料集類型。 | 任何關聯式結構描述。 | 取決於您為關聯式資料集選取的資料集類型。 |


### 新增資料集

您可以在建立或編輯連線時，新增一個或多個 Experience Platform 資料集。


1. 在「**[!UICONTROL 連線]**」>「**[!UICONTROL _連線名稱_]**」介面中，選取「![資料新增](/help/assets/icons/DataAdd.svg) **[!UICONTROL 新增資料集]**」。

1. 在「➊ **[!UICONTROL 選取資料集]**」步驟中，您會看到 Experience Platform 資料集的清單。

   ![選取資料集](assets/select-datasets.png)

   對於每個資料集，清單會顯示：

   | 欄 | 說明 |
   |---|---|
   | **[!UICONTROL 資料集]** | 資料集的名稱。選取名稱即可將您導向 Experience Platform 中的資料集。選取「![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」可顯示含有資料集更多詳細資訊的快顯視窗。您可以選取「**[!UICONTROL 在 Platform 中編輯]**」，以直接在 Experience Platform 編輯資料集。 |
   | **[!UICONTROL 資料集類型]** | 資料集類型：[事件](#event-dataset)、[輪廓](#profile-dataset)、[查詢](#lookup-dataset)、[摘要](#summary-dataset)、[臨時](#ad-hoc-dataset)或[關聯式](#relational-dataset)。 |
   | **[!UICONTROL 記錄數量]** | Experience Platform 中資料集的上個月記錄總數。 |
   | **[!UICONTROL 結構描述]** | 資料集的結構描述。選取名稱，將您導向 Experience Platform 中的結構描述。 |
   | **[!UICONTROL 上一個批次]** | 在 Experience Platform 攝取的最後一個批次的狀態。請參閱[批次狀態](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/batch/troubleshooting#batch-states)以了解更多資訊。 |
   | **[!UICONTROL 資料集 ID]** | 資料集的 ID。 |
   | **[!UICONTROL 最後更新時間]** | 資料集的最後更新時間戳記。 |

   * 若要變更資料集清單中顯示的欄，請選取「![欄位設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」並選取要在「[!UICONTROL 自訂表格]」對話框中顯示的欄。
   * 要搜尋特定資料集，請使用搜尋欄位「![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)」。
   * 要讓所選資料集切換為顯示或隱藏，請選取「![選取](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg)」「**[!UICONTROL 隱藏已選取]**」或者「**[!UICONTROL 顯示已選取]**」。
   * 要將已選取資料集清單中的資料集刪除，請使用「![關閉](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg)」。要刪除所有已選取的資料集，請選取「**[!UICONTROL 全部清除]**」。
   * 若要顯示資料集的詳細資料，請選取「![資訊大綱](/help/assets/icons/InfoOutline.svg)」。


1. 選取一個或多個資料集，然後選取「**[!UICONTROL 下一步]**」。連線中必須至少包含一個事件或摘要資料集。

1. 在「**[!UICONTROL 新增資料集]**」對話框的「➋ **[!UICONTROL 資料集設定]**」步驟中，[逐一設定每個選取的資料集](#dataset-settings)。

   ![新增資料集](assets/add-dataset.png)

1. 選取「**[!UICONTROL 新增資料集]**」，將已設定的資料集新增至連線。如果您尚未提供您要新增之每個資料集的所有必要設定，系統會通知您。

   或者，您可以選取「**[!UICONTROL 取消]**」，取消將資料集新增至連線。或選取「**[!UICONTROL 上一步]**」回到「➊ **[!UICONTROL 選取資料集]**」步驟。


### 編輯資料集

若要編輯已針對連線進行設定的資料集，請在「**[!UICONTROL 連線]**」>「**[!UICONTROL _連線名稱_]**」介面中：

1. 針對要編輯之資料集表格中所列的資料集，選取「![更多](/help/assets/icons/More.svg)」
1. 選取「![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料集]**」。

1. 在「**[!UICONTROL 編輯資料集：_資料集名稱_]**」對話框中設定[資料集設定](#dataset-settings)。

   ![編輯資料集](assets/edit-dataset.png)

   >[!NOTE]
   >
   >針對屬於已儲存連線的[臨時](#ad-hoc-dataset)或[關聯式](#relational-dataset)資料集，您不能編輯其&#x200B;**[!UICONTROL 資料集類型]**、**[!UICONTROL 個人 ID]**、**[!UICONTROL 身分識別命名空間]**&#x200B;和&#x200B;**[!UICONTROL 時間戳記]**。若要變更這些設定：
   >
   >1. 從連線中刪除現有的臨時或關聯式資料集。
   >1. 將相同的資料集連同更新後的設定新增至連線。
   >

1. 選取「**[!UICONTROL 套用]**」來套用資料集設定。選取「**[!UICONTROL 取消]**」進行取消。


### 資料集設定

新增資料集或編輯現有資料集時，您會設定每個資料集的資料集設定。可用的設定取決於[資料集類型](#dataset-types)，而有部分資料集類型則取決於連線類型 (個人型或 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 帳戶型)。

所有資料集和資料集類型都有[一般設定和詳細資料](#general-dataset-settings-and-details)，例如是否要匯入新資料以及要求回填。

#### 事件資料集

事件資料集的特定設定取決於連線類型。

##### 個人型連線

![事件資料集設定 B2C](assets/event-dataset-settings-b2c.png)

針對個人型連線中的事件資料集，您可以指定：

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 個人 ID]** | 從可用身分識別的下拉式選單中選取個人 ID。這些身分識別由 Experience Platform 的資料集結構描述賦予定義。如需如何使用身分識別圖做為個人 ID 的相關資訊，請參閱[使用身分識別圖做為個人 ID](#use-identity-map-as-a-person-id)。<p>如果沒有個人 ID 可以選擇，表示結構描述中尚未定義個人 ID。有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。 <p>所選個人 ID 的值會區分大小寫。例如，`abc123` 和 `ABC123` 是兩個不同的值。<p>如果記錄不包含您選取做為事件資料集個人 ID 之身分識別的值，則會略過記錄。 |
| **[!UICONTROL 啟用身分識別拼接]** | 選取以針對此事件資料集[啟用身分識別拼接](/help/stitching/overview.md)。 |
| **[!UICONTROL 時間戳記]** | 此設定會自動設定為 Experience Platform 中事件型結構描述之預設時間戳記欄位。 |
| **[!UICONTROL 資料來源類型]** | 選取資料來源類型。資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |
| **[!UICONTROL 資料來源說明]** | 當您選取「其他」做為資料來源類型時，對該資料來源的說明。 |


##### 帳戶型連線

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

針對帳戶型連線中的事件資料集，您可以指定：

![事件資料集設定 B2C](assets/event-dataset-settings-b2b.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 全域帳戶 ID]** | 從 Experience Platform 資料集結構描述中已定義的可用身分識別當中，選取一個全域帳戶 ID (帳戶的唯一識別碼)。在您將全域帳戶做為容器新增至連線後適用。 <p>如果記錄不包含您選取做為事件資料集帳戶 ID 之身分識別的值，則會略過記錄。 |
| **[!UICONTROL 帳戶 ID]** | 從 Experience Platform 資料集結構描述中已定義之可用身分識別當中，選取一個帳戶 ID (帳戶的唯一識別碼)。當您未將全域帳戶做為容器新增至連線時適用。 |
| **[!UICONTROL 機會 ID]** | 從 Experience Platform 的資料集結構描述中已定義的可用身分識別當中，選取機會 ID (機會的唯一識別碼)。 |
| **[!UICONTROL 購買群組 ID]** | 從 Experience Platform 資料集結構描述中已定義的可用身分識別當中，選取一個購買群組 ID (購買群組的唯一識別碼)。 |
| **[!UICONTROL 個人 ID]** | 從可用身分識別的下拉式選單中選取個人 ID。這些身分識別由 Experience Platform 的資料集結構描述賦予定義。如需如何使用身分識別圖做為個人 ID 的相關資訊，請參閱[使用身分識別圖做為個人 ID](#id-map)。<p>如果沒有個人 ID 可以選擇，表示結構描述中尚未定義一或多個個人 ID。有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。 <p>所選個人 ID 的值會區分大小寫。例如，`abc123` 和 `ABC123` 是兩個不同的值。 |
| **[!UICONTROL 時間戳記]** | 此設定會自動設定為 Experience Platform 中事件型結構描述之預設時間戳記欄位。 |
| **[!UICONTROL 資料來源類型]** | 選取資料來源類型。資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |
| **[!UICONTROL 資料來源說明]** | 當您選取「其他」做為資料來源類型時，對該資料來源的說明。 |

#### 輪廓資料集

輪廓資料集的特定設定取決於連線類型。

##### 個人型連線

![輪廓資料集設定 B2C](assets/profile-dataset-settings-b2c.png)

對於個人型連線中的輪廓資料集，您可以指定：

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 個人 ID]** | 從可用身分識別的下拉式選單中選取個人 ID。這些身分識別由 Experience Platform 的資料集結構描述賦予定義。如需如何使用身分識別圖做為個人 ID 的相關資訊，請參閱[使用身分識別圖做為個人 ID](#id-map)。<p>如果沒有個人 ID 可以選擇，即為結構描述中尚未定義個人 ID。有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。 <p>所選個人 ID 的值會區分大小寫。例如，`abc123` 和 `ABC123` 是兩個不同的值。 <p>如果記錄不包含您選取做為輪廓資料集個人 ID 之身分識別的值，則會略過記錄。 |
| **[!UICONTROL 資料來源類型]** | 選取資料來源類型。資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |
| **[!UICONTROL 資料來源說明]** | 當您選取「其他」做為資料來源類型時，對該資料來源的說明。 |

#### 帳戶型連線

![輪廓資料集設定 B2B](assets/profile-dataset-settings-b2b.png)

對於帳戶型連線中的輪廓資料集，您可以指定：

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 個人 ID]** | 從可用身分識別的下拉式選單中選取個人 ID。這些身分識別由 Experience Platform 的資料集結構描述賦予定義。如需如何使用身分識別圖做為個人 ID 的相關資訊，請參閱[使用身分識別圖做為個人 ID](#id-map)。<p>如果沒有個人 ID 可以選擇，即為結構描述中尚未定義個人 ID。有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。 <p>所選個人 ID 的值會區分大小寫。例如，`abc123` 和 `ABC123` 是兩個不同的值。 <p>如果記錄不包含您選取做為輪廓資料集個人 ID 之身分識別的值，則會略過記錄。 |
| **[!UICONTROL 全域帳戶欄位]** | 從可用身分識別的下拉式選單中，選取全域帳戶欄位，以支援資料集的帳戶型報告。在您將全域帳戶做為容器新增至連線後適用。 |
| **[!UICONTROL 帳戶欄位]** | 從可用身分識別的下拉式選單中，選取帳戶欄位，以支援資料集的帳戶型報告。當您未將全域帳戶做為容器新增至連線時適用。 |
| **[!UICONTROL 資料來源類型]** | 選取資料來源類型。資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |
| **[!UICONTROL 資料來源說明]** | 當您選取「其他」做為資料來源類型時，對該資料來源的說明。 |

#### 查詢資料集

查詢資料集的特定設定取決於連線類型。

##### 個人型連線

![個人型查詢事件資料集設定](assets/lookup-dataset-settings-b2c.png)

對於個人型連線中的查詢資料集，您可以指定：

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 索引鍵]** | 用於查詢資料集的索引鍵。 <p>如果記錄不包含您為查詢資料集選取之索引鍵的值，則會略過該記錄。 |
| **[!UICONTROL 比對索引鍵]** | 要加入其中一個事件資料集的比對索引鍵。若此清單空白，您可能尚未新增或設定事件資料集。 |
| **[!UICONTROL 資料來源類型]** | 選取資料來源類型。資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |
| **[!UICONTROL 資料來源說明]** | 當您選取「其他」做為資料來源類型時，對該資料來源的說明。 |
| **[!UICONTROL 轉換資料集]** | 對於特定的 B2B 查詢資料集，您可以對適當的 B2B 人員型報告情境啟用資料集轉換。如需詳細資訊，請參閱[轉換資料集以進行 B2B 查詢](transform-datasets-b2b-lookups.md)。 |



##### 帳戶型連線

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

![帳戶型查詢事件資料集設定](assets/lookup-dataset-settings-b2b.png)

針對帳戶型連線中的查詢資料集，您可以指定：

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 索引鍵]** | 用於查詢資料集的索引鍵。 <p>如果記錄不包含您為查詢資料集選取之索引鍵的值，則會略過該記錄。 |
| **[!UICONTROL 比對索引鍵類型]** | 選取如何連接資料集：根據&#x200B;**[!UICONTROL 依欄位比對]**&#x200B;或&#x200B;**[!UICONTROL 依容器比對]**。如需詳細資訊，請參閱[依欄位容器比對](/help/getting-started/cja-b2b-concepts-features.md#match-by-container-or-field)。 |
| **[!UICONTROL 比對索引鍵]** | 要加入其中一個事件資料集的比對索引鍵。若此清單空白，您可能尚未新增或設定事件資料集。<br/><br/>根據您選取的&#x200B;**[!UICONTROL 比對索引鍵]**&#x200B;類型，選取適當的值：<ul><li>**[!UICONTROL 依欄位比對]**：![依欄位比對](assets/match-by-field.png)<br/>從「**[!UICONTROL 比對索引鍵]**」下拉式功能表中選取欄位，以連結其中一個事件資料集。若此清單空白，您可能尚未新增或設定事件資料集。</li><li>**[!UICONTROL 依容器比對]**：![依容器比對](assets/match-by-container.png)<br/>從「**[!UICONTROL 比對索引鍵]**」下拉式選單中選取容器，以連結其中一個事件資料集。可供選取的容器取決於您在設定連線時所包含的容器選項。</li></ul> |
| **[!UICONTROL 全域帳戶欄位]** | 用於帳戶型報告的全域帳戶 ID。 |



#### 摘要資料集

摘要資料集的特定設定如下：

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 時間戳記]** | 此設定會自動設定為 Experience Platform 中事件型結構描述之預設時間戳記欄位。 |
| **[!UICONTROL 時區]** | 為時間序列摘要資料選取適當的時區。 |
| **[!UICONTROL 顆粒度]** | 表示用於彙總摘要資料的時間段，目前為小時或日。衍生自資料集中的資料。 |


#### 臨時資料集

>[!NOTE]
>
>雖然可以設定和選取，但基於效能考量，您應該避免針對時間序列 (事件、摘要) 資料使用臨時資料集。關聯式或一般 XDM 型資料集比臨時資料集更適合處理時間序列資料。

臨時資料集的特定設定如下：

| 設定 | 選取的資料集類型 | 說明 |
|---|---|---|
| **[!UICONTROL 資料集類型]** | 不適用 | 臨時資料集中的資料類型。可能的值為：**[!UICONTROL 事件]**、**[!UICONTROL 輪廓]**、**[!UICONTROL 查詢]**&#x200B;和&#x200B;**[!UICONTROL 摘要]**。 |
| **[!UICONTROL 個人 ID]** | 事件、輪廓 | 從臨時或關聯式結構描述中選取代表個人 ID 的欄位。此欄位可以是資料集中的任何欄位。從&#x200B;**[!UICONTROL 身分識別命名空間欄位]**&#x200B;或從&#x200B;**[!UICONTROL 非身分識別欄位]**&#x200B;選取。<br/>如果臨時結構描述中有一個或多個欄位標示為身分識別且具有身分識別命名空間，您只能從&#x200B;**[!UICONTROL 身分識別命名空間]**&#x200B;選取身分識別碼。 |
| **[!UICONTROL 身分識別命名空間]** | 事件 | 選取身分識別命名空間，若您已從&#x200B;**[!UICONTROL 非身分識別]**&#x200B;欄位中選取個人 ID。 |
| **[!UICONTROL 時間戳記]** | 事件、摘要 | 從臨時結構描述中選取代表時間戳記欄位的欄位。此欄位可以是類型 `DateTime` 的任何可用欄位。 |
| **[!UICONTROL 索引鍵]** | 查詢 | 用於查詢資料集的索引鍵。<br/>如果記錄不包含您為查詢資料集選取之索引鍵的值，則會略過該記錄。 |
| **[!UICONTROL 比對索引鍵]** | 查詢 | 要加入其中一個事件或查詢資料集的比對索引鍵。若此清單空白，您可能尚未新增或設定事件或查詢資料集。 |


#### 關聯式資料集

>[!NOTE]
>
>關聯式資料集主要用於支援即將推出的 Experience Platform Data Mirror for Customer Journey Analytics 功能。
>

關聯式資料集的特定設定如下：

| 設定 | 選取的資料集類型 | 說明 |
|---|---|---|
| **[!UICONTROL 資料集類型]** | 不適用 | 關聯式資料集中的資料類型。<br/>如果資料集包含時間序列資料，可能的值為：**[!UICONTROL 事件]**&#x200B;和&#x200B;**[!UICONTROL 摘要]**。<br/>如果資料集包含記錄資料，可能的值為：**[!UICONTROL 輪廓]**&#x200B;和&#x200B;**[!UICONTROL 查詢]**。 |
| **[!UICONTROL 個人 ID]** | 事件、輪廓 | 從關聯式結構描述中選取代表個人 ID 的欄位。選取範圍僅限於關聯式結構描述中標示為「身分識別」且確實具有身分識別命名空間的欄位清單。 |
| **[!UICONTROL 時間戳記]** | 事件、摘要 | 在結構描述中定義為時間戳記描述項的欄位。此欄位會自動填入。 |
| **[!UICONTROL 索引鍵]** | 查詢 | 用於查詢資料集的索引鍵。<br/>如果記錄不包含您為查詢資料集選取之索引鍵的值，則會略過該記錄。 |
| **[!UICONTROL 比對索引鍵]** | 查詢 | 要加入其中一個事件資料集的比對索引鍵。若此清單空白，您可能尚未新增或設定事件或查詢資料集。 |


#### 一般資料集設定和詳細資訊

每個 (資料集類型) 都有以下通用設定：

{{common-dataset-settings}}


### 再攝取資料

您有時需要將一個或多個資料集中的資料重新攝取到連線中。若是臨時或關聯式資料集，您需要[刪除資料集，然後再新增一次](#edit-a-dataset)。對於其他資料集，您可以更新設定。若要這麼做：

1. 針對您要重新攝取資料的資料集：

   1. 變更以下任一項目：

      * 已攝取的事件資料集的識別碼 (個人 ID、帳戶 ID 或其他 ID)。
      * 已攝取的輪廓或查詢資料集的索引鍵、比對索引鍵或比對索引鍵類型 (欄位或容器)。

      或者，您可以在資料集上切換「**[!UICONTROL 回填所有現有資料回填]**」。

   1. **[!UICONTROL 套用]**&#x200B;資料集的變更。



1. **[!UICONTROL 儲存]**&#x200B;連線。系統會針對特定資料集再攝取資料。


### 刪除資料集

刪除資料集時，您會收到說明刪除可能產生之影響的通知。刪除資料集會影響所有關聯的連線、資料視圖和專案。此外，如果您刪除連線中唯一的事件或摘要資料集，系統會提示您新增另一個事件或摘要資料集。您只能儲存包含至少一個事件或摘要資料集的連線。


### 過去的回填

當您在介面中選取「![歷史記錄](/help/assets/icons/History.svg) **[!UICONTROL 過去的回填]**」時，「**[!UICONTROL 過去的回填：_資料集名稱_]**」對話框會顯示資料集的最新回填。


## 連線預覽 {#preview}

若要預覽您已建立的連線，請在「連線設定」對話框中選取「![PageSearch](/help/assets/icons/PageSearch.svg) **[!UICONTROL 連線預覽]**」。

![連線預覽](assets/create-conn4.png)

此預覽包含列出連線設定的一些欄。顯示的欄類型取決於您的個別資料集。


## 連線圖

若要查看您連線中資料集之間的關係圖，請在「連線設定」對話框中選取「![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 連線圖]**」。

![連線圖](assets/connectionmap.png)

此圖能協助您更加了解自己是如何定義連線，以及如何使用容器和識別碼建立事件、輪廓、查詢和摘要資料集之間的關係。


## 使用數值欄位做為查閱鍵和查閱值 {#numeric}

如果您想將成本或邊界等數值欄位新增到字串鍵欄位，此查詢功能會很實用。它允許數值做為查閱的一部分，當成鍵或值。 在您的查閱結構描述中，您可能會有繫結到 (舉例來說) 您的產品名稱、COGS、行銷活動行銷成本或利潤等的數值。 以下是 Adobe Experience Platform 中的查閱結構描述範例：

![查閱結構描述](assets/schema.png)

系統現在支援將這些值當做量度或維度引進 Customer Journey Analytics 報告中。當您設定連線並提取查閱資料集時，可以編輯資料集以選取[!UICONTROL 「索引鍵」]和[!UICONTROL 「相符的索引鍵」]：

![編輯資料集](assets/lookup-dataset.png)

當您根據此連線設定資料檢視時，您會將數值作為元件新增到資料檢視中。 然後，任何根據此資料檢視的項目都可以報告這些數值。

## 以「身分識別對應」作為個人 ID {#id-map}

Customer Journey Analytics 支援以「身分識別對應」作為個人 ID。 「身分識別圖」是一個允許使用者上傳索引鍵值組的對應資料結構。索引鍵是身分識別命名空間，值是保存身分識別值的結構。 「身分識別對應」存在於每個上傳的列/事件，並會相應填入每一列。

只要資料集所使用的結構屬於 [ExperienceEvent XDM](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home) 類別，一律適用「身分識別對應」。 當您選擇要在 Customer Journey Analytics 連線中包含這類資料集，您就可以選擇使用一個欄位作為主要 ID，也可以使用「身分識別對應」：

![](assets/idmap1.png)

如果您選取「身分識別對應」，系統會提供另外兩個設定選項：

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 使用主要身分名稱空間]** | 這選項會指示 Customer Journey Analytics 在標示 `primary=true` 屬性的「身分識別圖」中尋找身分識別，並且使用該身分識別作為該列的個人 ID。此身分識別在 Experience Platform 中是用於資料分割的主索引鍵。此身分識別也是做為 Customer Journey Analytics 個人 ID 的首選 (取決於資料集在 Customer Journey Analytics 連線中的設定方式)。 |
| **[!UICONTROL 命名空間]** | (當您未使用主要 ID 命名空間時，才能使用此選項) 身分識別命名空間是 [Experience Platform 身分識別服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces)的元件。命名空間是作為身分識別相關內容的指標。如果您指定命名空間，Customer Journey Analytics 會針對此命名空間索引鍵搜尋每一列的身分識別圖，並使用該命名空間底下的身分識別作為該列的個人 ID。由於 Customer Journey Analytics 無法對所有列執行完整的資料集掃描，以判斷哪些命名空間實際存在，因此下拉式選單會列出所有可能的命名空間。了解資料中指定了哪些命名空間；系統不會自動偵測這些命名空間。 |

{style="table-layout:auto"}

### 「身分識別對應」邊緣案例 {#id-map-edge}

下表提供邊緣案例出現時的兩個設定選項及其處理方式：

| 選項 | 「身分識別對應」中沒有 ID | 多個 ID，沒有一個標示為主要 | 多個 ID 標示為主要 | 單一 ID，不一定標示為主要 | ID 標示為主要的無效命名空間 |
|---|---|---|---|---|---|
| **[!UICONTROL 使用主要身分名稱空間]已核取**<br/>![&#x200B;使用主要身分名稱空間](assets/use-primary-identity-namespace.png) | Customer Journey Analytics 會刪除該列。 | Customer Journey Analytics 會刪除該列，因為未指定主要 ID。 | 系統會擷取所有命名空間下標示為主要的 ID，彙整成清單，並依字母排序；重新排序後，系統會將第一個命名空間的第一個 ID 視為個人 ID。 | 做為個人 ID 的單一 ID。 | 即使命名空間可能無效 (不存在於 Adobe Experience Platform 中)，Customer Journey Analytics 也會使用該命名空間下的主要 ID 做為個人 ID。 |
| **[!UICONTROL 已選取特定身分對應名稱空間]**<br/>![&#x200B;未使用主要身分名稱空間](assets/not-use-primary-identity-namespace.png) | Customer Journey Analytics 會刪除該列。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為個人 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為個人 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為個人 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為個人 ID。 (建立連線時只能選取有效的命名空間，因此不可能使用無效的命名空間/ID 作為個人 ID)。 |

{style="table-layout:auto"}

## 計算每日事件平均數量 {#average-number}

連線中的每個資料集都要完成這項計算。

1. 前往 [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home)，並建立查詢。

   查詢如下所示：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   在此範例中，「analytics_demo_data」是資料集名稱。

2. 若要顯示 Adobe Experience Platform 中的所有資料集，請執行 `Show Tables` 查詢。


>[!MORELIKETHIS]
>
>* [資料攝取概觀](/help/data-ingestion/data-ingestion.md)
>* 部落格：[如何在 Adobe Customer Journey Analytics 中善用事件、查詢和輪廓資料集](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-to-leverage-event-lookup-and-profile-datasets-in-adobe/ba-p/681478)

