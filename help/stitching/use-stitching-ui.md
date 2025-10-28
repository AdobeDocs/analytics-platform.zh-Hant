---
title: 使用匯整
description: 如何使用拼接
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta" type="Informative"
source-git-commit: 0afe57047e2038f1acd9f88a1e7992da9a2819b1
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 3%

---

# 使用匯整

您可以在已設定為連線一部分的一或多個事件資料集上啟用拼接。 您可以啟用彙整功能的事件資料集數目，會由您已授權的Customer Journey Analytics套件決定。

{{release-limited-testing}}

當您[建立連線](/help/connections/create-connection.md#dataset-settings)或當您[編輯連線](/help/connections/create-connection.md)時，您可以將拼接啟用為事件資料集之[資料集設定](/help/connections/manage-connections.md#edit-a-connection)的一部分。

## 先決條件

若要啟用連線UI中事件資料集的拼接功能：

* 資料集所根據的結構描述必須已定義：

   * 設定為身分的多個欄位，可讓您為永久ID和人員ID選取不同的值。
   * 至少一個標示為主要身分的欄位具有關聯的名稱空間，以備您將「身分對應」和主要身分名稱空間用於永久ID或人員ID。

* 事件資料集必須為Identity服務[啟用](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)，以備您想要使用Identity圖表和圖表式銜接時使用。


## 預檢檢查

如果您符合先決條件，在啟用身分拼接之前，可能會想要對事件資料集中的資料執行一些預檢檢查：

* 確保在事件資料集的結構描述中正確標示身分。 [請參閱身分名稱空間概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces)。
* 驗證永久ID和人員ID的身分涵蓋範圍：
   * 永久ID：查詢7天的資料，其中您的永久ID欄位不是Null，再除以資料集內所有事件的7天資料查詢。 此百分比應高於95%。

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

      * `{PERSISTENT_ID_FIELD}`是持續性識別碼的欄位。 例如：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}`是事件資料集的資料表名稱。
      * `{FORMAT_STRING}`是時間戳記欄位的格式字串。 例如：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE} `是開始日期。 例如：`2024-01-01 00:00:00`。
      * `{END_DATE}`是標準格式的結束日期。 例如：`2024-01-08 00:00:00`。


   * 人員ID — 查詢您的人員ID欄位不是Null的7天資料，然後除以資料集內所有事件的7天資料查詢。 此百分比應高於5%。

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



## 啟用身分識別拼接

>[!NOTE]
>
>如果Connections介面中無法使用&#x200B;**[!UICONTROL 啟用身分拼接]**，請使用[要求程式在資料集上啟用拼接](/help/stitching/use-stitching.md)。



若要啟用拼接，請在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;或&#x200B;**[!UICONTROL 編輯資料集]**&#x200B;對話方塊的事件資料集區段中：

啟用身分拼接時![身分拼接選項](assets/identity-stitching-ui.png)

1. 選取&#x200B;**[!UICONTROL 啟用身分拼接]**。

   如果您啟用現有事件資料集的彙整功能，**[!UICONTROL 變更人員ID]**&#x200B;對話方塊會顯示由於使用彙整功能而導致人員ID變更的影響。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

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
   >您必須有權使用身分圖表。
   >

   在此之前，會顯示&#x200B;**[!UICONTROL 變更為身分圖表]**&#x200B;對話方塊，以確保您在使用身分圖表進行拼接之前[已完成資料集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)的身分圖表設定。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。


1. 從&#x200B;**[!UICONTROL 回顧視窗]**&#x200B;下拉式功能表中選取回顧視窗。 可用選項取決於您有權使用的Customer Journey Analytics套件。

一旦您儲存的連線包含已啟用身分拼接的資料集，每個資料集的拼接程式都會在該資料集的資料擷取開始時開始。

## 限制

除了[欄位式拚接限制](/help/stitching/fbs.md#limitations)和[圖表式拚接限制](/help/stitching/gbs.md#limitations)之外，當您在「連線」介面中啟用拚接時，將會套用下列限制：

* 您只能將事件資料集拼接一次，做為單一連線的一部分。 您無法定義多個相同事件資料集，並為每個執行個體使用個別的彙整設定。 如果您想在相同資料集上套用不同的彙整設定，請為每個設定使用個別的連線。

