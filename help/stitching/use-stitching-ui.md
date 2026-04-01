---
title: 啟用拼接
description: 在Customer Journey Analytics中啟用事件資料集的身分彙整。 瞭解如何在連線UI中設定永久ID、人員ID和重新執行視窗，以彙整資料。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: f9c2f9cef97e00eb491b815ab8e83820b2dfc032
workflow-type: tm+mt
source-wordcount: '1712'
ht-degree: 9%

---

# 啟用拼接

您可以在已設定為連線一部分的一或多個事件資料集上啟用拼接。 您授權的Customer Journey Analytics套件決定您可以啟用進行拼接的事件資料集數量。

當您[建立連線](/help/connections/create-connection.md#dataset-settings)或當您[編輯連線](/help/connections/create-connection.md)時，您可以啟用拼接功能，作為事件資料集的[資料集設定](/help/connections/manage-connections.md#edit-a-connection)的一部分。

## 先決條件

您需要檢查並符合您指定的拼接方法的先決條件：[欄位式拼接](fbs.md#prerequisites)或[圖表式拼接](gbs.md#prerequisites)。


## 預檢檢查

如果您符合先決條件，在啟用身分拼接之前，可能會想要對事件資料集中的資料執行一些預檢檢查：

* 如果您打算將XDM結構描述欄位用於永久ID或人員ID，請確定在事件資料集的結構描述中正確標示身分。 [請參閱身分名稱空間概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces)。
* 驗證永久ID和人員ID的身分涵蓋範圍：

   * **永久ID**

     查詢7天的資料，其中您的永久ID欄位不是Null，再除以資料集內所有事件的7天資料查詢。 此百分比應高於95%。

     可用於驗證的查詢範例：

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     其中:

      * `{PERSISTENT_ID_FIELD}`是永久識別碼的欄位。 例如：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}`是事件資料集的資料表名稱。
      * `{FORMAT_STRING}`是時間戳記欄位的格式字串。 例如：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE} `是開始日期。 例如：`2024-01-01 00:00:00`。
      * `{END_DATE}`是標準格式的結束日期。 例如：`2024-01-08 00:00:00`。


   * **個人 ID**
      * 對於圖表式拚接，請確保身分圖表包含從您選擇的永久ID名稱空間和人員ID名稱空間中連結ID值的片段。 您可以前往[Experience Platform身分識別圖形檢視器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"}執行測試，並透過某些範例永久ID值查詢圖形。 驗證這些永久ID值是否連結至圖表中的人員ID值。
      * 對於以欄位為基礎的彙整，請查詢7天資料中的人員ID欄位不是Null，然後除以資料集中所有事件的7天資料查詢。 理想情況下，此百分比應高於5%。

        可用於驗證的查詢範例：

        ```sql
        SELECT
          COUNT(*) AS total_events,
          COUNT({PERSON_ID_FIELD}) AS events_with_personid,
          ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
        FROM 
          {DATASET_TABLE_NAME}
        WHERE
          TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
          AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
        ```

        其中:

         * `{PERSON_ID_FIELD}`是人員ID的欄位。 例如：`identityMap.crmId[0]`。
         * `{DATASET_TABLE_NAME}`是事件資料集的資料表名稱。
         * `{FORMAT_STRING}`是時間戳記欄位的格式字串。 例如：`MM/DD/YY HH12:MI AM`。
         * `{START_DATE}`是開始日期。 例如：`2024-01-01 00:00:00`。
         * `{END_DATE}`是標準格式的結束日期。 例如：`2024-01-08 00:00:00`。



## 啟用身分識別拼接 {#enable-identity-stitching}

當您在以人員為基礎的連線中[新增](/help/connections/create-connection.md#add-datasets)或[編輯](/help/connections/create-connection.md#edit-a-dataset)事件資料集時，可以啟用身分拼接。 以帳戶為基礎的連線無法使用身分彙整。

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="身分識別圖的變更"
>abstract="在使用身分識別圖進行資料拼接之前，請確定已完成身分識別圖的設定。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/gbs" text="圖表型拼接"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="個人 ID"
>abstract="從可供使用的身分識別中選取人員 ID (人員的唯一識別碼)。 若您的授權包含圖表型拼接，且您想使用該拼接方式，請選取&#x200B;**[!UICONTROL 身分識別圖]**。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="拼接量度"
>abstract="拼接量度是使用具有過去7天事件時間戳記的範例資料集來計算。<br>此資料範例集通常與&#x200B;**[!UICONTROL 預覽]**&#x200B;資料表中使用的範例資料不同。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="個人 ID 覆蓋率"
>abstract="在拚接程式（即時和重播）期間用於識別的所選人員ID的涵蓋範圍。<br/>為了達到最佳拼接結果，每個永久ID的身分圖表中都應有（永久ID、人員ID）關係。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="個人 ID 覆蓋率"
>abstract="在拚接程式（即時和重播）期間用於識別的所選人員ID的涵蓋範圍。<br/>為了達到最佳拼接結果，每個永久ID （裝置資訊）至少應在一個事件中傳送個人ID （使用者資訊）。"

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="永久性 ID 覆蓋率"
>abstract="此值用於在拼接過程（即時和重播）期間進行識別，以備無法偵測到人員ID值時使用。 <br/>資料中會捨棄沒有永久ID和人員ID的事件。 為獲得最佳拼接結果，所有事件都應有永久性 ID。"


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="異常 ID"
>abstract="異常 ID 是指嚴重影響報告資料的 ID 值。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/technotes/badids" text="異常 ID"


### 資料集設定

若要啟用拼接，請在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;或&#x200B;**[!UICONTROL 編輯資料集]**&#x200B;對話方塊的事件資料集&#x200B;**[!UICONTROL 資料集設定]**&#x200B;區段中：

啟用身分拼接時![身分拼接選項](assets/identity-stitching-ui.png)

1. 選取&#x200B;**[!UICONTROL 啟用身分拼接]**。

   如果您啟用或停用連線中儲存事件資料集的拼接，**[!UICONTROL 變更人員ID]**&#x200B;對話方塊會顯示人員ID變更的影響。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   **[!UICONTROL 啟用身分拼接]**&#x200B;對話方塊會摘要拼接身分的結果。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

1. 從&#x200B;**[!UICONTROL 永久ID]**&#x200B;下拉式功能表中選取永久ID。

   如果您為永久ID選取&#x200B;**[!UICONTROL 身分對應]**，則必須選取名稱空間。 您有兩個選項：

   * 選取&#x200B;**[!UICONTROL 使用主要身分名稱空間]**&#x200B;以使用主要身分名稱空間。
   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。

1. 從&#x200B;**[!UICONTROL 人員ID]**&#x200B;下拉式功能表中選取人員ID。

   如果您為人員ID選取&#x200B;**[!UICONTROL 身分對應]**，則必須選取名稱空間。 您有兩個選項：

   * 選取&#x200B;**[!UICONTROL 使用主要身分名稱空間]**&#x200B;以使用主要身分名稱空間。
   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。


   如果您為人員ID選取&#x200B;**[!UICONTROL 身分圖表]** （若要使用[圖表式拼接](/help/stitching/gbs.md)），則必須選取名稱空間。

   >[!NOTE]
   >
   >確定您有權使用身分圖表。
   >

   在此之前，會顯示&#x200B;**[!UICONTROL 變更為身分圖表]**&#x200B;對話方塊，以確保您已完成資料集的身分圖表設定。 此設定是[圖表式先決條件](/help/stitching/gbs.md#prerequisites)的一部分，之後您才能使用身分圖表進行拼接。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。

1. 從&#x200B;**[!UICONTROL 重新執行視窗]**&#x200B;下拉式功能表中選取重新執行視窗。 可用選項取決於您有權使用的Customer Journey Analytics套件。

1. 選取&#x200B;**[!UICONTROL 下一步]**&#x200B;以檢視要拼接的事件資料集主題預覽。


### 資料集預覽

在標準&#x200B;**[!UICONTROL 資料集預覽]**&#x200B;介面之上，當[新增](/help/connections/create-connection.md#add-datasets)或是在以人員為基礎的連線中[編輯](/help/connections/create-connection.md#edit-a-dataset)資料集時，可以使用兩個額外的資訊面板。

啟用身分拼接時![身分拼接選項](assets/identity-stitching-ui-preview.png)

#### 拼接量度

**[!UICONTROL 拼接量度]**&#x200B;是使用具有過去7天事件時間戳記的範例資料集計算。 這個範例資料集通常與&#x200B;**[!UICONTROL 預覽]**&#x200B;資料表中使用的範例資料不同。 拼接量度提供下列專案的詳細資訊：

* **[!UICONTROL 人員ID涵蓋範圍]**：在拼接程式（即時和重播）期間用於識別的所選人員ID涵蓋範圍。
   * 為了獲得最佳欄位式拚接結果，每個永久ID （裝置資訊）應在至少一個事件上傳送個人ID （使用者資訊）。
   * 為了獲得最佳的圖表式拚接結果，每個永久ID的身分圖表應會顯示（永久ID、人員ID）關係。

  人員ID涵蓋範圍會以百分比顯示，並和穩定開發或生產設定上建議的專案進行比較。 此涵蓋範圍值越高，使用選取的人員ID所獲得的拼接結果就越好。

* **[!UICONTROL 永續識別碼涵蓋範圍]**：此值用於拼接程式（即時和重新執行）期間進行識別，以防偵測不到人員ID值。 沒有永久性 ID 和個人 ID 的事件會從資料中剔除。為獲得最佳拼接結果，所有事件都應有永久性 ID。

  永久ID涵蓋範圍會以百分比顯示，並和穩定開發或生產設定上的最低建議值比較。


#### 異常 ID

>[!INFO]
>
>在Customer Journey Analytics介面中，不良ID也稱為BAVID。
> 

在Customer Journey Analytics中，錯誤ID是識別碼：

* 具有特定ID值，且該ID值來自啟用拼接功能資料集中的永久ID或人員ID欄位，**和**
* 在一個月內對連線資料中的超過100萬(1,000,000)個事件負責。

當ID值標示為錯誤ID時，連線資料中任何包含該ID值的未來事件都會遭到捨棄，而不會顯示在報表中。

錯誤ID使用案例的範例：

* 人員ID欄位中有自訂或預留位置值（例如，`undefined`）。 這類值也會影響[拼接與報告資料品質](/help/stitching/faq.md#undefined-person-id-values)。
* 在以欄位為基礎的彙整設定中，如果多人共用一部裝置，且使用者之間的轉換總數超過50,000。 在此案例中，拚接程式會停止為該裝置使用人員ID資訊，而僅改用永久性ID資訊。 因此，該裝置的所有資料集事件都會傳送到具有永久ID身分的連線資料中，這極有可能導致「ID錯誤」情況。


>[!NOTE]
>**[!UICONTROL 拼接量度]** （包括&#x200B;**[!UICONTROL 錯誤的ID]**）是根據有限的資料集計算的。 若要識別您計畫用於拼接的資料集是否存在錯誤ID，請參閱[錯誤ID技術檔案](/help/technotes/badids.md)。
>


### 儲存

儲存連線後，一旦開始為這些資料集擷取資料，就會開始彙整已啟用資料集的彙整程式。

>[!CAUTION]
>
>對於在連線介面中啟用拼接的資料集，回填狀態會立即並錯誤回報為![狀態綠色](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _回填已完成]**，因為回填已完成數目。 使用其他方法驗證是否回填了拼接資料集中的資料。
>


## 限制

除了[欄位式拚接限制](/help/stitching/fbs.md#limitations)和[圖表式拚接限制](/help/stitching/gbs.md#limitations)之外，當您在「連線」介面中啟用拚接時，將會套用下列限制：

* 您只能將事件資料集拼接一次，做為單一連線的一部分。 您無法多次定義相同的事件資料集，並為每個執行個體使用個別的彙整設定。 如果您想在相同資料集上套用不同的彙整設定，請為每個設定使用個別的連線。


## 移轉

在Connections介面中啟用的彙整可同時存在，而不會出現任何以請求為基礎的彙整問題。

例如，由於先前或目前的拼接請求，您在資料湖中有網頁型拼接資料集。 您可以使用連線介面，從客服中心資料集新增拼接資料，以將該資料與網頁型資料結合。

最終，Adobe會將您的請求型彙整資料集移轉至連線體驗中的新彙整。
