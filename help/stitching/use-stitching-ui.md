---
title: 啟用拼接
description: 瞭解如何在連線UI中啟用拼接。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: d1ba2d203738ca9bf74d17bb93712eff26f88f25
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 5%

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

     其中：

      * `{PERSISTENT_ID_FIELD}`是永久識別碼的欄位。 例如：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}`是事件資料集的資料表名稱。
      * `{FORMAT_STRING}`是時間戳記欄位的格式字串。 例如：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE} `是開始日期。 例如：`2024-01-01 00:00:00`。
      * `{END_DATE}`是標準格式的結束日期。 例如：`2024-01-08 00:00:00`。


   * **個人 ID**
      * 對於圖表式拚接，請確保身分圖表包含從您選擇的永久ID名稱空間和人員ID名稱空間中連結ID值的片段。 您可以前往[Experience Platform身分識別圖形檢視器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"}執行測試，並透過某些測試永久ID值來查詢圖形。 驗證這些永久ID值是否連結至圖表中的人員ID值。
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

        其中：

         * `{PERSON_ID_FIELD}`是人員ID的欄位。 例如：`identityMap.crmId[0]`。
         * `{DATASET_TABLE_NAME}`是事件資料集的資料表名稱。
         * `{FORMAT_STRING}`是時間戳記欄位的格式字串。 例如：`MM/DD/YY HH12:MI AM`。
         * `{START_DATE}`是開始日期。 例如：`2024-01-01 00:00:00`。
         * `{END_DATE}`是標準格式的結束日期。 例如：`2024-01-08 00:00:00`。



## 啟用身分識別拼接 {#enable-identity-stitching}

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="身分識別圖的變更"
>abstract="在使用身分識別圖進行資料拼接之前，請確定已完成身分識別圖的設定。"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs" text="圖表型拼接"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="個人 ID"
>abstract="從可用身分中選取人員ID （人員的唯一識別碼）。 如果您要使用圖表式拼接，請選取&#x200B;**[!UICONTROL 身分圖表]**。"

若要啟用拼接，請在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;或&#x200B;**[!UICONTROL 編輯資料集]**&#x200B;對話方塊的事件資料集區段中：

啟用身分拼接時![身分拼接選項](assets/identity-stitching-ui.png)

1. 選取&#x200B;**[!UICONTROL 啟用身分拼接]**。

   如果您啟用或停用連線中儲存事件資料集的拼接，**[!UICONTROL 變更人員ID]**&#x200B;對話方塊會顯示人員ID變更的影響。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   **[!UICONTROL 啟用身分拼接]**&#x200B;對話方塊會摘要拼接身分的結果。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

1. 從&#x200B;**[!UICONTROL 永久ID]**&#x200B;下拉式功能表中選取永久ID。

   如果您為永久ID選取&#x200B;**[!UICONTROL 身分對應]**，則必須選取名稱空間。 您有兩個選項：

   * 啟用&#x200B;**[!UICONTROL 使用主要身分名稱空間]**&#x200B;以使用主要身分名稱空間。
   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。

1. 從&#x200B;**[!UICONTROL 人員ID]**&#x200B;下拉式功能表中選取人員ID。

   如果您為人員ID選取&#x200B;**[!UICONTROL 身分對應]**，則必須選取名稱空間。 您有兩個選項：

   * 啟用&#x200B;**[!UICONTROL 使用主要身分名稱空間]**&#x200B;以使用主要身分名稱空間。
   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。


   如果您為人員ID選取&#x200B;**[!UICONTROL 身分圖表]** （若要使用[圖表式拼接](/help/stitching/gbs.md)），則必須選取名稱空間。

   >[!NOTE]
   >
   >確定您有權使用身分圖表。
   >

   在此之前，會顯示&#x200B;**[!UICONTROL 變更為身分圖表]**&#x200B;對話方塊，以確保您在使用身分圖表進行拼接之前，已經完成資料集的身分圖表設定，這是[圖表型先決條件](/help/stitching/gbs.md#prerequisites)的一部分。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。


1. 從&#x200B;**[!UICONTROL 重新執行視窗]**&#x200B;下拉式功能表中選取重新執行視窗。 可用選項取決於您有權使用的Customer Journey Analytics套件。

儲存連線後，針對已啟用拼接功能的資料集進行的拼接程式會在開始擷取這些資料集的資料時啟動。

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
